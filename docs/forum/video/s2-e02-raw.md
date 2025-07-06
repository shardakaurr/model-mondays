0:01
hello everyone and thank you for joining us for today's session my name is Danny and I'm the event planner for the New
0:07
York Reactor Space before we start I have a few things to go over please take a moment to review our code of conduct
0:13
we seek to provide a respectful environment for both our audience and presenters we encourage engagement in
0:19
the chat but please be mindful of your commentary remain professional and on topic useful links will be shared in the
0:26
chat the session is recorded and will be available on demand in 24 to 48 hours on
0:32
the Microsoft Reactor YouTube channel which brings us to today's session it
0:37
will run for approximately 30 minutes with time for questions throughout i will now turn it over to our speaker for
0:44
introductions hi hi hi hello everyone my name is Nitan
0:51
Arsaman and I'm on the AIDS team at Microsoft and today I'll be joined by my colleagues uh Charma and Dan as we talk
0:59
about a topic that's very very interesting to all of you model context protocol but before we dive in uh just a
1:05
quick runoff show we usually start the show off with like a highlight segment where we cover the top news from the
1:10
past week before we dive into the spotlight so let me just give you a couple of links to look at uh the first
1:17
one is model Monday/isord all the things we talk about that's our community so feel free to join us there after this
1:23
event if you have questions and we will also host an AMA there on Fridays we'll talk about it later and there is a
1:30
GitHub discussions forum we will have a card for this uh particular episode there where you can put your questions
1:35
on we're also trying something new so feel free to grab these links if you've missed an episode we actually have a
1:42
Microsoft Student Learn Ambassador uh writing recaps of each uh week's uh episodes that you can find on Tech
1:48
Community and Dev.2 but right now I want to start off with our weekly highlight segment so I think
1:55
our uh my colleague Charla will probably be here in just a bit but she did record the five things that you need to know
2:02
happened last week so without further ado let's roll tape and see what's new in Azure AI Foundry this week
2:09
thank you Nita and everyone welcome back to Model Monday's highlights in this
2:15
week's highlight we are diving into new models smarter security and infrastructure updates that are shaping
2:22
the future of Genai on Azure um so let's get into it and uh as usual on every
2:28
update uh there is a QR code which links to either the blog or the model card so please take a screenshot of the QR code
2:36
um so the first update is um that coher models are now available on manage
2:41
compute in foundry so what is managed compute managed compute is where you can bring in your own Azure infrastructure
2:48
and deploy uh and use that infrastructure kod for deploying these uh models on Azure so this means you can
2:56
deploy like very command light enterprise ready language models with just a few clicks but it's still backed
3:02
by Microsoft SLAs and Azure enterprise security stack so if think of like you
3:08
can achieve low latency easy scalability and you still have robust guardrails so which is ideal for production grade uh
3:15
rag use cases so now it's easier than ever to go from idea to inference on
3:21
your own um infrastructure like uh Azure infrastructure securely and reliably now
3:27
the next update is on um prom shields so with AI apps going mainstream and
3:33
security is becoming non-negotiable and just a few weeks back we rolled out Prom Shields a new runtime layer that helps
3:40
detect and block prompt injection attacks now combining that with Azure AI content safety which is now featuring
3:47
image and multimodal filtering you've got a very comprehensive AI firewall so
3:52
whether it's jailbreak attempts or offensive outputs you're protected end to end while still delivering fast
3:59
creative AI experiences now we are moving on to some model announcements uh we are excited to say
4:06
that OpenAI's 03 pro model is now available in Azure AI foundry it
4:12
delivers GPT4 turbo level performance with faster throughput and lower cost
4:17
and it's optimized for enterprise that are scaling AI across orgs so if you've been pushing your GPT4 and hitting
4:25
capacity ceilings or latency limits 03 Pro gives you serious firepower with
4:30
better economics and seamless Azure integration now the next in the line of model
4:38
launches is our Codex Mini so um any developer who's building CLI tools and
4:45
fast feedback workflows a Codex Mini is for you it's a small scalable code
4:51
generation model purpose-built for command line scenarios think shell scripts quick command scaffolds
4:57
automation helpers all with low latency and minimal footprint and it's perfect
5:02
for embedding into your local developer environments or using as a lowcost
5:07
high-speed alternative for repetitive coding tasks then last but not the least the model u
5:15
model context protocol just MCP just got a serious upgrade with models and at
5:21
build in May uh we released u what uh support for model based access control
5:28
better inference routing and integration with model usage telemetry for MCPS
5:33
Azure AI foundry MCPS and this improves observable observability governance and
5:39
performance for scale AI deployments so if you're running multimodel applications or supporting regulated
5:45
workloads the new MCP makes your infrastructure smarter and more secure
5:50
so that's a wrap for this week's model Mondays from frictionless coherent deployments to turbocharged OpenAI
5:57
models and nextG security Azure AI foundry is evolving fast um and we are
6:03
bringing all that information to you uh so see you again next week with more
6:08
highlights and now I'll pass it on to Nita to get into the next section of our
6:16
episode thank you hey Charila um hopefully you're here but
6:24
this is actually perfect like the way you set it up for this week so um for what it's worth uh couple of things we
6:30
are talking MCP this week but in that last slide Charmela pointed out this work on MCP servers we will have the
6:36
folks from that particular blog post coming uh to speak to us in a couple of episodes from now look for the research
6:42
and innovation uh episode but in the meantime we are now on to our weekly spotlight section where we will put a
6:49
spotlight with a 15minute deep dive into our topic and I'm so so excited to have
6:55
Dan Demarski with us today so hello Dan hello hello i'm excited to be here thank
7:00
you for having me yes so I want to first set you up so if you haven't seen Den uh he's been at every MCP event in the past
7:07
week he's been super busy he was at Build then at MCP Dev Summit then AI engineer conference so Den two things
7:14
what is MCP and why should people care and then what are you going to talk about today and then we can go over to the deep dive cool yeah so I'll I'll put
7:21
it this way like for for uh all the excitement that exists around like LLMs AI we know that the bulk of the value
7:30
actually is us you know locked behind the scenes of different like APIs and different systems right like your
7:37
dropboxes and your box and sharepoint and salesforce and the question always comes to like well if I have my AI
7:43
systems how do I connect to all this data so MCP is or model context protocol
7:49
is quite literally literally like if you reverse the the name that's exactly what
7:55
it does it's protocol to provide context to models that's what it is it's USBC
8:00
for LLMs and it makes it very easy uh to connect uh all these different data
8:06
sources to LLM to make sure that they can actually reason on it and provide some kind of insights or extract the
8:13
data and act on it and uh today we're going to be talking about some of the authentication authorization because
8:19
guess what to connect all those data sources you kind of need to have some credentials and those credentials are
8:25
coming from a standard and we have that standard and uh just recently by the way
8:31
the spec revved to a new iteration I believe it's 20250618
8:36
that actually has the authorization specification baked in in its current kind of the the current format it's
8:43
great and I'm excited to to talk about it and by the way when you'll see the talk you'll see me refer to it as kind
8:48
of the draft spec it's no longer draft it's production starting next week or I mean sorry last week and I was I think
8:55
we're going to roll tape but I'll just say one other thing i believe VS Code's recent release is the first one to have the whole MCP is that right absolutely
9:02
yep vs Code is fully compliant with the MCP spec which is super exciting yeah so we'll have all those links for you right
9:07
after this but now we should roll tape and get the 15-minute deep dive into MCP hey folks I am Dan Deamarski i'm a
9:14
principal product engineer at Microsoft and I'm a member of the MCP steering committee and today I'm going to be talking about building protected MCP
9:20
servers because as MCP is gaining traction and a lot of folks are starting to host servers remotely in the cloud or
9:26
you know any other provider they care about making sure that those servers are protected from unauthorized access so
9:32
that's what we're going to be talking about today i'm going to switch to my slides here and one of the things I want
9:38
to call out is that what we're going to be talking today is really applicable to remote servers because we know that
9:44
anything that's hosted in the cloud is not necessarily designed to be open to the broad public and that is especially
9:50
critical if your server is running uh in a way that connects to other APIs that
9:55
require user authorization and a lot of servers are like that if you're hosting some business productivity MCP server
10:01
that needs to connect to Dropbox or Salesforce or any other service chances are that those APIs require some kind of
10:08
user context that is important to have and you want to make sure that you're gating the MCB server before you give
10:14
access to those downstream APIs now this is important for remote servers it's not
10:19
as important for local servers because a local server or local MCP server is just
10:24
a binary that runs on the box so if you can use npx you might be using uh one of
10:30
the Python servers it doesn't really matter but it's just a binary that has access to a bunch of other libraries and
10:36
ways to acquire the user context directly on the machine without interacting with any kind of standard
10:42
authorization protocol if you will now why is this important well first of all
10:47
if you're interacting with downstream APIs if your server is the one that acts as the proxy to those APIs that means
10:54
that that API needs some kind of user context to be able to return the right data what that means in practice is that
11:01
you need to authorize a given user or a given service account if your server is acting on behalf of itself against that
11:09
API and what that also means is that that user context needs to be acquired somehow in the first place you're
11:15
dealing with that cold boot problem of having that initial bootstrap process of
11:21
getting the credentials transforming them into let's say something like a token and then passing it to that API
11:26
now the API also controls which users have access to it now there is an
11:33
important distinction here we're not talking about just kind of a broad definition of user access but more of the API can decide what level of access
11:40
it can grant to what users or what roles and groups and we're getting in kind of the world of policy definitions but it's
11:46
a bit of a you know scope overreach here but the idea is that the API itself can
11:52
determine who has access to what level of you know information that it exposes
11:58
the API also connect differently depending on the context of the users they're requesting information so if you
12:04
have somebody that is an admin and they request user context they might get a lot of information versus somebody that
12:09
is just a contributor might get a very restricted set of information about the exact same user using the exact same API
12:15
call so this context is very very important and it's especially important as we start exposing these APIs to LLMs
12:23
with the help of MCP servers now I did call out something that for local MCP
12:28
servers this is not as applicable so why is that well first of all local servers
12:33
work on the box with the context of the user that can be provided directly to the application for example if I'm
12:40
running this on a Windows machine I might have a Microsoft account already connected to my Windows machine so my
12:46
local MCP server can use built-in APIs to just request that user context and
12:52
authorize a given user to whatever API needs to invoke later on downstream i'm
12:59
not necessarily authorizing myself to use the MCP server it's more of the server actually needs to access some
13:05
downstream APIs and it gets the user context from me now the this also means that the authorization can be done in
13:11
any way that is necessary you don't need to use OOTH you just need to use a library that knows how to talk to whatever downstream API the local server
13:18
is talking to which in practice means that it opens the door for literally any
13:23
implementation because it's a local binary that means you can code in any approach that you really want and any
13:29
approach that the API downstream requires there is of course special cases like if you have an MCP server
13:35
that runs locally uh that is shared on the same machine between multiple users like in remote desktop scenarios but
13:41
that's a bit out of scope for for this particular conversation uh and that does require some work but it's left right
13:47
now as an implementation detail to those that manage and build MCP servers that
13:52
run on the box or the local MCP servers so I want to talk about the two
13:58
specifications here that we have so you might have noticed that in the MCB protocol spec there is a authorization
14:05
spec that's been authored or released on March 26 2025 this year that
14:11
authorization spec actually required customers or developers or implementers of MCP servers to go ahead and implement
14:18
an authorization server it's a component that is responsible for essentially minting tokens based on user context
14:25
that is being kind of requested and received by the client uh which is complicated not a lot of folks want to
14:31
do that from scratch and it requires a level of security expertise that not a lot of folks even want to have and we'll
14:37
we'll talk about that shortly um that also means that in this implementation that server the MCP server acting also
14:44
as the authorization server would need to keep track of token issuance validate those tokens make sure that whatever it
14:51
receives is correctly structured and formatted for this to be properly implemented you would kind of need to be
14:57
an oath expert and not everybody wants to be an oath expert so we worked with a
15:03
community of security experts we worked with folks at Octa AWS uh uh Dcope and
15:08
many many others to make sure that we implement a draft specification that does this clean separation between the
15:16
MCP server also known as the resource server and the authorization server what this means in practice is that you no
15:23
longer need to implement this from scratch so if you're somebody that has an MCP server that deals with I don't
15:29
know let's say Salesforce data you don't actually need to implement any of the custom authorization logic to mint
15:36
Salesforce tokens on the server or to mint tokens that you can then map to some Salesforce tokens instead if you're
15:44
Salesforce and you're building an MCP server you can just make sure that you're correctly advertising what
15:50
authorization server using on the server and then the client the MCP client in this case is the one that jumps through
15:57
the hoops of acquiring a token going through the process and following standard OOTH procedures which by the way all of this is snapping to OOTH 2.1
16:05
so we're following the standards there's nothing super custom here it's literally the OOTH 2.1 protocol what this also
16:12
means is that the server itself is not going to be minting tokens the authorization server downstream the
16:19
actual you know usually provided by an identity provider like say octa or ozero or entry id is going to be the one
16:25
minting the tokens and then the server is only responsible for validating them uh also this means that the client now
16:31
is the one handling tokens directly and the server has very little to do other out of them make sure that the tokens that it receives are correct
16:38
i mentioned something that is crucial here and that is that most developers do not want to be security experts and they
16:45
really don't because for a lot of them the crux of the issue is I'm building an
16:51
MCP server to solve a very particular customer problem that's what I want to accomplish i don't really care about the
16:58
details of what's the structure of a JSON web token how to generate the
17:04
signature how to check the expiration date like a lot of these things are problems that were solved by existing
17:10
libraries by existing authorization servers by existing identity providers that handle a lot of the policy
17:15
conversations all of this is a solved problem so we wanted to make sure that developers have
17:21
a path to using existing tooling using existing conventions and focus on
17:26
solving the actual problem they care about which is implementing the MCP server instead of chasing little
17:33
security details that they have to implement for the server to work properly so this led us to build this
17:39
new authorization spec that I mentioned about that defines exactly this a lot of the components of the specification are
17:46
and by the way it's available publicly on the model context protocol website you can go and check it out uh it
17:51
captures a lot of the requirements and the gist of it is that the authorization server now is advertised in what's known
17:59
as a protected resource metadata document that is attached to the server what this means is that now developers
18:06
just implement this metadata and can point to an existing authorization server and just use that as their
18:13
gateway in a way to get tokens for use with their MCP server so there is no
18:21
need to implement anything from scratch you're completely absolved the responsibility if you are building a protect MCP server and you want to use
18:27
an existing off-the-shelf identity provider now the server also has a standard way to tell the client what
18:34
authorization server it uses which is the protected resource metadata document which can be either a JSON blob or it
18:40
can be a token and it follows the standard OT 2.1 conventions which means that if you're using any of the existing
18:47
libraries that do this you're off the hook you don't need to build anything
18:52
from scratch and by yourself again we're developer ergonomics here are very very
18:57
important the goal is to get you from zero to a protected MCP server as fast
19:02
as possible without having to be bogged down by a lot of these details that you might not even care about
19:09
on the client side the client now is going to be responsible for doing the token dance the token exchange and
19:15
making sure that the authorization code that it receives is actually exchanged for a token and then it passes a token
19:21
to the server the only responsibility that the server has in this context is to make sure that it looks at the token
19:27
ensures that the token was issued to it to the server which by the way very very important you got to make sure that you
19:33
validate tokens that your server receives it's not just about the server being the proxy because that's that's a
19:38
completely completely bad pattern to adopt uh the server needs to validate tokens and make sure that it's issued
19:44
for it you should not be doing token pass through and what this means in practice is that developers have very
19:50
little to actually implement you can again use off-the-shelf solutions just plug and play like a bunch of Lego
19:55
bricks and you're good to go your server is protected and there's plenty of identity providers
20:02
that you can actually use for your scenarios right like there's Entra ID there's Octa AWS Cognto
20:09
plenty of them and as long as you use one that supports standard OATH 2.1
20:14
conventions you're good now there's going to be some nuances of course around things like dynamic client registration which requires some level
20:22
of implementation and if different providers do not support it you'll need to implement this directly on your server but the bulk of the interaction
20:30
is now encapsulated on this authorization server side not the MCP server side which is extremely extremely
20:36
helpful for developers that want to build secure servers that they want to deploy to the cloud now let's think
20:45
about this a little bit and see like how does this actually work in practice how does this work if we take an example MCP
20:51
server an example MCP client and an authorization server for that I have this bit of a I want to call like a
20:57
flowchart if you will so we have an MCP client that its first step is requesting
21:03
data from the MCP server it just asks for some information it can be information about existing tools or any
21:09
other primitives that exist on kind of the MCP side of the world and then the server will respond back with a 401
21:16
unauthorized because the client did not attach any authorization context with an attached pointer to the PRM the
21:23
protected resource metadata document which in this case as I described can be a basically a JSON file that tells you
21:28
what the contents what the authorization server is and then what the client can
21:34
do with that pointer is go ahead and pull that JSON file that that PRM document that it needs to proceed with
21:41
that PRM document it's going to look pick an authorization server it's going to use the scopes that are declared
21:47
there and then it's going to complete the authorization flow because it's going to going to follow the discovery protocol to make sure that it connects
21:53
to the uh as the authorization server it's gonna understand what is a token
21:59
endpoint what is the authorized endpoint what is the register endpoint uh go through that flow you know if it needs
22:05
to register a client it's going to register a client and then the OT server is going to return tokens directly to the MCP client the server is not in the
22:11
loop here mcp client is going to be the one that's going to store you know cache the tokens and then pass them to the
22:18
server it's going to request data again with a token attached usually in the authorization header and then the server
22:23
is going to return the data back again very easy very streamlined like the process follows standard conventions
22:30
like I have here this very overly trivialized step that says complete flow but what that means is that it just
22:37
basically is going to go through the oath uh authorization code flow with Pixie PKC
22:44
um and it's just going to complete it get the tokens and be on its merry way that's kind of it the client is now
22:50
responsible for making sure that it's using proper tokens it's making sure that it's refreshing the tokens and the
22:55
server is absolved of a lot of lot of responsibility that it previously was
23:00
tasked with here's an example of what this PRM document looks like and here you can
23:06
very very clearly see that it's fundamentally not super complex to parse
23:13
there's a definition of the resource which is the MCP server in this context there's a definition of the list of
23:19
authorization servers that are supported it can be one or many and by the way the client in this context is going to be
23:25
the one responsible for picking which of them to choose uh bearer methods support
23:30
it that defines what exactly are the kind of the the authorization bear the bearer token methods that the uh
23:37
authorization server is capable of uh using and then the scopes that are
23:43
exposed to uh a particular client that they can use to then request authorization with that MCP server and a
23:50
pointer to some documentation and for any additional details I highly recommend going to the actual RFC
23:55
document that you'll see linked uh below in the description to see more like what other properties can be included because
24:01
this is not a complete example of a PRM document there could be more information there of course uh this is just a sample
24:07
to give you an idea of how it's structured and what the client would see to parse it if you want to have more
24:13
information about what we just talked about I highly highly highly recommend you check out the existing
24:18
specifications on the model context protocol website you have the current stable spec the 20250326
24:26
uh and you have the specification that is in draft that I talked about before
24:31
uh again very very helpful to compare them the draft one is going to be live
24:37
soon uh hopefully after this talk uh and that's going to be another revision of the protocol that's going to enable you
24:42
to do the PRM document all these nicities that we talked about uh and then not only should you read the specs
24:49
but you also should check out the security best practices document that you see at the bottom here because it
24:54
outlines some of the recommended approaches that you can use to make sure that your MCP server is secure that
25:01
you're not exposing data when you shouldn't and that you're properly controlling the token usage which again
25:08
I I I said it several times in this talk you should always validate your tokens because the worst thing you can possibly
25:15
do is accept a token on your server and then not check it and assume that just because you have a token that everything
25:20
is fine uh it's really not so this is it thank you so much for listening to me
25:26
talk about authorization in MCP if you have any questions do reach out my contact information is in the
25:32
description for this video i look forward to hearing comments and helping make the MCP ecosystem more secure thank
25:38
you all right um thanks so much Dan i think
25:45
that has been one of the most packed talks I have seen that was there was so many links of sharing on the chat um we
25:52
usually have like a five second delay so I'm going to encourage folks who are on the chat to please put your questions in
25:58
but uh before we go ahead I wanted to ask you um just you know is there a place that people can go and learn about
26:04
i know you have those three um links but is there a place they can go learn about security best practices for MCP yeah so
26:10
the the best place for that is literally going to the MCP website so if you go to modelcontextle.io IO there's a whole
26:15
section called security best practices and that's actually something that we're working with both security experts in
26:20
the industry as well as anthropic to make sure that we're properly documenting the flow uh as to how to
26:27
build MCP servers and clients that are inherently secure so highly highly recommend to go there and check it out
26:33
thank you and I'll keep an eye on uh for questions so if you're watching this chat please do uh I noticed someone basically so you have one conversion at
26:40
least uh I think Joel had basically said "I was reading about this new MCP security spec over the weekend i'm happy
26:45
to remove all the bear token code from my MCP servers." So yay uh but in that
26:51
context I was going to ask I remember you did a really good demo at the MCP Dev Summit so is there a place people
26:56
can go look at like a simple sample just to get a a kind of like an applied understanding of how to use that yeah so
27:02
there's we we'll share the links afterwards uh we are aggregating a whole bunch of them on GitHub the MCP car SDK
27:09
if you go to the GitHub repository for that has a pull request right now that we're finalizing with the whole authorization spec and once that is in
27:16
you'll actually have samples built in directly into the SDK and that's going to be applicable by the way to other SDKs as well so if you're using Python
27:22
TypeScript you know Go it's it's all going to it's going to come with time as we're we again last week the spec just
27:29
formalized so now we're getting getting it all lined up and if right now because of like you said the spec is just out
27:36
last week so what can people expect going forward in terms of the security aspect of it but also the broader MCP
27:42
roadmap if you have any insights yeah of course so I think that the main thing is that the clients and servers will now
27:48
start adopting the patterns that we've documented in the specification so uh we talked about VS code being fully compliant with the spec but VS Code is
27:54
just one MCP client like we expect that you know cloud code uh and a whole bunch of other uh MCP clients that are out
28:01
there to start kind of snapping to this so if you're building MCP servers things should just work like no matter where
28:07
you plug it in which is kind of the beauty of MCP right like that's the whole point is I want to grab the server
28:12
and just plug it in in any of my existing infrastructure and things will just magically work i don't need to do anything custom in terms of integrations
28:20
so we had a question on the chat from someone said "How do I mitigate security risk in an MCP implementation what best
28:25
practices should I follow?" Yeah so uh as I mentioned the security best practices document like is the place to
28:32
get started i'd say like go there check it out the links are going to be available um it's literally on the MCP
28:38
website uh there's uh more things that we're working on integrating uh through
28:43
a variety of different channels of course some Microsoft some are more generic in the industry that's going to be uh again documented in the next
28:50
couple of weeks but I'd say like the security best practices doc is the starting point uh and I think like uh I
28:56
think my slides are frozen but hang on a second i think we're almost at time but I wanted to There we go let me quickly
29:03
just give you a couple of things next week we're going to have someone from Microsoft research talking about SLMs and reasoning but I want you to be aware
29:10
of the Foundry of Foundry Friday AMA so thank you so much Den i know he had to
29:15
drop for a meeting but if you have questions Den will be coming to our Azure AI Foundry Discord on Friday so
29:22
grab that link and join us there we'll have 30 minutes to kind of talk through all of this all the links he talked
29:27
about will be in the chat but also in that uh post that you'll see for the forum that you see right there so you
29:33
can kind of follow up on this and last but not least I'll leave you with these three CTAs so if you found this series
29:40
useful uh don't forget you can register for the entire upcoming series we've got I think this is the second of 12
29:45
episodes in season 2 so you can go to model Mondays to pre-register for the
29:51
next I think four episodes uh join the Discord we share a lot of information in there there is a model Monday's channel
29:57
where I will share these slides and all the information Den put out and most importantly if you go to that forum link
30:03
at the end it lists all the AMAs every Friday on Azure AI Discord this Friday
30:09
the focus will be on MCP so I can't wait to see you all there uh thank you so much for joining us and uh happy Mondays
30:17
we'll see you on Friday