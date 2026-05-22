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
* 