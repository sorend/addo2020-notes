
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

  
  
