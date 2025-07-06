<!---
Read this transcript for a livestream
Summarize it for a beginner audience with the following segments

What You'll Learn = a list of QUESTIONS that are answered here
Summary = Short paragraph summarizing key points of the discussion
Takeaways = 3-5 bullet points indicating key takeaways from the discussion
Related Resources = Relavant resources by URL mentioned in the transcript
Put this in a "===" fenced section at the start of the transcript file

copy this markdown result into a file in the same directory with the same name except "raw" is replaced by "aigen" 

Then update it with a section called Recap where you revisit the questions you identified and provide a 1-2 line answer from the transcript

update the newly created file to split the summary into highlights and spotlights sections reflecting the two different speakers. The highlights should have just 5 bullet points with the announcements.

Update the recap section to have a nicer format - for instance create a numbered list where question is in italics and response in normal font

update the doc but now use the Docs MCP server to add relevant resource links for Related Resourcea from the Microsoft Docs instead of just text
--->

## What You'll Learn
- What are reasoning models and how do they differ from regular chat models?
- What new AI models and features have been released in Azure AI Foundry?
- How do you build applications with reasoning models using tools like DeepSeek and LangChain?
- What are the advantages and limitations of reasoning models?
- How can you separate the "thinking" process from the final output in reasoning models?
- What tools and techniques help reasoning models access real-time information?
- How do you evaluate and test reasoning model responses for consistency?

## Highlights
- **Direct-from-Azure Models**: Microsoft now hosts and sells models from DeepSeek, XAI, Meta, and Mistral under Microsoft service terms with flexible provisioned offerings
- **Sora Video Generation**: OpenAI's video generation model is now available in Azure AI Foundry's new video playground with exportable code and enterprise-ready pipelines
- **Model Router**: A new model in the catalog that automatically selects the smartest, cheapest, and fastest route for your prompts, currently supporting OpenAI models with plans to expand
- **Grok 3 Models**: New Grok 3 and Grok 3 Mini models landed in Azure AI Foundry with long context (up to 131K tokens), advanced reasoning capabilities, and enterprise reliability
- **DeepSeek R1 Update**: The latest DeepSeek R1 (0528) model offers improved reasoning, better chain-of-thought processing, and enhanced hallucination blocking for production-ready applications

## Spotlights
This episode's main spotlight features Marlene Mahungami demonstrating how to build a "deep researcher" application using DeepSeek R1 and LangChain. The demo shows how reasoning models think step-by-step through problems using "think tags" to display their internal reasoning process, which can be separated from the final user response. The demonstration covers enhancing reasoning models with web search capabilities for real-time information access and building complex applications that generate high-quality research reports.

## Takeaways
- Reasoning models produce higher quality outputs but take longer to process due to their step-by-step thinking approach
- The "think tags" in reasoning models show the internal thought process, which can be separated from the final user-facing response
- Azure AI Foundry now offers a unified platform for various models with flexible deployment options (serverless, reserved, managed)
- DeepSeek models offer a good balance of quality and cost-effectiveness, especially for local deployment
- Model evaluation and testing are crucial from the beginning of development, not just at the end
- Reasoning models work well for complex tasks like research, analysis, and generating detailed reports


## Recap

1. *What are reasoning models and how do they differ from regular chat models?*  
   Reasoning models are LLMs trained with reinforcement learning that show their step-by-step thinking process through "think tags" and produce higher quality, more detailed responses than regular chat models.

2. *What new AI models and features have been released in Azure AI Foundry?*  
   Azure AI Foundry introduced direct-from-Azure models (DeepSeek, XAI, Meta, Mistral), Sora video generation in the video playground, model router for automatic model selection, and new Grok 3 and DeepSeek R1 models.

3. *How do you build applications with reasoning models using tools like DeepSeek and LangChain?*  
   Use the LangChain Azure AI package to access Foundry models, pass research queries as human messages, and separate the thinking process from final results using Python code that identifies think tags.

4. *What are the advantages and limitations of reasoning models?*  
   Advantages include higher quality outputs and detailed reasoning; limitations include longer response times, training cutoff dates that limit recent knowledge, and the need for tools like web search for current information.

5. *How can you separate the "thinking" process from the final output in reasoning models?*  
   Use Python code to identify start and end think tags, extract everything between them as the thinking process, and return everything after the closing tag as the final user response.

6. *What tools and techniques help reasoning models access real-time information?*  
   Provide web search tools and current date context to the model, allowing it to generate proper search queries and reason over real-time data from the internet.

7. *How do you evaluate and test reasoning model responses for consistency?*  
   Set up LLM-as-a-judge evaluations, use reflective processes where models reason over their own outputs, implement built-in evals, and start evaluation from the beginning of development rather than at the end.

## Related Resources
- [Azure AI Foundry Documentation](https://docs.microsoft.com/azure/ai-studio/) - Complete guide to Azure AI Foundry platform and model catalog
- [Azure OpenAI Service](https://docs.microsoft.com/azure/cognitive-services/openai/) - Documentation for OpenAI models on Azure including reasoning models
- [LangChain Azure AI Integration](https://python.langchain.com/docs/integrations/platforms/microsoft/) - Official LangChain documentation for Azure AI integration
- [Azure AI Evaluation SDK](https://docs.microsoft.com/azure/ai-studio/how-to/develop/evaluate-generative-ai-app) - Guide for evaluating generative AI applications
- [Model Router in Azure AI](https://docs.microsoft.com/azure/ai-studio/how-to/deploy-models-serverless) - Documentation on serverless model deployment and routing
- [Sora Video Generation](https://docs.microsoft.com/azure/ai-studio/how-to/generate-images-video) - Guide to video generation capabilities in Azure AI Foundry
- [Direct-from-Azure Models](https://docs.microsoft.com/azure/ai-studio/how-to/deploy-models-managed) - Information about Microsoft-hosted model offerings