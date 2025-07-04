# Using AI For Content Authoring

You may see the following disclaimer in specific content items for this series. This includes blog posts and AMA recaps. 

> _This post was generated with AI help and human revision & review. To learn more about our motivation and workflows, please refer to [this document](https://github.com/microsoft/model-mondays/blob/main/docs/README.ai.md) in our website_

The document linked above is _this one_.


<br/> 

## About This Page

**This** page provides a deeper dive into how (and why) we are exploring AI for content generation. We have two goals for this:

1. **Transparency** - we want to be responsible in our use of AI and ensure that our readers know when and how it is applied in the content they read.
1. **Experimentation** - we want to share our own experiments and process with the community so they can potentially learn from our experience and adapt them to their own needs if useful

Think of this as a living document that we will keep updated to reflect our learnings.


<br/> 

## Expt 1: Automated TWIMM Blogs

Our first experiment is to streamline the creation of the _This Week In Model Mondays_ [blog posts](./blog/posts/) written by Sharda Kaur to keep up with the weekly pace of the series.

### Why we use AI

1. **Topic Complexity** - Model Mondays is a weekly series featuring a new technology and speaker in the "spotlight" segment every Monday. Many topics are new or contain advanced ideas that require a non-trivial amount of time to understand underlying concepts. _How can a learner pick up enough about the topic to write a recap and get insights from it for further exploration_.
1. **Time Pressure** - The recaps need to go out every week, ideally by Wed to allow our Friday AMA attendees to use it as a reference. A lot of the post will involve "boilerplate" sections - embed the slides, embed the livestream video, provide the title and description for the talk, and end with CTAs. _Having a starter template that provides the baseline content pre-filled can help meet deadlines_.


### How We use AI

1. The first post of the series was written manually. It helped us understand the components of the blog post and where to get the relevant information to fill it.

1. **Copilot Chat** - In the [second post](https://techcommunity.microsoft.com/blog/educatordeveloperblog/model-mondays-s2e2---understanding-model-context-protocol-mcp/4427914) the authors used [Visual Studio GitHub Copilot Chat](https://code.visualstudio.com/docs/copilot/chat/getting-started-chat) as a tool to _understand_ the topic (MCP) by _summarizing_ relevant references to the discussion (authorization). The document template itself (with the relevant sections) was created **manually**. 

1. **Agent Mode** - In the [third post](https://techcommunity.microsoft.com/blog/educatordeveloperblog/model-mondays-s2e2---understanding-model-context-protocol-mcp/4427914) the authors used [Visual Studio GitHub Agent Mode](https://code.visualstudio.com/docs/copilot/chat/chat-agent-mode) to take the workflow one step further by using AI to _scafffold_ a new post using the previous post as a "template", and using the [Season 2 schedule](./../docs/season-02/README.md) as data for _context engineering_ the initial draft.


**IMPORTANT**:
In each case, the final blog post was published only after human revisions and review by the main author and co-authors on the team. 

### What's Next

> 🚧 | This is a work in progress. 

We are continuing to understand and iterate on the process with two objectives in mind - (a) content quality and (b) content authenticity.

1. **Content Quality** - a core value of AI is that it exposes us to new content sources or perspectives we did not think about. This allows us to expand our awareness of a topic - but requires us to be more rigorous in both validating it, and ensuring that the tone & substance of the writing remains valuable. _This is adding a new shift in mindset to think about how we author prompts for quality_,

1. **Content Authenticity** - we want to reflect personal insights and real learner experiences in the process. These are areas that an AI cannot help with since it lacks the lived experience of beginners. _To do this, we are exploring prompts that ask for sections to be left unwritten - and instead asking the AI to do research to help us then craft the response manually_.

Check back on this post for updates on new experiments and more detailed write-ups on our workflow. Feedback and comments are welcome - [post an Issue](https://github.com/microsoft/model-mondays/issues).

---