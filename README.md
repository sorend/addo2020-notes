
# All Day Devops 2020 notes


## Keynotes

### Ask me anything keynote: CI/CD
(Cloudbees + HSBC engineers)

* CI/CD: Automation is about removing friction. Possiblity to go through a process as fast as possible.
* Business perspective: Cultural shift. Continuous everything, we want to do our best.
* Going faster means breaking less, smaller releases. Business is impacted of going faster.
* Regulatory impact. Controls are codified and deploys together with code. Engineers don't think about it, it just happens.
* Complete views of what is met and what is not met automatically all the time.
* Goal centric approach over tools centric approach.
* Principles for CD: Break pieces down in small pieces. Release + monitor small parts + automated roll-back + gradual roll-outs.
* How do you think about releasing code?
* How to convince upper management? Customer value stream + reduce turmoil.
* Champions are required, to drive progress.

* Set a goal for yourself. Start small. Measure everything. You have to do it. Build community around it. Make it public (advertise it).


## Sessions

### Are we really moving faster? How visualizing flow changed the way we work
(Roman Pickl, Elektrobit)

* Are we really moving faster?  AFTER the journey to K8s with monitoring.
* Problem: Delivering value
* Impediments: Long dev cycles, high workloads, changing priorities, decreasing morale
* Fast physical feedback and visibility of problems
* Clear feedback signals.
* Ambient awareness: Extreme feedback devices (physical feedback devices in highly visible locations)
* Provoke conversation, show nothing to hide. Traces back to your production system.
* Weekly status meeting regarding Operations.
* "We shape our buildings, and afterwards our building shape us".
* Dashboard metrics: Open pull requests, open support requests, tickets in progress, tickets done but not released.
* Confluence does not provide value until developer sees them.
* High variability in design domain, low variability in delivery domain
* Flow framework: Flow load (items worked on), Flow time (time through valuestream), Flow efficiency (actively worked on), Flow velocity (number done), Flow distribution (allocation in specific state) -> Flow-board + happiness + quality :-)
* Separate Features vs bugfix.
* Local optimization and the urgency paradox (measure the full value-stream, not only the development section where things are pushed to go fast).
* Value vs non-value adding activities. Goal eliminate, optimize. Use value-stream mapping technique.

### DevOps in a highly regulated environment - Aiming high like a Unicorn in skates
(Marc Cluet, Ukon Cherry Ltd)

* Governance, risk and control: Approval process crafted to ensure compliance.
* All data tightly classified and controlled. Long process to ensure we don't do anything silly (design/technical/regulatory forums).
* Challenges: No confident in Agile/Devops. Upskilling required. Maintain levels of controls. Increase speed of innovation.
* We still want to reap benefits of cloud.
* DevOps about people, process and tools. Each impact/creates tension to the others.
* People: Experts help accelerate.
* Change through metrics: DORA.
* Create CCoE
* Agile governance: Controls are business requirements, need to ensure we accelerate controls.
* Continuous governance: Controls as code, governance as code, policy as code.
* Tooling: Open Policy Agent, Hashicorp Sentinel.
* Shift left security: Zero trust security in cloud, code security checks in pipeline, dependency checks in pipeline, external dependencies scanned.
* Platform security: Platform releases at intervals, pentest of any new platform release, everybody required to be on new platform, anything killing for more than 3 months killed and refreshed.
* Tools: Everything must be CI. Deployment also auditable that needs to align with governance.
* Tools: Everything is an API. Follow twelve-factor app rules. Restful interfaces always secured. Short lived sessions.
* It's possible for big/regulated to transform to Agile+Devops
* Takes time. Need focus on people first, then process+tools. Use technology as catalyst for change. Upskill people for happiness and retention.





### Bullet-Proof Coding : Adaptive Collaboration for Resilience
(Anton Weiss, Otomato Software)

* Solitary coding != collaborative coding.
* Collaboration = communication + coordination + alignment.
* Colabboration is inversely proportional to scale.
* Promise theory: publish intentions in form of promises.
* Promises != executive commands.
* Adapt to a rate of unkept promises.
* Resilience: "how a system bends instead of breaking."
* Careless engineering helps to build resilient systems.
* Build resilient teams (teams that can adapt to new situations): Diversity, sharing.
* Efficient != resilient.
* Dialogue: Different form of conversation. No judgement or regulation.
* Empathy: Understand other teams. Shadowing.
* Championship. Champions promoteDevOps.
* Manage stress.


### Site Reliability Engineering: Anti-patterns in Everyday Life and What They Teach Us
(Jennifer Petoff, Google Ireland)

* SRE patterns:
  * Users should never notice outage before you
  * Eliminate classes of errors rather than point fixes
  * Don't feed machines with human toil
  * Faiure is an opportunity to improve
* Coffee machine example:
* Set and meet SLOs aligned with happiness.
* Don't overload -> cascading failure.
* Avoid Ops overload -> don't overload people.
* Actively plan and manage serving capacity
* Hotel lock example:
* Incident management framework:
  * Access impact, mitigate and verify, debug, short term fix, underlying causes, long term fix, resolved.
  * Impact - High risk - Low risk - Resolved.
* "Human" errors are really systems problems (can't fix people, but can fix systems to make people do better).
* Lack of ownership -- empower teams to mitigate and resolve issues.
* Case for blamenessless:
  * Failure happens
  * Embrace failure to improve MTTD and MTTR
  * Proactively address failure -- more robust systems
* Takeaways:
  * Reap a return on the unplanned investment by learning
  * It's never human error


### The Past, Present, and Future of Cloud Native API Gateways
(Daniel Bryant, Ambassador Labs)

* Edge: Boundary between data center and your users.
* Thesis: Evolution of edge has been driven by app architecture and technology.
* History:
  * 90s: Hardware LB: HA/Scalability.
  * 00s: Nginx/HAProxy: HA/scalaility (lower cost).
  * 05s: Ajax -- Application Delivery Controller (ADC). HA + application acceleration. SSL offload, caching, compression, LB.
  * 10s: API gateway 1st gen. Expose APIs ("api management"), L7 routing, publishing, dev portal, analytics, monetization.
  * 15s: API gateway 2nd gen. ADC, API Gateway, Monolith, Mini-services: Centralize cross-cutting app concerns, Authentication, rate limiting, monitoring, routing.
* Building cloud-native applications: Microservices, built/released/scaled independently.
  * App Architecture: Spectrum of services.
  * Different locations: K8s/Vms/FaaS
  * Different protocols: gRPC, http,websockets, tcp
  * different load-balancing: Sticky sessions, round robin.
  * Different authentication requirements
* Cloud gateway neesd:
  * Need API gateway management stuff.
  * Need ADC-like traffic management
  * Real time service discovery
* Microservices lead to even bigger change:
  * "You build it, you run it." (from code to production)
* Workflow: Full cycle development
* Stack self-service tooling, all backed by specialists:
  * Build tools
  * Deployment pipelines
  * Metrics and alerts
  * Insights tools
* Dev teams use this "platform" self services to optimize their workflow.
* Thesis: The future evolution of the edge will be drive by applicaiton architecture, technology and workflow.
* Two biggest challenges with k8s and edge:
  * Scaling edge management - more things at the edge, changes to the edge becomes a bottleneck.
  * Supporting diverse edge requirements.
* Strategies for Edge with Kubernetes
  * Deploy additional kubernetes api gateway. Below normal gateway.
  * extend existing gateway (k8s operators integrate)
  * deploy an in-cluster edge stack. 
 
### CI and CD for Documentation
(Olivier Jacques & Laurent Gil, DXC Technology)

* The quest for great documentation.
* Widely used: microsoft, github, gitlab, aws.
* fast, secure, cheap (static sites)
* easier to contribute (git flow)
* battle tested, engineered (automated tests, different outputs - sites/pdf/whatever)
* monitoring (analytics)
* challenges: diagrams (what changes?), broken links, publishing, DRY, common voice, common look/feel.
* CI: Spell checking, approved acronyms, one voice, dead links.
* CD: automate publishing
* CI/CD tools for documentation:
* Authoring: Markdown
  * Editors: Intellij/VSCode/Eclipse/etc
  * Markdownlint, Draw.io (drawings), PlantUML (diagrams as code), Marp (slides)
  * Github Codespaces or GitPod -- edit directly from browser, make it easy for tech editors (no local install), shared extensions.
* Pick a tool:
  * Jekyll -- not good experience (-)
  * Hugo -- powerful, blazing fast (/)
  * Marp -- slides as code in markdown
  * MkDocs + material theme (/)
* Orchestrating:
  * GitHub Actions, GitLab CI, Jenkins, AWS Code Pipeline, AzureDevops
* Linter: github super-linter, markdownlint (vscode plugin)
* Spell-checker: spellcheck-github-actions, spellcheck-cli, vscode code-spell-checker extension
* Link checker: markdown-link-check
* Style/voice: Vale
* Hosting: Github pages, Gitlab pages, Netlify, S3 bucket
* Making it easy: Github templates, Gitlab project templates

### Your own Kubernetes Operator: Not Only in Go
(Nicolas Fränkel, Hazelcast)

* Controllers: Control loops that modifies state.
  * Deployment controller, Job controller, etc.
  * Out-of-the-box controllers are in the control-plan.
  * Custom controllers can run anywhere (inside or outside cluster).
* Operator: Application specific controller.
  * Extends kubernetes API with CRD, and controls the CRD.
  * Operator is controller that manages a CRD.
  * Talks to API server, REST based
  * Mostly written in Go (K8s is written in Go, there is the operator-sdk in Go)
* Using fabric8 kubernetes-client + GraalVM to make small image.
(was missing talk about dealing with CRDs in fabric8 kubernetes-client)
  * 


### Serverless databases: the good, the bad, and the ugly
(Renato Losio, Funambol)

* Aurora database, mysql "automatic" scaling
* boto3
* Elastic scaling databases
* Pay for what you need (bad queries -> you pay more until you fix the issue)


### Service Mesh Past, Present, and Future with Envoy Proxy and WebAssembly
(Idit Levine, Solo.io)

* From monolity to microservices -> the network is the queen of the cloud.
* Challenges:
  * Routing: Make A talk to B (traffic control, resiliance)
  * Security: Make A talk to B securely (root cert, mtls, policy)
  * Observability: A talks to B1, B2, B3, you need to be able to observe it (metrics, logs)
* From: library / application specific routing/security
* To: Network abstraction: Service mesh: Separate operation code from business logic in separate layers.
* How: Sidecars to your service which setups the routing, security, observability (it's a proxy, Envoy)
  * Control plane (envoy config)
  * Envoy (data plane)
  * Service
* Service mesh challenges:
  * Hard to tell which is best
  * Complicated on-boarding
  * Different APIs
* Contendors: Linkerd, nginx, consul, istio, kuma, open-service-mesh, mæsh
  * Some are built on top of Envoy, some are not.
* Supergloo: API on top of existing meshes.
  * KISS: Source -> Policy rule -> Destination
  * Standardized: Service mesh interface (SMI)
  
### I Have an SLO. Now What?
Alex Hidalgo, Alex Hidalgo

* What to do with all the data we have? (Logs, metrics, traces) Setup SLOs
* The reliability stack:
  * SLIs (service level indicator): Measurements from user perspective (measure what customers actually need from us)
  * SLOs: Target percentages for SLIs (how often do they show correct, pre-done math)
* 100% isn't reasonable, it's too expensive to even try
* Error budgets: Measurements over SLOs over time
* Measure service reliability!
* Service has one job: Do what the user needs it to do.
* Using error budgets (this is outdated!):
  * Error budget surplus -- ship features
  * Error budget exceeded -- stop, fix reliability
* What to do with your SLO data:
  * Maintain balance between shipping and fixing reliability
  * Determine focus of project work (reliability improvements are features, not everyone owns the code they own) -- measure better SLI is project work. So is picking better SLO thresholds. Examine measurements often. They could be wrong!
  * Are users happy? Align error budgets to user happiness.
  * Examine your risk factors. Determine biggest risks according to burning error budgets. Figure out when you're unreliable (proactively improve reliability).
  * Justify experimentation / chaos engineering. When do you start burning from error chart? Use error budget to experiment.
  * Schedule load tests, stress tests, and blackholes. Where on the curve does stuff break?
  * Just turn stuff off. Burn error budget to get a feeling of what fails when components are down.
  * Do nothing. Nothing at all. SLOs are data, not mandate (you don't need to do anything)
  * Report your service reliability in a more meaningful way. (error budgets over tickets and mttX)
  * Have better conversations, leading to better decisions(!)
* Everything is about humans and data driven decisions


### Fast & Simple: Observing Code & Infra Deployments At Honeycomb
(Liz Fong-Jones, honeycomb.io)

* How to ship at honeycomb:
* Instrument as we code
* Functional and visual testing
* Design for feature flag deployment
* Automated integration
* Human PR review
* Green button merge
* Auto-updates, rollbacks and pins
* Observe behaviour in production
  * Prod: customers observe data
  * Dogfood: observes prod
  * SLO adoption: page views
  * Kibble observes dogfood
* That's how 12 engineers deploys 12 times/day
* Tips:
  * Start with lead-time
  * Deploy frequency goes up
  * Change fail rate goes down
  * time to restore goes down
  * 0.1% fail-rate
* What about infrastructure?
  * Infrastructure empowers products
  * Kubernetes isn't the goal: Reliability and simplicity is
  * Everyone starts somewhere
  * Automate painful parts
  * Keep enviornment clean
* Repeatable infrastructure with code
* Centralize state and locking
* Diff and release in browser
* Remote run from git
* Deploy changes incrementally
* Feature flags for infra!
  * Ephemeral fleet and autoscaling
  * Quarantine bad traffic
* Scaling challenges
  * Team size has doubled
  * Commit frequency is up
  * Consumer traffic is pouring in
  * Bottlenecks
  * Releases not granular enough
  * Manual rollbacks are too slow to maintain SLOs
* SLOs:
  * 99% Store incoming telemetry
  * 99% Default
* Sleep easily at night is the top priority in the company


### Continuous Delivery for Machine Learning
(Adarsh Shah, Consultant)

* ML code is a small part of the machine learning application system (feature extraction, analaysis, etc etc)
* Data management - experimentation - Production
* Challenges unique to ML:
  * Data management
  * Experimentation (lots of CPU for training models)
  * Production deployment (offline/online prediction, monitoring/alerting)
* Solutions
  * Data management: Data pipelines (automated), Versioned datasets
  * Experimentation: CI (training code)
  * Production deployment: CI (application code), smoke tests


### Six Categories of Monitoring in the DevOps Pipeline
(Hasan Yasar, CMU)

* metrics logs reports -> data
  * devops metrics
* monitoring -- architecture, metrics to dashboard, 
* Logs is a specific event. Metrics is a measurement at a time.
* Pipelines (flow) generates a lot of data.
* We want to quantify impact of investment in software delivery
* Devops metrics pyramid
* Guidelines:
  * avoid relying on single metric
  * look for trends, outliers and level shifts -- not only averages
* when to measure:
  * bug report submitted
  * change request submitted
  * code commit
  * build progress
  * test results
  * deployment activities
  * operation failure and recovery
  * application usage and latency
* metrics categories
  * productivity (deployment freq)
  * reliability (mttr, mttd)
  * quality (failed deployments, number of tickets)
  * security (change req)
  * operations
* monitoring: collect, interpret, and make action from information gathered
* types of monitoring: development (devops process), usability, perofrmance, security, business (kpi), functional (use-cases how are capabilities working)
* development: build failures, testing failures, issue monitoring
* operations: outage monitoring, resource usage
* security: vuln monitoring


### How to Scale Your Company's Security
(Clint Gibler, r2c)

* Distilled insights from surveying lots of companies
* Mindsets and principles
  * automate as much as possible
  * guardrails not gatekeepers (minimize no's)
  * prefer high-signal low-noise tools and alerting (better to miss something than drown)
  * developers are your customers (build useful features, telemetry logging, etc)
  * self-service security (tools and services than can be used without security taems interaction)
* Chose how to invest time: Now, short-term, long-term (yes)
* Focus: Is X better use of time than Y?
* Fundamentals: vuln mgnmnt (know current state, minimize friction for devs, track in same system as you usually work/workflow -- jira), cont. scanning.
* data driven bug bounty
  * open vulnerabilities by prio over time
  * open vulns by subteam and priority
  * bug bounty cost per vuln class (need bug bounty program)
* cont scanning:
  * scan new code with static and dynamic tools
  * dracon 
  * scan unit PRs
  * show tool findings within PR
  * capture metrics
  * go for linting/AST
* asset inventory
  * what do you own and how do they connect?
  * use the asset inventory to answer questions (which servers are exposed through internet?)
  * use asset inventory for shortening vuln window, by easier finding out who has to fix stuff.
* security engineering: implement libraries/wrappers to take care of classes of security problems.
  (e.g. library to call SQL which takes care of SQL injections)
* Automating least priviledge
* Enforce invariants (alert on things that should never be true, e.g. auto-shutdown if we can access internet, or, alert if we can access everything on internet)
  * what should always or never be true in your environment
  * which can we programatically alert on
  * and automatically take action on?
  
### Sensory Friendly Monitoring: Keeping the Noise Down
(Quintessence Anx, PagerDuty)

* Lots of notifications, we feel overloaded. In own life, put headphones on.
* Buries important/high sev alerts in a sea of low prio notifications -- the people who neede to be notified wont be.
* Let's find a happy medium for high sev alerts.
* Consider: the cost of noise -- your brain on alerts.
* Bubble burst for the problem you were building -- simple questions interrupted costs ~25 min (study shows)
* Costs quality.
* Not possible to compensate for the interruption, does not depend on the problem "complexity"
* Be aware, not overwhelmed:
  * Determine the sources of noise
  * Categorize the types of noise.
  * Channel noise into productive flow
  * Create a routine to clear clutter
* Sources of noise: email, tickets, slack, PRs, humans, etc. (you're the source of your noise)
* How often do you check mail, etc....?
* Communication boundaries:
  * Setting time to focus, including friends and family (e.g. create focus-time for yourself)
  * Define "relevant emergency"
  * Set reasonable expectations for yoruself and others.
* What about external sources:
  * Categorize your noise (severity, false positives, false negatives, fragility, frequency). Fix it!
* Noise flow:
  * What needs to be known
  * who needs to know it
  * how soon should they know it
  * how should they be notified
  * Be specific in alerting, do not train people to ignore notifications
* Re-evaluate redundancy (e.g. slack is down, can we dynamically re-route the notifications to email/etc)
* Resilient noise builds trust. Silence is artificial (why is there no notifications?)
  * How reliable are your services? How much notification duplication is needed?
* Keep alerts relevant: For every alert triggered ask: 
  * Was it needed? (if not, delete it)
  * How was the incident resolved? 
  * Can the solution be automated? (switch what is triggering the alert to the automation?)
  * Is the solution permanent? (condition does not exist anymore, delete it)
  * How urgently was a solution needed? (adjust if too severe, or not severe)
* 




