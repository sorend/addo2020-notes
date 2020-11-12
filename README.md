
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
* * Users should never notice outage before you
* * Eliminate classes of errors rather than point fixes
* * Don't feed machines with human toil
* * Faiure is an opportunity to improve
* Coffee machine example:
* Set and meet SLOs aligned with happiness.
* Don't overload -> cascading failure.
* Avoid Ops overload -> don't overload people.
* Actively plan and manage serving capacity
* Hotel lock example:
* Incident management framework:
* * Access impact, mitigate and verify, debug, short term fix, underlying causes, long term fix, resolved.
* * Impact - High risk - Low risk - Resolved.
* "Human" errors are really systems problems (can't fix people, but can fix systems to make people do better).
* Lack of ownership -- empower teams to mitigate and resolve issues.
* Case for blamenessless:
* * Failure happens
* * Embrace failure to improve MTTD and MTTR
* * Proactively address failure -- more robust systems
* Takeaways:
* * Reap a return on the unplanned investment by learning
* * It's never human error









