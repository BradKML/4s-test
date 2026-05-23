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