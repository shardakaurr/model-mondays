# Using GitHub Copilot With Visual Studio Code

This document captures guidance, learnings and troubleshooting tips for using GitHub Copilot with Visual Studio Code to support AI-driven content generation.

---

## Getting Started 

> For safety/convenience, I always use MCP within a Dev Container environment in GitHub Codepsaces or Docker Desktop. And I use the stable version of VS Code to ensure reuse by others.

1. [Add an MCP Server](https://code.visualstudio.com/docs/copilot/chat/mcp-servers#_add-an-mcp-server) - sets up `.vscode/mcp.json`
1. [Add GitHub MCP Server](https://github.com/microsoftdocs/mcp) - with Personal Access Token
1. [Add Microsoft Docs Server](https://github.com/microsoftdocs/mcp) - with "search" tool access for grounding links

**Tip**: When configuring the GitHub server, choose the option that uses the Personal Access Token. Note that it is configured to _use the inputs feature_ to ask for the token interactively at the time you start the MCP server. You now have two options:
1. Go to [GitHub Settings](https://github.com/settings/personal-access-tokens) and generate a token on demand each time. You will not see this again so you will need to regenerate the token each time, or copy it somewhere (which is a security issue).
1. Do the step above - but then save it to a [Codespaces secrets](https://github.com/settings/codespaces) environment variable which can then get associated with any repo. Now, the relevant token will be visible in your Codespaces env variable at runtime, making it easier for you to copy it into input when asked (without exposing it externally).

Here is an example of the file with the Microsoft Docs MCP and GitHub MCP servers configured. _Since the `.vscode/` folder is gitignore-d, you will not see this in the version controlled codebase_. You can add the MCP servers in interactively or just recreate this file in your active session. _The file will have `Start Server` annotations over each server for easy start/stop controls.

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