
0:01
hello everyone and thank you for joining us for today's session my name is Danny and I'm the event planner for the New
0:07
York Reactor Space before we start I have a few things to go over please take a moment to review our code of conduct
0:14
we seek to provide a respectful environment for both our audience and presenters we encourage engagement in
0:19
the chat but please be mindful of your commentary remain professional and on topic useful links will be shared in the
0:26
chat the session is recorded and will be available on demand in 24 to 48 hours on
0:32
the Microsoft Reactor YouTube channel which brings us to today's session it
0:38
will run for approximately 30 minutes with time for questions throughout i will now turn it over to our speaker for
Introduction to Model Mondays Series
0:44
introductions hi everyone good afternoon good morning
0:49
good evening wherever you are in the world today is series three of model Monday so I'm Lee Star i'm a principal
0:55
cloud advocate manager unfortunately I'm not Nitia nit is in the background today so Nitia is answering all our questions
1:02
on LinkedIn and on YouTube so we are streaming on those two channels today as
1:08
Danny said this session will be recorded and made available on demand after today
1:13
so if you do have any questions or you want to follow up with us please do talk to us in the Discord and on the GitHub
1:19
discussion so as always we have Shemila here with us today to talk about models and we also have our guest Mohan Japili
1:27
from the the FI models team so Moan is going to talk about what her experience
1:32
is with the FI models but first of all let's get started with Shemila and talk about Model Monday so hopefully you've
What is Model Mondays?
1:39
all been to Model Mondays before this is series episode three of series two um
1:44
each week we try and break down a different aspect of the Azure AI Foundry model catalog and talk around specific
1:51
model features services or tooling to help you get started with your AI
1:56
developer and AI engineer experiences we host those on Mondays hence the model
2:02
Monday's name and then we do a follow-up on Fridays which is an AMA but because this week is the 4th of July it's a
2:10
pretty special day for those people in the US as you can tell I'm not in the US but we're going to have Model Friday
2:16
Foundry Fridays now on Thursday so this Thursday we'll be hosting uh Foundry
2:21
Thursdays with Mohan talking about the fine models but we'll come into that in a little bit more so if you are
2:28
interested please check out Model Mondays please register for future events you can see all the different
2:33
activities we have coming up so Shema over to you for our weekly highlights
Azure AI Foundry Weekly Highlights
2:39
from Azure AI Foundry
2:46
thank you Lee and welcome to Model Mondays your weekly roundup of what's new in Azure AI Foundry so again we're
2:53
going to talk about what actually matters to you in this week's highlights um as a developer we have five updates
3:00
this week all high impact low flop fluff and as usual every highlight has a QR
3:06
code so take a screenshot of it and that QR code usually takes you to a blog or to a GitHub repo or even to the model
3:14
card depending on what the news is so let's get started
Safety Leaderboards & Responsible AI
3:19
so first up Azure AI Foundry uh just launched safety leaderboards it's a big
3:25
step towards responsible AI we did have leaderboard um a model leaderboard announced a few weeks back and it had um
3:35
things that could you could check for performance latency and cost but now uh
3:42
we are taking a big step towards responsible AI this new addition to the leaderboard lets you evaluate and
3:48
compare models based on safety benchmarks like jailbreak resistance and prompt injection resilience you can now
3:56
make informed decisions not just on performance and cost but also on trustworthiness before they bite you in
4:02
prod so it's a great step if you're shipping anything that's customerf facing in production or if you're
4:08
shipping things in regulated industries or domains moving on next is foundry local in and
Foundry Local in Public Preview
4:16
it's now in public preview so these are these uh foundry local has Azure hosted
4:22
models that run entirely on your infra so you can now deploy LMS vision models and more in a container with no internet
4:29
dependency it boots instantly works in air gap settings and brings AI to edge
4:36
use cases without latency or compliance trade-offs next highlight is model context protocol
Model Context Protocol (MCP) Support
4:44
support so last week we talked about MCP support in foundry models now today we
4:49
are talk going to talk about MCP support in Azure AI agent service so if you
4:55
built with multiple models in production you know how routing logic can get really messy and MCP support lets your
5:03
app reason about context and route task to the best model automatically so fewer
5:09
if else blocks more intelligent abstraction is what you get with MCP support in foundry agent service
Fine-Tuning Enhancements in Foundry
5:18
now moving on um we've not been talking a lot about fine-tuning in the past few
5:24
months but recently fine-tuning in foundry just got a serious boost so we
5:30
have rolled out new models uh and also new capabilities like reinforcement fine-tuning with O4 mini supervised
5:37
fine-tuning for GPT4.1 nano and then fine-tuning support available for llama
5:43
force code models which we announced um last month and this means you can lower
5:51
cost do faster training and better results with less data so you don't torch your budget or the data so it's
5:58
perfect for customizing performance without retraining for from scratch
Microsoft Named Leader in Gartner MQ
6:05
and finally a quick shout out microsoft has been named a leader in the 2025
6:10
Gartner Magic Quadrant for data science and machine learning platforms for the second year in a row this is the big
6:17
validation of the Azure AI platform and its commitment to building tools that scale across AI life cycle from
6:24
experiment to production and that's a wrap whether you're working on edge AI
6:29
agent routing or fine-tuning Azure AI foundry has real tools to speed up your
6:35
built build cycles so see you all next Monday in another set of highlights and
6:40
I'm going to hand it over back to Lee thank you
6:46
thanks Sha so again you know great update there from the the product team around different things that are
6:52
happening in Azure AI Foundry again a big call out you know in terms of the Gartner magic quadrant you know Azure AI
6:58
foundry is now within the top sector of the quadrant so again lots of activities happening please do check that out have
7:04
you got any other key insights or or updates for us live on air
7:10
live on air so there are I mean just watch out in the next few days we have
7:15
more models dropping so uh oh a new day a new model yeah exactly so we I'll come
7:22
back next week but for Now I think we had a really good set of updates a lot
7:27
lot of things happening on MCP so I'm I'm guessing folks will be interested and last week we had the MCP episode so
7:34
that's a continuous drum beat that we're doing so uh please keep an eye out for that yeah excellent yeah and again with
7:42
MCP we've launched the MCP for beginners um which is a hands-on guide if you're interested in working with MCP from
7:48
being beginner to very advanced and we cover things like security what is MCP how to use MCP so please do check that
7:56
resource out on our our Discord channels as well so huge thank you Shamila so let's move over to our guest so today
Weekly Spotlight: Small Language Models (SLMs)
8:03
we're going to do our weekly spotlight and we're going to be talking about small language models so SLM and
8:09
specifically the new reasoning models from the FI team so the F4 reasoning
8:14
model so Mohan Jaffa is from the actual FI team she's from the product team and
8:20
she's one of our senior researchers in Microsoft research so the actual team behind the development of the FI model
8:26
so I'd like to welcome Moan to the to the stage and we've got a great session
Meet Mohan Japili from the FI Models Team
8:32
lined up for you and then we're open to Q&A so great to meet you Moan so give us a bit of background who you are and what
8:38
do you work on hi um thanks Lee for the introduction uh
8:43
so I'm a senior researcher at Microsoft Research uh we um you know do
8:49
pre-training and post- trainining on small language models and our hope and um kind of goal is to uh bridge the gap
8:56
between frontier models and SLMs and try to kind of match the performance in a
9:01
lot of areas and the main motivation behind SLMs is that they are much easier to fine-tune and customize for you know
9:08
downstream tasks that uh folks are interested in they're much easier to iterate on and much more efficient and
9:14
uh kind of cheaper to do large scale inference so we are really pushing the capabilities of these models and trying
9:20
to see uh what is possible with them i've got a question before you you know we go into your demos you know so if
9:27
you're going to explain to someone a small language model versus a large language model what the key
9:33
characteristics that's a great question and I think that we are constantly um shifting the def
9:40
the definition of SLMs as well maybe back in 2023 SLM would have been
9:45
anything below uh maybe three billion parameters but as the hardware and also
9:51
the demand for the capabilities has grown grown i would say that we are kind of becoming more ambitious on how many
9:57
parameters we allow our models to have for an SLM but I think as a general guideline we would like to have models
10:04
that can run typically on commodity hardware such as a laptop or maybe not like a um you know state-of-the-art GPU
10:12
so I think as long as we can host our models on uh settings such as that then
10:17
I think we are we can fall within the definition of SLMs but like I said as
10:22
you know the underlying hardware and the frameworks for inferencing becomes uh more mature and more uh you know
10:28
customized I think that we can push the definition of SLM to even mar more larger models as well excellent so we
10:35
we'll go into your demo and hopefully we'll get some questions and we can have a bit of a Q&A after the after the demo
Demo: Introduction to FI Reasoning Models
10:41
so yeah let's see the demo hi everyone my name is Mojon and I'm a
10:47
senior researcher at Microsoft research air frontiers lab and today I wanted to talk to you about our most recently
10:54
released models fo reasoning before going into the details I wanted
10:59
to first explain what reasoning models are and why are they important
11:06
so the core characteristic of the reasoning models is that they follow explicit logical steps in order to solve
11:12
the problems and that means that they decompose the a complex problem into sub
11:17
problems in order to solve each of the steps and this is kind of similar to how humans think and they work by iterative
11:24
refinement meaning that they constantly backtrack and doublech checkck and verify that the previous steps that
11:30
they've taken to solve the problem have been correct and if not they make them correct and all of this happens through
11:36
an explainable process so all of these models are generating what we call a thinking trace that kind of shows you
11:43
all of the rationale and the reasoning path that the model is taking to reach the final solution and this is
11:49
especially helpful if you want to verify where the answer comes from and double check everything step by step
Why Reasoning Models Matter
11:57
so because of the capabilities that I just described reasoning models are really well suited for complex decision
12:03
making and this involves uh mathematical reasoning like solving equations and proofs strategic planning like
12:09
multi-step problem solving algorithmic thinking like developing systematic approaches and also logical analysis
12:15
where you need to evaluate complex arguments now let's take a look at the five
12:20
reasoning models late last year we released the 54 non-reasoning model which is a 14
12:27
million parameter dense decoder only transformer architecture and all of the FIF for reasoning models are built on
12:34
top of 54 through a specific post-training process the first model in the family is 54 reasoning which is
12:40
fine-tuned on more than 1.4 million STEM and coding questions and 54 reasoning
12:46
plus is a further enhanced versions that has a short reinforcement learning step
12:53
what is special about the five for reasoning models is that they're really competing with models that are five to
Overview of the FI Reasoning Model Family
12:58
50 times larger their size while maintaining superior efficiency and performance per parameter and they have
13:04
they have an extended context length of up to 32,000 tokens that allows them to go through complex reasoning chains and
13:11
comprehensive problem analysis and at 14 billion parameters they're actually very suitable to efficiently run even on
13:19
commodity hardware such as laptops fifer reasoning family have
13:24
unprecedented reasoning capabilities that outperforms larger openweight models and is competitive with some of
13:30
the state-of-the-art models despite being only 14 billion parameters in size so for example we are better across the
13:36
board compared to deepsek distillation of llama 7TB and better on most hacks
13:42
compared to cloud 3.7 while having superior performance compared to Gemini 2 thinking and we've evaluated our
13:48
models in various reasoning domains including mathematics scientific reasoning coding and programming
13:54
algorithmic problem solving planning and scheduling and spatial understanding as I'll talk about later today
14:01
and so far we've seen really strong community adoption with more than 30,000 downloads for FIFO reasoning on hogging
14:08
face and 84 quantized models um contributed by the community and 24,000
14:14
downloads on FIFO reasoning plus with 26 quantized models and the most popular quantized variants is the onslaught jig
14:21
version which has 120,000 downloads so far
Community Adoption & Feedback
14:27
and we have been receiving really strong positive feedback online and from the community as well that talk about the
14:33
reasoning power of these models and how they outperform larger models on math logic and coding how they have a clear
14:39
train of thought which is intentional and it's easy to follow the multi-step outputs that the model is generating
14:46
they are very efficient in deployment and the value of the open weight which allows um the community to run local
14:53
inference it's free and accessible and also allows them to do fine-tuning and various specializations on top of this
14:58
model uh the community also appreciated our rigorous benchmarking and in fact
15:04
all of our uh benchmarking code is open source and available online and also they have contributed various quantized
15:11
versions as I mentioned such as the onslaught version which have been very very helpful and popular
Training Pipeline: Data Curation
15:18
now in order to train for excellence we have three fundamental pillars and steps in our design process for the 54
15:24
reasoning models the first step is data curation and it starts by collecting and filtering high
15:32
volumes of data and when we do this collection and filtering we are really focused on four different strategies the
15:38
first one is that the prompts should be teachable so they're selected to have the optimal complexity and diversity in
15:45
order to teach the most content to the model and they're really selected to be at the edge of base model capabilities
15:51
in order to kind of boost the performance of the model to the max and we really filter for high quality
15:58
and have a high bar for quality control when we are selecting our data and we make sure that we cover a lot of the
16:04
domains that we want the model to be good at such as STEM coding and also safety focused tasks and once we have
16:10
gathered our prompts and questions we generate detailed reasoning chain of thoughts using 03 mini as a teacher
16:17
model and these high quality step-by-step demonstrations are later showed to the model in the training data
16:23
in order to achieve that problem solving capability and we really focus and emphasize on data mixture and we do a
16:30
strategic combination of different domains and difficulty levels and different data sources in order to make
16:35
sure that our models are you know uh comprehensively capable across multiple
16:41
problem types and the data mixture is essentially a
16:47
carefully balanced mixture across various domains to ensure broad reasoning capability and robust
16:53
performance and the domains that we consider in high level are STEM uh which is science technology engineering and
17:00
mathematics we have coding which is focused on algorithm design problem solving code generation and debugging
17:06
and finally safety which focuses on content moderation ethical reasoning harm prevention and responsible AI and
17:13
when designing these data mixtures we are really careful on creating it and we emphasize on data quality over quantity
17:21
and we acknowledge that the data mixture and the training recipe are actually fundamental to the success of the model
Supervised Fine-Tuning & Key Insights
17:28
the second stage of our training is supervised fine-tuning and we actually have a multi-step process for this one
17:34
as well the first step is exploration where we are really establishing our training recipe and we focus on doing a
17:40
lot of ablations and experiments on single domain data sources and we also really tune our training hyperparameters
17:47
and just the general training algorithm and we had a couple key insights during our explorations which is that synthetic
17:54
act data actually improves the final answer precision a lot and we find it to be very helpful as we have outlined in
18:01
the technical report as well and we notice that reasoning specific system messages actually boost the consistency
18:07
and performance of the model and that is why in the model card we actually suggest a system prompt that the model
18:13
has been trained with and encourage everyone to consistently use that specific system prompt now we also
18:19
notice that as the model becomes better and the quality improves the response length decreases as the thinking process
18:25
becomes more efficient and coherent and we also notice that there is an additive property across domains in the
18:32
data mixture where we can really individually optimize the data sources within one domain and then confidently
18:38
combine all of the domains together in one final run and that brings us to the second stage which is really the scaling
18:44
up of the training and inference so in this phase we really combine all of the data from all of the different domains
18:51
that we've optimized previously we use a better teacher model and allow essentially an inference time scaling of
18:57
the teacher model in order to generate longer responses and we support these longer responses to allow our model to
Reinforcement Learning for Accuracy
19:04
uh solve more complex problems by thinking more the final stage of our training is a
19:10
short reinforcement learning using outcome based rewards with verifiable solutions which enables the model to
19:17
learn from the success and failure patterns of the answers that is generating and we really focus on math
19:23
problems and we select 6,000 high-quality mathematical problems to conduct the reinforcement learning over
19:30
and what we observe is that throughout the reinforcement learning the length of the reasoning traces actually increases
19:35
and the model generates approximately 1 1.5 times longer reasoning chains while
19:41
providing more detailed step-by-step problems solving approaches and this really provides an accuracy versus
19:47
efficiency trade-off to the users where the reinforcement learning checkpoint offers higher accuracy at the cost of
19:52
increased token usage and this really is a choice between efficiency and performance
19:59
so we really have two models and two strategies and the users can choose between efficiency and maximum accuracy
Choosing Between Reasoning & Reasoning
20:06
based on the specific use case so on the one hand side the supervised fine-tune model which is 54 reasoning is
20:11
efficiency optimized and it uses tokens efficiency it has faster inference and lower computational cost and still a
20:18
very strong reasoning performance so this is well suited for fast lightweight logical reasoning and structured problem
20:24
solving with lower latency and FIFO reasoning plus on the other hand is accuracy maximized
20:30
so it has higher accuracy especially on math related questions with longer reasoning traces and more detailed
20:37
explanations that can have on average 1.5 times longer generations and this is
20:43
really best suited for handling more complex multi-step reasoning tasks with improved accuracy and a broader
20:49
generalization now let's take a look at the benchmarking of the models
Benchmarking Results: Math, Science, Coding
20:56
so the five for models including the reasoning and reasoning plus have all been rigorously benchmarked across two
21:02
primary categories the first one is reasoning specific capabilities that focus on tasks that benefit from this
21:08
step-by-step problem solving and logical reasoning and the second one is general purpose capabilities that are broad
21:14
abilities including you know simpler reasoning and other behaviors now the most popular benchmarks that are
21:21
evaluated for the reasoning models are mathematical reasoning and in that prompt the first one is AM 2025 which is
21:28
the qualifier for the USA math Olympia and this exam is actually contamination free because it came out after we had
21:35
already gathered our data sets and trained our models and as you can see we
21:40
actually have performance on this benchmark that is comparable to the full DeepSseek R1 model which has over 50
21:46
times more parameters compared to 54 reasoning models the second set of problems HMNT or Howard MIT mathematics
21:53
tournament and what is exciting to see here is that we really outperform the distilled version of DeepSec R1 in Llama
22:00
7V which is five times larger and we also outperform 01 mini and 01 from the open AI models as well as the original
22:08
DeepSeek R1 and similarly on OmniMath which has more than 4,000 Olympia level
22:13
problems in algebra calculus geometry and number theory we have over 40%
22:18
improvement over the base model which is the non-reasoning 54 while outperforming 01 mini 01 and also LMA 7TB
22:27
the second set of benchmarks are for scientific reasoning and GPQA is graduate level Google proof Q&A
22:33
benchmark that has expert design questions and answers in biology physics and chemistry and on this benchmark you
22:40
can see that the 14B models have better performance than 01 mini and the distillate version of Llama 70B
22:47
reasoning on these PhD level questions and finally for coding we evaluate live
22:52
codebench which is a challenging coding benchmark and we see that we have over
22:58
25%age improvement points on on this benchmark compared to the non-reasoning
23:03
54 another thing that is worth noting is that the models have strong
Generalization to Out-of-Domain Tasks
23:08
generalization to out of domain tasks as well so what we did was we took the models and we started evaluating them on
23:15
reasoning benchmarks that are really out of distribution with respect to the data that we have trained the models on and
23:20
that includes three set or three literal satisfiability problems which are solving MP hard problems and we saw that
23:27
we actually had 60% improvement compared to the base non-reasoning five for model
23:33
similarly for the traveling salesman problem which is again an NP heart problem both of the models were able to
23:41
get more than 30% improvement compared to non-reasoning models and finally for
23:46
calendar planning which essentially tries to find a common time slot given a series of complex constraints we have
23:53
50% improvement compared to the base non-reasoning model even though again none of these tasks are things that we
23:59
explicitly had in our training data so this really suggests that once the model learns reasoning as a meta skill it can
24:06
generalize and apply it to new domains that it hasn't seen before
General Purpose Capabilities & Safety
24:11
and we also saw really good performance on general purpose benchmarks even though again these were not targeted in
24:17
the post-training process for example these models have improvements compared to the base architecture in instruction
24:23
following in long context question answering and also just in general in terms of human preference which is
24:29
represented by the arena hard benchmark the reasoning models also perform really
24:36
well on information retrieval tasks as measured by the ketop uh benchmark and
24:41
they're also really good in terms of safety and responsible AI measured by the toxygen benchmark that kind of uh
24:49
sees whether the model can detect toxic content and whether it can correctly identify neutral content on the other
24:55
hand and we saw consistent improvements across these different benchmarks compared to other models as well as the
25:01
base non-reasoning model now let's take a look at the use cases
Real-World Use Cases for FI Reasoning
25:06
given all of the benchmarks that we've seen so far and the reason why we think FIFO
25:11
reasoning is really amenable to use is the fact that it's competitive with much larger models despite being only 14
25:17
billion parameter in size which make them super efficient and compact to do inference and we've also noticed a lot a
25:24
lot of transferable skills where reasoning not only improves in the domains that we've targeted where we are
25:29
training data but we also saw improvements on out ofd domain tasks and also general purpose tasks and we've
25:35
shared all of our methodology um through a technical report that we think will help advance the entire field and kind
25:41
of help boost that research and uh you know development and in terms of use cases um that we
25:48
envision for 54 reasoning uh plus and 54 reasoning includes intelligent tutoring
25:53
system that require a personalized math and science tutor with step-by-step reasoning to solve complex um you know
25:59
problems show adaptive learning paths and also run efficiently on tablets and devices and also scenarios that require
26:06
autonomous agents that can um handle logic heavy reasoning for complex multi-step problem solving and this
26:13
includes planning and execution self-reflection capabilities and in fact our models are already being used in
26:19
some of the open source autonomous web agent frameworks and we envision people to uh build on
26:26
top of the five for reasoning models in order to further um you know pursue the research and accelerate the research as
26:33
a foundation as well as in order to um test scientific hypothesis and perform
26:38
data analysis and gain insights and finally we envision it being able to be
26:43
used for customer service and support like intelligent routing or a fallback assistant for high volume customer
26:50
interactions that can handle automated ticket classification or complex query resolution
26:57
we also think that FIFO reasoning can be um integrated in next gener uh
27:02
generation development tools for example in order to help with software development such as code generation and
27:07
debugging and help users understand um the code better with detailed reasoning chains that kind of explain the
27:13
different algorithmic approaches and also help them optimize um different strategies for the code and in fact our
27:20
models are already being used in autonomous coding agents and um the models can also help with
27:26
automated code review and get integrated into systems that can identify the errors or suggest optimization and
27:32
ensure just overall high code quality um they can also be used for strategic
27:38
planning um and complex scheduling like you know project management resource allocation timeline optimization uh that
27:45
has different constraints and different priorities or various uh methods or flavors of resource management like
27:51
optimizing human resources equipment allocation budget distribution and this includes you know various complex
27:58
organizational structures and project requirements and in terms of summary and key
Summary of Key Advantages
28:03
advantages um five for reasoning models are are able to do multi-step problem
28:08
solving and break down the problem into sub problems in order to solve it better they have internal reflection and
28:14
self-evaluation in order to doublech checkck the process and their own solutions they have um you know
28:20
strategic exploration built into them in order to test multiple approaches before solving the problem and they also
28:27
support inference time scaling and generate you know longer responses as needed in order to tackle the task at
28:33
hand and they have also some business advantages like the fact that they're cost effective and they outperform you
28:39
know variants that are you know 50 billion parameters five times larger and above they are enterprise ready because
28:44
we have really had a safety focused training and we have uh built the safety uh you know safeguards inside of the
28:51
models and they are easily customizable for specific business needs by running additional fine-tuning on top of them
28:58
and they do provide reasoning at a small scale you can um you know enjoy fast deployment because of the smaller size
29:04
and faster inference they are device friendly and run on tablets and uh you know laptops and phones and they're
29:10
small and compact this concludes my talk and I would like to thank all of you for attending and
29:16
here are some of the resources in case you're interested to kind of learn more about the FIFO reasoning models and the
29:22
project
Audience Q&A: Edge Devices & Quantization
29:29
great thank you we've got some great questions from the audience so you know overview of of the models there was was
29:37
really comprehensive and I think you know one of the first questions was you know would a small language model be
29:42
better to incorporate on edge devices and you touched a little bit on this but could you go into a bit more details
29:48
about you know are they available in CPU GPU MPU variants sure absolutely so I
29:55
think we have um quite a few different quantized versions that have been you know contributed from the community as
30:01
well as Microsoft so Microsoft recently introduced um like some onyx um
30:06
optimized models that are for bit uh int for quantized we also have some other
30:11
variants u that are available and um I believe that we we um are sharing the
30:17
links with the audience that I um you know encourage them to take a look at them they're available in VS code um you
30:24
know AI toolkit we also have um some um quantized versions available on hugging
30:29
face that uh you know folks can download and take advantage of like 4-bit um you know 16 bit and 8 bit quantiz variants
30:36
um by onslaught that have been um you know very popular as well excellent yes
Why SLMs Excel at Math Reasoning
30:41
so um we've got more details around AI toolkit next week so if you are interested please come on to that
30:47
session another question was you know why do you think these small language models are so good with mathematical
30:53
reasoning um I think that mathematical reasoning is is kind of just a an interesting and
31:01
maybe lowerhanging fruit but it doesn't necessarily it's not an end goal for these models and it's just to showcase
31:07
that they are able to perform you know rigorous um steps and break down the problem into you know soft problems and
31:14
able to doublech check and kind of test multiple different hypothesis at the same time and the fact that they are
31:20
doing well on mathematics I think is encouraging because it shows that they can also apply the same meta skill of
31:27
reasoning into other domains as well like we are very excited to explore more on the you know agentic tool use that we
31:34
are actively working on and conducting research on and also other areas that I mentioned um in the talk excellent so
SLMs for Biometric & Health Monitoring
31:41
this really brings me on to our next question is you know can small language models be trained to recognize and alert
31:47
for dangerous symptoms clusters using real-time biometric such as wearables
31:55
sure um that's a that's a great question and I think that one thing that um like the answer is definitely yes but I think
32:03
an interesting nuance here is that all of these you know SLMs and even LLM are trained on natural language so I think
32:10
that one thing that we would need here is kind of like a wrapper that translates the biometrics and the sensor
32:16
information that has been gathered from the variable devices into you know natural language explanation of what is
32:22
happening and then we can definitely use these models to go over the transcript and kind of categorize and pick up the
32:30
important signals and try to kind of give you know alerts or just do general
32:35
um classification so the final question we've got two questions which are very similar so I'll
SLMs in Healthcare & Finance + Fine-Tuning
32:41
put them together so the question is one's about health care so can you use a small language model to enhance patients
32:48
triage clinical decision making in tele medicine environments and the other one
32:53
is around finance and this is like can SLMs be used in finance so I think they both sort of are very good questions
33:00
because they link to fine-tuning of models so do you want to talk a little bit about you know you had a very good
33:06
highlight of you know producing fine-tuned models in your in your session but can you go into a bit more
33:11
detail of how someone can take a model and then fine-tune that model for a specific task
33:17
yes absolutely um I think that um like a lot of the general capabilities are are
33:22
baked into these models but I think that you know as users come up with their own evaluation for their own tasks um they
33:30
can see some shortcomings in some areas which can definitely be uh you know patched with fine-tuning um I know that
33:36
the general methodology that we um you know carried over to teach the models you know mathematics or coding the same
33:43
kind of concepts apply you can do you know supervised fine-tuning on you know little amounts of data and you can
33:50
already see you know big boosts happening on certain areas and certain um you know evaluations reinforcement
33:57
learning is another very promising avenue to fine-tune the models although it can be a little bit tricky to kind of
34:02
get right so I would suggest you know start by evaluating the models um see
34:08
where the gaps are try to generate data that exactly targets those specific skill gaps that you're observing and
34:14
then start with supervised fine-tuning um and we have many great um frameworks for that as well available um that you
34:22
know we can link on on discord channels um for uh folks if they're interested
34:27
and then um you know finally the cherry on top would be reinforcement learning um
FI Model Family Overview
34:33
brilliant so we've just got another question around the fi silica models so fi silica models now ship within the
34:40
windows AI PCs and the question is is really around you know um utilizing a fi
34:46
silica now I know filica is out of a different team but again it's the same process you would use something like
34:51
Laura to fine-tune that using the AI toolkit yes do you want to sort of explain the family of the fi models
34:57
because there is quite a lot of fi models now isn't there sure yeah absolutely and I think that we actually
35:02
work very closely with the Windows team who's ship shipping the fi silicon model we are you know sharing our data and in
35:08
fact we are actively doing uh a fine-tuning and reasoning fine-tuning on one of the models that they pre-trained
35:15
for them and working very closely uh so I think that in high level we have quite a few different you know models in the
35:21
series we have 53 models that actually have uh you know different sizes and we have 54 which was recently released at
35:28
14 billion parameters so these are kind of the general purpose SLMs and then in
35:33
the reasoning family we have the two um kind of reasoning and reasoning plus models and we also have a mini reasoning
35:39
at at 4B parameters that folks can use if they're interested and like you mentioned we have you know different um
35:46
optimized versions as well for example for Windows which is you know handled by the uh by the Windows team and um and
35:53
yeah and um like you mentioned they are we are actively working with them they
35:58
are working on quantized versions of the model as well um for inference and a lot
36:04
of Laura fine-tuning yep excellent and again lots of resources in the FI
36:09
cookbook to cover the whole FER family of models so yeah lots of lots of
Wrap-Up & Upcoming Sessions
36:15
resources lots of information and again you know we will be having a further discussion on Thursday in the discord
36:21
channel so our next session next week will be with the AI toolkit team we've talked a little bit around AI toolkit
36:27
and how it can be used for development and for agent building and also
36:32
fine-tuned models so Leo Yao from the f from the AI toolkit team will be here
36:38
with us next week and the host will be April so April will be hosting next week and then on Thursday we've got Moan back
36:45
and we're going to be talking much more detail around the five model so please do join us on the Discord channel we'll
36:53
be there we're going to have 30 minutes it's gone from 2:00 Eastern time um on
36:58
Thursday Thursday not Fridays this week and we will be talking more detail more
37:03
depth so please do ask your questions we will recording questions today from anything that we've missed they'll be
37:10
going on to both the Discord channel and the GitHub discussion channel again
37:15
please ask your questions and bring them to the session on Thursday and we hope to see you there
37:21
so thank you to our guests today it's been a great pleasure in hosting this series and thank you for knitter being
37:26
in the background here's some QR codes if you want to watch this content on demand if you want to join our AMAs
37:33
which are typically on Friday just Thursday this week and if you want to find a recap of what we discussed today
37:39
we do have that posted onto the forum so there's the QR codes for you to utilize
37:45
and hopefully enjoy Modern Monday so we hope to see you all on Thursday so huge
37:50
thank you thanks Lee and thanks everyone for listening in