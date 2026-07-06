# 8. Behavioral & Case Studies

Real-world engineering scenarios and cross-functional collaboration — synthetic biology design work is rarely a solo, purely technical endeavor.

---

### Q: Tell me about a time an engineered construct or strain didn't perform as expected once tested, despite looking correct on paper (and by sequencing verification). Walk me through your troubleshooting process. 🟡

**What a strong answer includes:**
- Honesty that this is an extremely common experience in synthetic biology — interviewers are wary of candidates who present every design as having worked cleanly on the first attempt.
- A systematic troubleshooting approach: verifying the construct's sequence and successful transformation/build first, then considering context-dependence issues (chassis effects, unexpected host interactions), metabolic burden, or genetic instability as potential explanations, rather than jumping to conclusions.
- A concrete example connecting to specific technical concepts (e.g., unexpected transcriptional interference, RBS performance not matching prediction, genetic instability under selection) discussed elsewhere in this repo.
- A systemic change made afterward (e.g., a new standard verification step, a more conservative design choice for a similar future construct) to reduce the chance of a similar surprise recurring.

**Follow-ups:**
- How did you distinguish between the possibility that your design itself was flawed versus that something went wrong during the build/testing process?

---

### Q: Describe a time you had to make a design tradeoff between engineering elegance/thoroughness and practical delivery timeline. 🟡

**What a strong answer includes:**
- A specific, honest articulation of the actual tradeoff (e.g., choosing a simpler, less modular design that could be built and tested faster, versus a more thorough, future-proofed design requiring more upfront characterization effort) rather than a vague generality.
- Evidence of communicating this tradeoff transparently to relevant stakeholders (a manager, a cross-functional partner) rather than making the call unilaterally and silently.
- A concrete outcome, with honest reflection on whether the tradeoff was the right call in hindsight, including any technical debt incurred and how it was later addressed (or wasn't).

**Follow-ups:**
- How do you generally decide how much design/characterization rigor is "enough" for a given project stage, given that more rigor always costs more time?

---

### Q: Walk me through how you'd approach designing a genetic construct for a completely new host organism your team hasn't worked with before, given a specific target function to engineer. 🟡

**Case-study structure — a strong candidate would:**
1. **Research what's already known and characterized for this host organism** — existing genetic tools, characterized parts, known transformation/editing methods, and any documented pitfalls from prior work by others, rather than assuming techniques and parts from a more familiar host organism will transfer directly (tying to the chassis-dependence discussion in section 1).
2. **Start with a small-scale, well-instrumented pilot** (e.g., testing basic reporter constructs to characterize baseline part performance in this new host) before committing to the full target construct, since a new, uncharacterized host introduces substantial additional uncertainty that's worth de-risking incrementally.
3. **Identify likely failure points specific to this new host** proactively (e.g., different codon usage bias requiring re-optimization, different available selection markers, different growth/transformation protocols) rather than discovering them only after a failed full-scale attempt.
4. **Set realistic timeline expectations** with stakeholders given the added uncertainty of working with an unfamiliar host, rather than assuming the same timeline that a similar project in a well-characterized, familiar host organism would take.

**Follow-ups:**
- How would you decide how much upfront characterization/pilot work is worth doing in the new host before committing to the full target construct, given time and resource pressure to show progress on the actual target application?

---

### Q: Tell me about a time you had to communicate a technical limitation or failure to a non-technical stakeholder (e.g., a business/commercial partner) who was expecting a specific engineering outcome on a specific timeline. 🟡

**What a strong answer includes:**
- A specific example of translating a genuine technical setback (e.g., unexpected metabolic burden limiting achievable yield, or a directed evolution campaign plateauing below target performance) into terms a non-technical stakeholder could understand and use to make an informed decision, rather than either minimizing the issue or being so technical as to be unhelpful.
- Evidence of proactively flagging risk/uncertainty before it became a surprise, where possible, rather than only communicating a setback once it had already fully materialized.
- A concrete, constructive path forward proposed alongside the bad news (e.g., a revised timeline, an alternative approach, or a scoped-down interim milestone) rather than simply delivering the setback without a plan.

**Follow-ups:**
- How do you calibrate how much technical detail to include when communicating a setback like this, given that oversimplifying can lead to the stakeholder underestimating the genuine difficulty involved?

---

### Q: Describe a situation where you had to collaborate closely with a computational/data science colleague (or team) to design an engineering campaign, given that you brought biological/experimental expertise and they brought computational/modeling expertise. 🟡

**What a strong answer includes:**
- Evidence of genuine two-way collaboration — incorporating computational predictions and design suggestions into experimental planning, while also providing experimental feedback and domain context that helped the computational colleague refine their models/approach, rather than either side working in isolation.
- A specific example showing how this collaboration led to a better outcome than either the purely experimental or purely computational approach would have achieved alone (e.g., a computational model helping prioritize a much smaller, more tractable set of candidates for experimental testing than would otherwise have been feasible to test exhaustively).
- Honest acknowledgment of any friction or miscommunication that arose (e.g., a computational prediction that didn't hold up experimentally, or an experimental result that was hard for the computational colleague to interpret without additional biological context) and how it was resolved.

**Follow-ups:**
- How would you approach a situation where a computational colleague's model consistently prioritizes candidates that don't perform well experimentally, straining trust in the collaboration?

---

### Q: Tell me about a time you had to decide whether to escalate a biosafety or biosecurity concern about a project you were working on. 🔴

**What a strong answer includes:**
- A specific, appropriately discreet description of the concern and the reasoning behind it (interviewers should not expect or want operationally sensitive specifics — focus on the decision process and judgment involved, not technical specifics of the concern itself).
- Evidence of engaging appropriate institutional channels (biosafety committee, appropriate oversight body) rather than either unilaterally deciding the concern wasn't serious enough to raise, or unilaterally taking independent action outside established institutional processes.
- A clear articulation of how the concern was ultimately addressed or resolved, and what you learned about your organization's (or your own) processes for handling this kind of situation.

**Follow-ups:**
- How do you think about the balance between being appropriately cautious/proactive about raising potential concerns versus avoiding being someone who raises false alarms so often that genuine concerns risk being taken less seriously?
