* Architecture is the orchestration of practices that generate systemic support for thinking well together about software systems 
* Decentralized and participatory architecture decision making for stewarding the evolution of software intensive systems
* Architecture needs both "decentralized deciding" and "fast feedback at scale" (Team Topologies)
* Decentralized governance was one of the original characteristics of microservices
	* How to empower teams
* A book that focuses on fundamental change agents - people and culture - enabling teams and organizations to evolve software architectures in a safe and inclusive way
* Only when people work out their designs will there be necessary motivation, responsibility, commitment (is this true?)
* Both scaling and democratizing software architecture

Foreword

Changes in the last 20 years - core trend is moving from centralized control to decentralized ownership - power, responsibility, decision-making have moved from a few managers or committees to the teams doing the work
	Agile: From prescribed plan to team-led iteration
	Before (waterfall): a central project manager/business analyst would write a detailed months long plan
	Agile - the team is given a goal and works with a product owner to decide how to build it - the team self organizes, choosing what to work on during a sprint, how to break down tasks, how to solve technical challenges
	DevOps: Before - dev wrote code and threw it to an independent operations team - ops decided how to deploy, monitor, support it - if something  broke, ops fixed it or blamed dev - dev had no access or responsibility for the live system
	DevOps - the same team that writes the code also deploys it, monitors it, fixes it when it breaks - they own the full lifecycle
	-> this resulted in decentralized control of the production environment - every team now has the independence to release their own code and support theire own systems
	Project to Product - from temporary initiative to persistent ownership - A project is temporary - once software shipped, the team disbanded - a separate run team often maintained it - the business need was defined by a project sponsor, not the builders
	After - Product - the team is permanent and aligned with a business capability - they are responsible for the product's outcomes - like customer satisfaction and business value - decentralized responsibility for business value, not just technical tasks

Tradeoff: The old centralized model was slower but offered consistency and predictability
New decentralized model - faster/more empowering, but requires strong guardrails - shared platform services (Kubernetes, CI/CD pieplines, internal developer portals (Backstage), clear security/compliance standards
	-> previous, the shared purpose was simple/temporary - deliver a specific project on time and on budget 
	-> after (multiple purposes - product, platform, business) - right now there's a set of enforceable technical and financial boudnaries, but outside of them central authority still intervenes - and purpose is often fragmented by competing executive agendas, quarterly earnings pressure - platform teams and security are the new central planners
DevOPs is just an adaptation to centralized political and financial power (though I think centralization is a shorthand for exploitation, lack of opportunity, lack of autonomy etc)
And the tools are still owned by AWS, Azure, Google Cloud (technofeudalism lol - decentralized teams can't build its own chip fabs, undersea cablees, data centres). Furthermore these workers still work for salary and don't really own the equity

* Previously architects worked in a separate team, designing architectures for whole systems, setting standards, choosing which database, programming language, deployment mechanism to use
* By making architecture just something people in senior engineering roles do there can be a wide divergence in approaches
* The approach here: teams have autonomy to make architectural decisions but they have to seek advice from people affected by the choice they make and by supposed experts
* This process can shape the culture we need, moving towards an organization that optimizes for learning, autonomy and a fast flow of value - involving power sharing and deciding who is accountable
* Trusting people and allowing them to make choices where they have more expertise
* Blending of roles - the highest performance team, supported by the most collaborative architects - never seemed to be adversely affected by the complexity of architectures they were building and running - the blending of roles meant it felt like almost everyone was architecting
* In the lowest performing teams there was rarely a lack of technical skill - these failing teams lacked a two way relationship with architecture - often hindered by arms length architects and heavily guarded designs and artifacts
* Software has potential but this power is squandered, manifesting as complexity, rigidity, expense, waste
* Quality software reflects a team's collective mindset and mental models, which are deeply influenced by the reality of systems running in the wild
* Book is aimed at developers trying to take steps into architectural accountability and architects learning to add facilitation skills to their repertoire
* A wide variety of architects: software, domain, solution, business, system, principal engieners, enterprise architects, IT, chief architects etc
	* architects can be within teams or across teams (systems architects - across product suites) - architecture across the entire organization - focus ranges across all technology systems in an organization, not just one built in house


--
Chapter 2 - To Practice Architecture is to Decide

* To practice software (and to build anything probably) is full of decisions. You need to decide how you want something to be structured, how you want a process to work for that something, so forth. You need to decide if your team should use resources from a third party such as an open source library.
* These decisions reflect the power structures and feedback loops that got them there.
* All architectural decisions are technical decisions. 
* Types of architectural decisions include: how to split a module and what the boundaries will be, who owns what services, format everyone uses to write their logs and where these logs are sent for collection, how to integrate with a new third party API, how to expose functionality or data via an API or message queue, testing frameworks to use etc.
* Non architectural decisions include - which IDE developers use, which customer segments are targeted, pair programming on user stories, naming conventions, testing libraries
* An architectural decision is significant based on three criteria (dependencies, interfaces, construction techniques) and the magnitude of the impact is reliably predictable
	* If a completely new dependency is added or if you upgrade by a major version with the same vendor, or if there is a complete vendor change. A new API to the interface, a new cnostruciton technique. Placement of function (where some logic or responsibility for something is located), the decision to start/stop using a design pattern or higher level architectural pattern.
* Up until the architectural decisions are reflected in the deployed software, they aren't decisions at all - they are aspirations, the code is just a collection of schematics - getting architecture into production as rapidly as possible
* Product management/business also affect architectural decisions 

Chapter 3: Decisions at Scale
* What are the standard approaches to decisions at scale and the characteristics of an 'ideal' postrevolutinoary process?
* A generic decision process that applies to all decisions and that involve more than one individual?
* Stage 1: Decision Required, Stage 2: The Act of Deciding (option discovery, crafting, assessment, selecting/communication) - this also involves assessing the situation, past attempts, stakeholders, constraints
* Software architecture falls into the realm of wicket problems
* Where does the power balance lie in decision processes - they lie with the decision taker because they will select the option that will be progressed and reject those that will not - for the power to be exercised, options have to be made - a great deal of effort is required to come up with one or more of the options - if a new path is being forged and standard approaches and patterns won't cut it, this can be hard, creative work (types of option making - unchartered territory, well known solutions to enumerate, where a decision's significance is missed and only the most obvious option is considered)
* Often in the world of traditional software architecture, where option making and decision taking power rests with architects, development teams frequently only witness architects taking decisions or even worse hear about them second hand - this is worst in the ivory tower.  Often the majority of option making is unspoken and unshared, or overly bureaucratic, or both. 
* Once other people enter the picture you have to consider things like how other people are affected by success or failure or whether they need some convincing. You also have to bear in mind how failure affects timescale, who needs to be involved with implementation and what they need to know. 
* Approaches fall into two categories:
	* Autocratic
	* Delegation
	* Consultative
* Decentralized decision processes
	* Consent
	* Democratic
	* Consensus

In an autocratic decision process, there is a single option maker/decision taker and a group that implements the decision, and so sharing the decision here is vitally important
An example of an autocratic decision is where a new chief architect joins a startup and decides after no consultation with others that the company will move from Amazon to Azure for their cloud services
	this can be fast for individual decisions and sometimes powerful but also disastrous. Sometimes it can be poorly implemented and slow overall as all decisions go through a single person, making them a bottleneck.
	Delegation - a variant of the autocratic method - the autocrat delegates their decision to someone within a wider group who is better placed to make options, take the decision and share it - this method is marginally slower and can lead to better implementations but is still a potential bottleneck as the number of people doing deciding remains small
	Consultative decision process - here the decision taker is the same person as in the autocratic method but now they actively go to a group of their choosing and seek inputs during the option-making stage
		The autocrat is not obliged to listen to any of the consultee's inputs but can potentially benefit from them
		This method is slower than both the autocratic and delegation approaches but can benefit from the expertise of a wider group
		But whole groups with valid expertise can be shut out completely, never even asked for input because the decision taker selects who to consult and who to ignore

* Decentralized decision processes
	* Consent process - the option maker and decision taker are still the same person, but once the decision is taken, others in a far wider group can block it in the form of a veto - paramount objection
	* This is a significant shift of power but not a complete one - vetoers do not have the power to directly make the options or take the decision but can block progress after that 
	* This is open to abuse by those who might deploy the veto with no intention of withdrawing until they get exactly what they want. But on the upside, the decision sharing element is unnecessary or greatly reduced
	* Democratic decision process - this refers to the Athenian ideal of direct democracy, not representative democracy. In a representative democracy, individuals cast votes to select someone who will represent them in the decision making process - how a lot of parliaments work. In a direct democracy, individuals cast votes or some other means to directly indicate their preference from a selection of options put in front of them - there might even be options to not vote at all or indicate ranked preference. The option that gains a majority of votes is the one selected. 
		* This can create a tyranny of the majority problem even though the minority might have valid objections. The ignored minority may also feel little to no ownership of the selected option and is therefore disinclined to implement it.
	* Consensus decision process - this seeks to resolve the inherent issues highlighted in the democratic approach  - this involves everyone in both stages of the decision process, both in the making of options and in the taking of decision of which option to select - this can level out power across everyone in the group and provide the possibility for everyone to be involved and listened to at both stages - this however can take forever to arrive at a conclusion, and there is significant danger that the conclusion reached will be a catalog of the lowest common denominator
	* This also requires everyone to feel equally able to be involved and to share their viewpoints and opinions - often people who decide are unaware of who they are excluding - they commonly conclude those who don't participate don't have anything to contribute or will agree with the opinions of those who participate
	* Avoidant approach - what happens if we don't do anything?
* With standard processes, there's a tradeoff between response speed and centralization.
* What makes a decision method fast to respond?
	* In the consent decision process, a group rather than an individual has influence on decision making, which can play out in a number of ways.
	* Consent decisions can be fast - when trust in the option maker and decision taker is high, consent from teams can sometimes be preassumed to be given in all circumstances - vetoes cause a slower process
* Decentralization might not be a good thing in itself - but it can also bring more minds to bear on an increasing number of problems simultaneously
* In The Age of Surveillance Capitalism, Zuboff discusses how while it's important to think about who is involved in the making and taking of decisions, it's equally important to think about who initiates the decision process and selects who is involved in it 
	* Who decides? And Who decides who decides? 
	* The key factor in a decision process's decentralization with regard to decision rights is the number of people who are de facto entitled to initiate and contribute to the taking of decisions
	* The greater the number and deeper the involvement, the greater the decentralization

* Parameters a fast and decentralized process would meet:
	* 1. It must involve the appropriate people while keeping the number as small as possible
	* 2. It must optimize the entitlement to initialize, make options, take decisions
	* 3. It should prioritize trust so that people feel the need to involve themselves in decisions where they have a stake
	* 4. It should minimize the need for explicit sharing 

Chapter 4; The Architecture Advice Process

* Decentralized and fast - the architecture advice process is a simple yet powerful approach to deciding that is both decentralized and fast - how this process meets all four requirements for a modern decision process by involving the right number of people, optimizing the entitlement to initiate decisions, prioritizing trust, minimizing the need to communicate decisions.
* Widespread impact the advice process can have on software and your organization's culture - not only removing blockers and increasing feedback but also promoting healthy equitable communication
* Is there a way to make architecture less the responsibilities associated with a job title and more about architecture as a collective practice? Might there be an alternative approach that could take architects out of the critical but stressful decision path while still maintaining the practice of architecture at the core. A decision process that locates decisions in the right place, involving as few decision takers as possible, while allowing many different individual to make and then take those decisions.
* In the architecture advice process, there is a single rule: anyone (a development team member of someone playing a cross-team architecture role) can take (select a decision option) and communicate an architectural decision as long as during the option-making stage they seek advice from - everyone who will be meaningfully affected by the decision and People who have expertise in the area in which the decisions is being taken.

* The key factor in a decision's response speed is the number of people who either contribute directly to the taking of a decision or can object to that decision after it is taken. The lower the number, the faster the optimal response speed
* In the advice process, the number of people involved in and accountable for the taking of the decision is one/one-team-sized group, and the number of people who can object is zero
* The greater the number of "meaningfully affected parties", the more people decision takers are obliged to seek advice from. This actually sets up a valuable reinforcement dynamic - to make fast decisions, teams will look to reduce the number of affected parties they must turn to for advice 
* More sharply define a decision/reduce or remove its impact on others - continually validate good system boundaries, rewards, decoupling, reducing the scope of the decision.
	* The greater the number of meaningfully affected parties, the more people decision takers are obliged to seek advice from - during the preceding option-making step of the process, those driving the decision are seeking advice -importantly, not permission from those affected by it and those with applicable expertise
	* The number of meaningfully affected parties, the more people decision takers are obliged to seek advice - to reduce the number of affected parties, need to sharply decision to reduce/remove the impact - teams need to continually validate good system boundaries, reward decoupling, reducing the scope of decisions
	* Decision takers also no longer need to convince experts of the reasons for a decision, so a rich conversation can take place from the beginning, with the sole goal of seeking and sharing knowledge and experience
	* With the advice process, those who make and take the decision are also the ones implementing it - the sharing step is simply getting back to the affected parties and experts and letting them know what the decision taken was - this is simpler because everyone was previously involved 
* In contrast to the architect approach, the advice process locates the center around whoever needs it, whenever it needs to be there - meeting the need for optimal decentralization 
	* The downside of the most decentralized decision processes (such as democratic or consensus) is that they are always maximally decentralized - everyone is always entitled to contribute to the taking of every decision - consequently, even in circumstances where everyone is aligned and on the same page with regard to consensus, simply letting everyone be heard on every topic can be at best long-winded - this happens because everyone feels obliged to participate, contributing what they can to both the making of the options and taking of the decision
		* If they stop participating, they will be seen to not care or not know enough to offer opinions - at the extremes, what you find is while everyone has an opinion, no one takes decisions
			* An advice process will flip this - there is now one decision taker, but that decision taker arises from the collective, wherever and whenever a decision is required. With the advice process, no one needs to seek permission to initiate this. The answer re who decides and who decides who decides is "whoever feels the need to"
			* A social contract - the decider (person who initiates the process because they have a need for a decision) and those offering the advice - the people who represent the affected parties and those with expertise
		* Everyone in the sociotechincal system, those building and running the software, could be called on to play either of these roles
			* what one wants for oneself, one needs to be able to offers onself
			* To play well, need others to trust me and I need to trust them
			* this trust can be built up by involving appropriate people in my decision via their advice by listening to and understanding that advice properly, taking advice into account in the options one shapes and selects when taking the decision, ensuring the right people know about a taken decision by sharing it appropriately
			* Trust is a big topic
		* Not everyone welcomes this advice process idea - not everyone feels as ready, willing, able to take on the responsibility and accountability that the advice process entails
			* complexity and emergence - adopting the advice process can be transformative for both the creations and the social dynamics of the team that build and run them
	* two tales of how a development team member and an architect might follow this process
		* Tale 1: team is in need of a solution that lets them disable their unfinished code while pushing directly to trunk and deploying regularly to production -> to do so, they need a significant architectural change involving some form of release toggle 
			* The team has a lot of local, specific, up to the minute detail on their need. They know about running services, infrastructure, backlog, state of existing pipelines, testing strategies, the skills they have as a group and what they are and aren't comfortable with.
			* People to seek advice from: peers in delivery teams whose lives would be changed as a consequence of release toggles being implemented - not hard to sit and think - who would have extra work to do as a result of us implementing the decision/whose freedom to act/flexibility to make changes unimpeded might be curtailed as a result of this -> important that the team thought about who might be impacted and spoke to them
			* These teams could provide a useful "outside but still here and now perspective on the proposal" - providing valuable context and detail
			* The deciding team wasn't being reckless or uncompassionate here - as soon as they were reminded of this fact, they realized just how problematic their original proposed change would be. They might get their features to production faster but these other teams were building services for the same end users, just for later stages of the journey.\
			* Putting yourself in everyone's shoes is difficult to do - someone having something removed from them is far more alert to the fact than someone who might be doing the removing
			* In many circumstances, "experience" translates, to "past experience an/or wider horizons on the decision"
			* Not all of the advice a decider receives may change their planned approach, but every piece does contribute toward making them aware of the full scope and impact of their pending decision - as well as learning about different features and their uses, past experiences of different members of the organization and thought processes, teams can also learn about their own limits and build human networks across the organization.
			* Who raises questions or brings up the need for cross cutting decisions and decisions that arise from the nature and evolution of the system as a whole? These decisions inevitably come from people playing roles outside of any single delivery team
				* we traditionally think of this as architecture
				* Sometiems what is a reliable and useful tool can become a liability - this isn't an unusual evolution - "what the workflow subsystem was doing now was far outstretching the original design goals of the team when they first developed it - it's no wonder then that things were beginning to creak at the seams" - "when the system was originally designed, noone thought user journeys would get so complex" - the signs that the architecture was the problem rather than a lack of testing or low code quality first became clear to those in architecture roles - they considered matters across the entire system and thus could aggregate individual instances of failure, while teams were quite likely aware of only the ones that affected them, so architects could see a possible pattern emerging - the diagnosis was done via 1) establishing the current design of the workflow service as it existed in the code 2) find out what each of the teams was trying to use the workflow service for - it turned out the code was clean and the design was explicit and well tested - the architect also uncovered this with a second line of investigation backed up - there were some usage patterns being supported




