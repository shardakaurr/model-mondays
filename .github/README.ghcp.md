# Using GitHub Copilot With Visual Studio Code

This document captures guidance, learnings and troubleshooting tips for using GitHub Copilot with Visual Studio Code to support AI-driven content generation.

---

## Getting Started 

> For safety/convenience, I always use MCP within a Dev Container environment in GitHub Codepsaces or Docker Desktop. And I use the stable version of VS Code to ensure reuse by others.

1. [Add an MCP Server](https://code.visualstudio.com/docs/copilot/chat/mcp-servers#_add-an-mcp-server) - sets up `.vscode/mcp.json`
1. [Add GitHub MCP Server](https://github.com/microsoftdocs/mcp) - with Personal Access Token
1. [Add Microsoft Docs Server](https://github.com/microsoftdocs/mcp) - with "search" tool access for grounding links
1. [Add Hugging Face MCP Server](https://huggingface.co/settings/mcp)

### Config Tips

The MCP Server configuration may require the use of secrets (e.g., GitHub PAT or Hugging Face token) in the configuration file in cleartext. The `mcp.json` file is _never_ checked into GitHub for version control to prevent leaks of these tokens. 

_But how can we then remember and reuse these secrets in successive runs?_. 
The easiest way is to store these values in GitHub Codespaces secrets, and have them be made available to your Codespaces (repo) automatically as env variables. Let's see how.

1. First, create the tokens you will need for these MCP servers.
    1. Create Fine-grained [GitHub PAT](https://github.com/settings/personal-access-tokens) for GitHub tools
    1. Create Read-only [HF-TOKEN](https://huggingface.co/settings/tokens/new) for Hugging Face tools
1. Then create [Codespaces secrets](https://github.com/settings/codespaces) with names you will associate with these tokens - and select the relevant repositories that you will be using them in. _Now, when you launch Codespaces on that repo, the secrets will be available automatically as named env variables.
1. Now, when the `.vscode/mcp.json` file is created, you can "fill in" the required tokens when needed. For instance, in the sample file below:

- Hugging Face token is hardcoded in the mcp.json file - so just copy the value from env variables into the file.
- GitHub token is taken from the input field - so just copy the value from env variables into the input prompt you will see when starting the server.

### Sample MCP Config

This is the `.vscode/mcp.json` that I use for this project. Note that you will need to replace the `<YOUR_HF_TOKEN>` from the HF secret above, and the enter a valid Github PAT when prompted for `GITHUB_PERSONAL_ACCESS_TOKEN` as input.

```json
{
    "inputs": [
        {
            "type": "promptString",
            "id": "github_token",
            "description": "GitHub Personal Access Token",
            "password": true
        }
    ],
    "servers": {
        "microsoft-docs-mcp": {
            "url": "https://learn.microsoft.com/api/mcp"
        },
        "github": {
            "command": "docker",
            "args": [
                "run",
                "-i",
                "--rm",
                "-e",
                "GITHUB_PERSONAL_ACCESS_TOKEN",
                "ghcr.io/github/github-mcp-server"
            ],
            "env": {
                "GITHUB_PERSONAL_ACCESS_TOKEN": "${input:github_token}"
            }
        },
        "hf-mcp-server": {
            "url": "https://huggingface.co/mcp",
            "headers": {
                "Authorization": "Bearer <YOUR_HF_TOKEN>"
            }
        }
    }
}
```



## Troubleshooting

## Related Resources

1. [VS Code Documentation](https://code.visualstudio.com/docs/copilot/overview)
    - [Use Agent Mode in VS Code](https://code.visualstudio.com/docs/copilot/chat/chat-agent-mode) - copilot will autonomously execute the task for you
    - [Use MCP Servers in VS Code](https://code.visualstudio.com/docs/copilot/chat/mcp-servers) - expand context to remote data/actions with "tools"
    - [MCP Developer Guide](https://code.visualstudio.com/api/extension-guides/ai/mcp) - create your own MCP servers for _others_ to use as context
1. [GitHub Documentation](https://docs.github.com/copilot)
    - [Copilot Plans](https://docs.github.com/en/copilot/get-started/plans-for-github-copilot) - tier sets model access & premium request rate limits
    - [Copilot best practices](https://docs.github.com/en/copilot/get-started/best-practices-for-using-github-copilot) - choose right tools, craft good prompts, validate!
    - [Copilot billing](https://docs.github.com/en/copilot/concepts/copilot-billing/understanding-and-managing-requests-in-copilot) - understand premium requests & cost/rate limitations
    - [Chat Cookbook](https://docs.github.com/en/copilot/tutorials/copilot-chat-cookbook) - prompts to debug, test, explain, document, or refactor.

## Tips For Usage

> Start by [comparing plans](https://docs.github.com/en/copilot/get-started/plans-for-github-copilot#comparing-copilot-plans) - and remember that a "premium request" is effectively a multiplier imposed on the interactions. So, 1 chat interaction with a premium model will use (multipler) premium requests, burning through your premium requests quota faster.
- Free tier has 50 chat messages, 2K code completions, 50 premium requests
- Paid plans have unlimited chat, code completions with higher premium requests
- Free tier has limited models accessible compared to paid tier
- In both cases model selection menu shows **model multiplier** for premium requests

> Track ongoing usage [here](https://github.com/settings/copilot/features) in your GitHub settings. 

- You should see a "Usage" percentage for premium requests and explore [Billing docs](https://docs.github.com/en/copilot/concepts/copilot-billing) for more detailed analysis based on tier. When selecting a model from the Copilot dropdown, look at the default multiplier values (right) and pick the right model for the job.

- **For some paid tiers**, when the _premium requests_ quota runs out, Copilot will drop back to use Standard models (multiplier=0 so they don't need premium requests). _This is not the case for Free tier_ where you will need to move to paid to continue.

Explore [Cookbook tips](https://docs.github.com/en/copilot/tutorials/copilot-chat-cookbook/debugging-errors/handling-api-rate-limits) into using practices like backoff-and-retry to get around rate limits.



---