# Multi-Phase Audit: Diverge-Converge Model

[Hans Friese](hans@cyfrin.io), [Patrick Collins](patrick@cyfrin.io), [Alex Roan](alex@cyfrin.io)

### Abstract

This paper delves into the exploration of various audit models that are pertinent to Web3 security. In our examination, we weigh the advantages and disadvantages of each model and introduce a novel model that is designed to reach the pinnacle of audit quality.

Our proposed audit model is structured into four essential distinct phases: a solo audit conducted by a lead auditor (or a traditional audit firm), a public epochal time-boxed bug bounty, an exclusive competition, and a final review. Additional phases can be added to the end of the third phase according to the protocol's preference.

In each of these phases, an audit report is generated which helps update and fortify the protocol codebase by addressing the vulnerabilities discovered in the preceding phase.

It is worth noting that the new model is not equal to simple combination of the existing models.
A unique feature of this model is the way each phase is interlinked with a set of incentives and disincentives, fostering a spirit of rigorous competition amongst auditors.

This model is meticulously crafted to enhance the efficiency of the audit process, striving to minimize both the time and cost associated with the completion of the audit.

Being the first model of its kind to incorporate multiple distinct phases of auditing, we anticipate that it will offer high quality in audits and foresee its wide adoption in the Web3 space.

# 1. Introduction

## 1.1 Background

The Web3 realm, commonly hailed as the next generation of the internet, is characterized by rapid evolution and expansion with a multitude of decentralized applications and platforms. These decentralized networks bring forth a host of advantages including enhanced privacy, resistance to censorship, and a democratized platform for creating value. Nevertheless, they also present unique security challenges that need to be addressed.

The fabric of the Web3 ecosystem is woven with blockchain technologies, smart contracts, and decentralized applications (dApps). Smart contracts stand out as they form the backbone of many Web3 applications, defining the rules and logic for decentralized interactions. Given their self-executing nature and the fact that the agreement terms are hard-coded, they become immutable once deployed. This immutability implies that post-deployment, any existing vulnerabilities or bugs in the contract cannot be rectified, turning them into attractive targets for hackers.

_TODO: Explain the security concerns that the industry faces at the moment with statistics and some notorious security breaches._

These incidents underscore the urgent need for comprehensive and robust security audits in the Web3 space. Security audits involve scrutinizing the code of smart contracts and dApps to detect and rectify vulnerabilities prior to deployment. However, existing audit methods have fallen short in the face of the complexity and rapid development pace within the Web3 ecosystem.

This paper explores the shortcomings of current audit models and presents the Multi-Phase Diverge-Converge Audit Model, a novel approach aimed at boosting the quality and efficiency of audits in the Web3 sphere.

## 1.2 Scope and Terminology

This paper primarily focuses on the security aspects of smart contracts and dApps within the Web3 ecosystem prior to their deployment. Aspects related to the architectural recommendations during the development and the post-deployment security are not within the purview of this paper.

- The term "**protocol**" in this context is used to denote the smart contract or dApp that is the subject of the audit.
- The "**client**" refers to the individual or organization that possesses ownership over the protocol and commissions the audit.
- An "**audit**" signifies the procedure of inspecting the protocol's code with the aim of detecting and eliminating vulnerabilities. Generally the terms "audit" and "security review" are used interchangeably but we will use the term "audit" throughout this paper. In a narrow sense, we use the term "audit" to refer to the process of inspecting the protocol's codebase that are ready to be deployed.
- An "**auditor**" denotes the individual or organization entrusted with the task of conducting the audit.
- An "**audit report**" is the conclusive document produced by the auditor upon completion of the audit process.
- A "**bug bounty**" is a mechanism to encourage the public to discover vulnerabilities in the protocol. In a traditional bug bounty program, rewards are given only for the first reported instance of a particular vulnerability, with subsequent duplicate reports not being eligible for rewards.
- A "**contest**" is a similar incentive-based process aimed at public participation in finding protocol vulnerabilities. Contrary to bug bounties, contests reward all valid vulnerability submissions.

# 2. Defining a Good Audit Model

In the context of Web3 application security, defining what makes an audit "good" is a crucial discussion. We suggest that an optimal audit model should meet three fundamental criteria: flawlessness, or **Perfectness**; operational effectiveness, or **Efficiency**; and the provision of supplementary benefits, which we categorize as **Plus**.

## 2.1 Perfectness

A high-quality audit aims for an ideal state we define as **Perfectness**. Perfectness represents a scenario where the audited codebase is entirely devoid of vulnerabilities. The quest for perfectness makes the codebase progressively more secure and reliable as we inch closer to this ideal state. The role of auditors is pivotal in this journey - as they dig deeper into the code, unearthing and resolving more bugs and vulnerabilities, the reservoir of potential vulnerabilities diminishes. This ongoing cycle of discovery and resolution of vulnerabilities fuels a positive feedback loop in the audit process. Each vulnerability spotted and fixed nudges us nearer to perfectness, thereby establishing a cycle of continuous enhancement towards a totally secure codebase.

The pursuit of audit perfectness encompasses two critical elements: **Exploit Quality** and **Consult Quality**.

- Exploit Quality is a measure of the audit's proficiency in detecting and evaluating potential vulnerabilities in the codebase. The objective is to unearth and address as many vulnerabilities as possible, reducing the pool of remaining vulnerabilities and advancing towards perfectness.

- Consult Quality, on the flip side, refers to the auditor's capacity to provide insightful advice and recommend best practices that enhance the overall security and robustness of the codebase, thus aiding the progress towards perfectness.

In this paper, we focus more on the exploit quality of the audit while the consult quality is also important.

When addressing perfectness, multiple factors contribute to the quality of the audit.

- Top-Tier Engagement
  Engaging a top-tier auditor in the process is invaluable, as their expert knowledge and experience significantly boost the exploit and consult quality of the audit.
- Many Eyes
  The "Many Eyes" principle implies that having a larger pool of auditors reviewing the codebase can enhance the chances of identifying vulnerabilities.
- Number of Rounds
  The quantity of audit rounds can influence the audit quality. Conducting multiple rounds can lead to the detection and resolution of more vulnerabilities, thus improving the exploit quality.
- Brainstorming
  Organizing brainstorming sessions among auditors can enhance the audit quality. These sessions allow auditors to leverage each other's expertise and share knowledge, leading to more comprehensive audits.
- Tooling
  Employing advanced tools like static analyzers can automate certain parts of the audit, improving its efficiency and comprehensiveness.

### The Role of Incentives and Disincentives

An essential consideration in auditing is the dedication of the auditor. When we speak of top-tier engagement, we're referring to a review that's carried out with a high level of commitment. This **Dedication** is a vital ingredient in a successful audit. Ideally, there should be a system that offers incentives or imposes disincentives on the auditor, influenced by specific "metrics". For example, an auditor could be incentivized based on the number of vulnerabilities they uncover, or face disincentives if they fail to adhere to set deadlines. This system of incentives and disincentives is an integral part of the Diverge-Converge Audit Model, which we will delve into later.

## 2.2 Efficiency

While striving for perfection is vital, it's also essential to maintain efficiency in terms of both turnaround time and cost. A high-quality audit shouldn't excessively delay the protocol's deployment or result in prohibitive expenses, as these factors can hinder innovation and growth within the Web3 ecosystem. It's important to clarify that being efficient doesn't mean rushing deployment. Instead, it's about reducing time and cost while ensuring the protocol's security through thorough efforts. The Diverge-Converge Audit Model is designed to enhance efficiency, minimizing both the time and cost associated with completing an audit.

## 2.3 Plus

A quality audit transcends mere perfection and efficiency, delivering added value through services like:

- **Architectural Review**: Evaluating the overarching system design, possibly including invariant definitions.

- **Threat Modelling**: A structured representation of all data affecting the protocol's security, essentially viewing the system from a security perspective.

- **Formal Verification**: Leveraging mathematical logic and reasoning to ensure the system functions correctly under all conceivable scenarios.

- **Test Support**: Aiding in the creation of a suitable test suite for the protocol, inclusive of invariant tests.

- **After Sight**: Providing assistance for potential incidents that might emerge after deployment.

Engaging in a prolonged partnership with an auditor or audit firm can be beneficial for clients in the long run, as it often leads to a deeper understanding and more comprehensive support.

## 2.4 Conclusing Remarks

In conclusion, when a protocol seeks an auditor's expertise, the attributes they prioritize can be ordered as: **Perfectness > Efficiency > Plus**.

Naturally, tension can arise between these different facets of a high-quality audit. For instance, while the involvement of top-tier auditors is desirable, it may pose challenges when coupled with the 'Many Eyes' approach, as the cost could escalate rapidly. Striking a balance between accommodating numerous reviewers and managing cost and efficiency constitutes a complex aspect of the auditing process that warrants careful navigation.

# 3. Assessment of Current Audit Models

In this section, we delve into existing audit models, discussing their strengths and weaknesses, considering factors such as perfectness, efficiency, and added value.

## 3.1 Individual Solo Audit

The individual solo audit approach represents the most basic model of auditing. Here, a single personal auditor is contracted by the client to scrutinize the protocol. Following the audit, the auditor compiles an audit report, upon which the client updates the protocol codebase to rectify the vulnerabilities detected in the report.

Clients tend to engage auditors who possess a strong reputation within the Web3 space. This is primarily due to the level of trust in the auditor's ability to conduct a comprehensive audit and produce a high-quality audit report. The auditor typically receives a predetermined payment for the audit.

While this model hinges on the auditor's credibility and integrity, it has several shortcomings.

First, being a single individual, the auditor may not be equipped to discover all potential vulnerabilities in the protocol. And the audit process is devoid of brainstorming or collaborative input.

Second, the fixed payment structure may not serve as an adequate incentive for the auditor to conduct an exhaustive and timely audit. The auditor may not be motivated to invest additional time and effort in the audit, as their compensation is predetermined.

Third, the process may lack the support of advanced tooling. The auditor may not have the latest tools or frameworks at their disposal to conduct the audit effectively.

Despite these limitations, the individual solo audit approach is the most economical model and may be suitable for smaller projects with constrained resources. Notably, this approach is frequently used in combination with other audit models.

## 3.2 Traditional Audit

The traditional audit approach is the most frequently adopted model. In this setup, the client contracts an audit team to review the protocol.

The audit team typically comprises a lead auditor, several assistant auditors, and often a project manager. The team engages in numerous brainstorming sessions during the audit process. The lead auditor is usually a highly reputed figure in the Web3 domain. The project manager ensures the audit is conducted in a timely fashion, overseeing the audit process. Additionally, the team generally has access to the most up-to-date tools and frameworks, bolstering the quality of tooling support.

Nevertheless, this model also rests heavily on the reputation and integrity of the audit team and shares similar shortcomings with the individual solo audit approach. Although multiple auditors participate, each individual auditor might not be incentivized to conduct a comprehensive and prompt audit, as their compensation is predetermined by the firm.

This model has been used to audit the majority of protocols deployed in the Web3 space, with the audit reports frequently made public.

Unfortunately, there are instances where protocols audited using this model have been compromised or exploited post-deployment. This raises questions about the quality of the audit and the effectiveness of the traditional audit model. We would like to note that this criticism is not directed at any particular audit firm and there are more than a few firms that have conducted high-quality audits and have a strong reputation in the Web3 space.

## 3.3 Contest-Based Audit

This model is a relatively new entrant, quickly gaining traction in the Web3 space. Here, the client organizes a contest with a prize pool, incentivizing the public to discover vulnerabilities in the protocol.

Typically, there is no cap on the participant count and the contest is open to all. Code4rena and Sherlock stand out as the most frequented platforms for conducting such contests in the Web3 domain, attracting hundreds of auditors to participate. Both platforms have successfully hosted numerous contests, with millions of dollars distributed in prizes.

### 3.3.1 Code4rena

[Code4rena](https://code4rena.com/) holds the distinction of being the pioneering platform for contest-based audits in the Web3 sphere and enjoys a reputation of high esteem. Each contest held by Code4rena witnesses participation from hundreds of auditors, ensuring the protocol codebase is inspected by numerous reviewers. It's notable that contests hosted by Code4rena often yield a higher number of findings compared to traditional audits. By discouraging duplicate submissions, Code4rena motivates participants to uncover unique vulnerabilities in the protocol codebase.

In terms of efficiency, Code4rena represents an effective audit model, enabling the protocol codebase to be inspected by a multitude of reviewers within a relatively short timeframe and at a lower cost. The platform also offers a degree of tooling support.

However, Code4rena faces substantial challenges with respect to achieving perfectness.

The incentive to uncover vulnerabilities has considerably diminished, a significant issue given the rapidly increasing participant count in Code4rena contests. Moreover, changes to the prize pool distribution structure have resulted in a smaller share for actual auditors. These factors have led to many top-tier auditors shifting away from Code4rena contests to other platforms or organizations. The absence of top-tier engagement negatively impacts the exploit quality of the audit, despite Code4rena's assertion that new, proficient auditors continually join their contests.

Theoretically, there is no guarantee that the protocol codebase will be inspected by top-tier auditors, especially when there are multiple on-going high-prize contests. Also the assigned auditors are kind of random for every contest and they are only engaged for a short period of time.

Criticism has also been directed at the unilateral judging model, which has deterred participants from joining the contests. The judging process lacks transparency, majority of the participants are unable to appeal the results.

### 3.3.2 Sherlock

[Sherlock](https://sherlock.xyz/), another platform for contest-based audits, has been gaining popularity in recent times.

Sherlock is recognized for its innovative approach in several areas.
First, the platform has introduced a scoring system for participants. Scores are assigned based on submission quality, and high scorers, designated Senior Lead Watsons, stand to gain a significant portion of the prize pool. This scoring system serves as a powerful incentive for top-tier auditors to participate in the contests. Indeed, several top-tier auditors have shown active participation in Sherlock contests.
Second, Sherlock introduced an insurance system, the first in the industry. Clients can insure their protocols, with the insurance compensating clients in the event of a hack or exploit. While the effectiveness of this system remains to be seen, it represents a noteworthy advancement in terms of post-deployment support.
Third, Sherlock has brought in a community-based judging model.

However, debates surrounding the system's fairness persist, given the privilege granted to the lead auditor to influence judging decisions (directly or indirectly). It is observed that majority of the prize pool is often rewarded to the lead auditor on top of their fixed percentage of the reward pool. This has discouraged participants from joining the contests, resulting in a lower participant count compared to Code4rena contests.
There also exists a problem of diminishing returns for duplicate submissions similar to Code4rena.

### 3.3.3 Prevalent Issues

Despite the high efficiency of the crowd-sourced contest-based audit model, it is not without its share of issues.

- Often, the audit is conducted as a singular event, with no follow-up review to verify the rectification of identified vulnerabilities unless the client requests and pays for a separate review. This presents a significant issue as the protocol codebase isn't scrutinized post-mitigation.
- Auditors independently traverse the entire process, from document review to codebase scrutiny, with minimal collaboration. This lack of cooperative brainstorming is a notable drawback, as it limits the opportunity for auditors to learn from each other and incurs a waste of time and effort.
- With the growing number of participants, the incentive to uncover vulnerabilities has diminished significantly, resulting in a lack of top-tier engagement.
- The engagement of auditors is limited to a short period of time, with no long-term relationship established between the client and the auditor.

## 3.4 Hybrid Audit

This model bears resemblance to the traditional audit model, but differentiates itself by categorizing auditors into various levels, with incentive allocation based on the auditor's level.

### 3.4.1 SpearbitDAO

[SpearbitDAO](https://spearbit.com/) emerged as the inaugural organization to implement this model, winning acclaim for their high-standard audits.

For each audit request, one or two lead auditors are selected from a pool of top-tier auditors to conduct the audit alongside associate auditors as a team. While the audit flow mirrors that of the traditional audit model, SpearbitDAO distinguishes auditors into several levels through a rigorous review process, with lead auditors receiving considerable incentives.

The generous incentive scheme ensures robust engagement from the lead auditors, motivating them to conduct comprehensive and prompt audits. This active involvement from several top-tier auditors culminates in an audit report of high quality.

It's worth noting that SpearbitDAO hosts public brainstorming sessions and retrospective reviews for every audit, enabling auditors to learn from each other and enhance their skills.

However, this model also comes with certain drawbacks.

- The cost of auditing is significantly high due to the substantial incentives provided to lead auditors.
- There is technically no disincentive mechanism for auditors, which could potentially result in a lack of sufficient dedication. Fixed predetermined incentives for auditors may not be adequate to motivate them to conduct a thorough audit.

### 3.4.2 AuditOne

[AuditOne](https://auditone.io/) serves as another audit platform that assigns audit requests to a pool of auditors based on their expertise and experience.

Auditors join the platform and increase their experience score by participating in audits and Capture The Flag (CTF) events. A unique feature of the platform is that the audit cost undergoes an approval process led by a high-tier auditor. Auditors are incentivized relative to their experience score – higher scores lead to higher incentives.

For every audit request, a team of four auditors is selected from the pool based on score and availability. The audit flow parallels that of the traditional audit model.

This model shares similar limitations with the traditional solo audit model.

## 3.5 Conclusing Remarks

In this section, we delved into an analysis of current audit models, examining their strengths and weaknesses in terms of perfectness, efficiency, and added value. We also contrasted these models and assigned them ratings based on our subjective analysis and estimation.

Upon evaluating the existing audit models, it becomes evident that they are not without flaws, thus underscoring the need for a novel audit model that can optimize audit quality.

# 4. Multi-Phase Audit Model: Diverge-Converge Model

We propose a novel audit model, the Diverge-Converge Model, designed to enhance the quality of audits by providing appropriate incentives to auditors and ensuring that the protocol codebase undergoes a thorough three-phase auditing process.

#### Phases of the Diverge-Converge Model

1. **Solo Audit by Lead Auditor**: This initial phase involves a lead auditor, who can be an individual or a team of auditors, selected based on their expertise and experience, represented as a score. The lead auditor holds a pivotal role in the audit process and is highly incentivized. The lead auditor is regarded as the most responsible party in the audit process and is involved in all phases. We expect the protocols build a long term relationship with the lead auditor for future audits.

2. **Public Epochal Time-Boxed Bug Bounty (PET Bug Bounty in short)**: In this phase, public auditors are encouraged to discover and report vulnerabilities. The bug bounty is time-boxed and open to all, with no limit on participant numbers.
The bounty consists of multiple epochs, each lasting 8~24 hours. Duplicates are permitted within an epoch, but a later epoch won't reward a bug already submitted in a previous epoch. For duplicate submissions within a single epoch, the quality rating is used to determine the reward.  To prevent premature disclosure, hunters will initially submit just the hash of their findings and the full details are open to the judges only after a block concludes. The findings are published as soon as possible to help hunters avoid duplicate submissions.
The lead auditor and bounty hunters are implicitly in competition, given the dynamic allocation of the reward pool based on findings. The lead auditor is also involved in this phase and is incentivized to continue exploring the protocol to find more vulnerabilities. Although the lead auditor's findings will not be rewarded as they are considered "known issues from Phase 1", their score will be updated accordingly. The dynamic structure of the reward pool and audit score incentivizes the lead auditor to identify more vulnerabilities.

3. **Selective Competition**: The third phase involves a selective competition among top-rated auditors from the previous phases. The main purpose of this phase is to review the mitigations of all the findings from the previous phases. Any new vulnerabilities introduced during the mitigation process should be identified in this phase. The lead auditor and top-performed hunters are invited to participate in this phase. The lead auditor is incentivized to find more vulnerabilities.

4. **Final Review**: The final phase is a review of the entire audit process, including the audit reports and the mitigation process. The lead auditor is encouraged to provide a final system analysis report, which describes the protocol from a security perspective.

![Phases](img/phases.png "Phases")

The name _**Diverge-Converge**_ is inspired by the fact that the audit process starts from a single auditor and diverges into a public bug bounty, then converges back to a small group of auditors and finaly to a single auditor.

#### Objectives of the Proposed Model

The Diverge-Converge Model emphasizes the following objectives:

- **Information Transfer**: Each phase ensures that all relevant information from the previous phase is transferred to the next one. This seamless transfer of insights contributes to a more robust and effective audit. Findings are published as soon as they are identified in the first two phases, allowing the protocol team to begin mitigation immediately. The lead auditor's comments and walkthrough explanation are also published to assist other auditors in subsequent phases. Also the codebase is open to public through the whole process.

- **Optimized Participation**: To maximize auditor incentives, the model aims to minimize the number of participants involved in each phase. Fewer participants not only increase the rewards for auditors but also reduce the overall cost and turnaround time of the audit.

- **Long-Term Engagement**: The model encourages long-term engagement between the client and the lead auditor, with the lead auditor being involved in all phases. This long-term relationship can be beneficial for both parties, as the lead auditor gains a deeper understanding of the protocol, while the client can leverage the auditor's expertise and experience in future audits.

The proposed model is centered on elevating the quality and efficiency of the audit process, providing a structured approach to identifying and resolving issues in the protocol codebase.

## 4.1 Roles and Terminology

The Diverge-Converge Model engages several roles.

- **Client**: The individual or organization that owns the protocol and commissions the audit. The client bears the audit cost (reward pool).
- **Lead Auditor**: The individual or organization that carries out the audit and produces the audit report. The lead auditor is highly incentivized by a fixed percentage of the reward pool and participates in all phases.
- **Bounty Hunter**: The individual or organization that takes part in the bug bounty. The bug bounty is open to all, with no limit on participant numbers. The lead auditor and bounty hunters are implicitly in competition, given the dynamic allocation of the reward pool based on findings. Valid findings are rewarded as long as they are not identified in previous epochs.
- **Contestant**: The individual or organization that participates in the selective competition.
  A small group of auditors, typically 3-5 including the lead auditor, are chosen as contestants based on their performance in previous phases and score. All valid submissions in this time-boxed competition are rewarded.
- **Judge**: The individual or organization that evaluates the findings from all phases. The judge, chosen from a reputable group in the Web3 space, is incentivized by a fixed percentage of the reward pool.
- **Host**: The individual or organization that oversees the audit process. The host sets up the audit process and ensures its timely completion. The host is incentivized by a fixed fee above the reward pool.

The Diverge-Converge Model also involves several terms.

- **Protocol Difficulty**: Starting from the pre-defined formula `difficulty=f(SLOC,complexity)`, where SLOC and complexity are defined by [`solidity-metrics`](https://marketplace.visualstudio.com/items?itemName=tintinweb.solidity-metrics), the Host decides the difficulty score ranging in 0 ~ 1.

- **Exploit Score**: A measure representing the implicit audit quality.
  The exploit score is computed based on the protocol difficulty, the number of findings, the severity of the findings, and the phase of the findings.

  The severity of the findings is categorized into three levels: High Risk, Medium Risk, and Low Risk. The severity of the findings is determined by the Judge, protocol team, and the lead auditor. Note that we don't include Gas saving findings but an additional phase can be added to the end of Phase 3 according to the protocol's preference. See the "Additional Phases" section for more details.

  Severity points are given as High Risk: 10 points, Medium Risk: 2 points, Low Risk: 0.1 point.
  Phase factor is applied as Phase 1: 0.7x, Phase 2: 1x, Phase 3: 1x.

  The exploit score is calculated as follows:
  $ES=C_p*C_d*(N_H*10+N_M*3+N_L)$, where $C_p$ and $C_d$ represent the phase factor and protocol difficulty.

  The idea behind the points by severity is we value an ability to find severe ones than not impactful ones.
  The idea behind the points by phase is it would be easier to find bugs at early phase than at later phase.

  _Example_. If an auditor found H3 M2 L10 in phase 1 and the difficulty is 0.8, the exploit score will be $0.5*0.8*(3*10+2*3+0.1*10)=14.8$.

- **Lead Performance Score**: A measure representing the performance of the lead auditor. Calculated based on the ratio of the lead auditor's exploit score ($ES_L$) to the other auditors' exploit score($ES_P$) for all phases. After the audit is completed, the lead performance score is calculated as $PS=ES_L/ES_P$, capped to [0, 2]. The lead performance score is used to update the auditor score for the lead auditor.

- **Auditor Score**: A measure representing the auditor's expertise and experience. Used to select the lead auditor and the contestants. When all phases are finished, exploit scores are calculated for all auditors involved in the process and the lead performance score is calculated for the lead auditor.

  Finally, the auditor score is updated as follows:
  $AS = AS + ES * (PS-1)$ for the lead auditor
  $AS = AS + ES$ for other auditors.
  We note that the performance score can both increase and decrease the auditor score for the lead auditor because $PS$ is capped to [0, 2].

**NOTE** All formulas and parameters are only for illustration purpose and they are not backed by any data. These need to go through actual experiments and tune.

## 4.2 Phases

### 4.2.1 Phase 1: Solo Audit by Lead Auditor

#### Inputs

The Protocol team should provide the source code repository access along with all supportive documentation (manuals, diagrams, etc.) that could be helpful for the audit. All the inputs are open to the public as well to allow the public auditors to access as early as possible.

#### Duration

The lead auditor provides the Host with an initial estimation of the necessary duration for this phase. The duration tends to be a tight estimate as the next phase will have the same duration, while the lead auditor can win the dynamic pool if he outperforms the public auditors. This estimated duration is denoted as $L_P$. The Host decide the duration finally based on the protocol's complexity and the lead auditor's estimation. Note that this duration estimation is vital, as it affects the total cost of the audit and is usually determined during the negotiation between the Client and the Host.

#### Execution

The first phase is a solo audit by a lead auditor, who could be an individual or a team of auditors. The selection of a lead auditor is generally based on their expertise and experience, represented as an Auditor Score but the Host can also consider other factors such as the lead auditor's availability and the Client's preference.

The lead auditor, engaged in all the phases and playing a key role in the audit process, is heavily incentivized with a fixed guaranteed percentage of the reward pool.

In this phase, the lead auditor's responsibility is to conduct a comprehensive audit, producing an audit report and a system analysis report. The audit process is similar to a traditional solo audit model, with the protocol development team involved in the process to assist the lead auditor in understanding the protocol.

Due to the dynamic structure of the reward pool, the lead auditor is heavily incentivized to conduct a thorough audit, as the more vulnerabilities left undiscovered, the lesser the reward will be. Furthermore, the lead auditor's performance score affects the final auditor score, encouraging them to uncover as many issues as possible.

The entire audit process should be transparent, with findings accessible to anyone as soon as they are identified. This allows the protocol development team to begin mitigation immediately as well.

Once the audit is complete, the lead auditor must deliver the Audit Report V1.0, which contains all the findings and recommended mitigation steps. The protocol team must address all findings (either fix or acknowledge them) and provide the Audit Report V1.1, containing all responses to the lead auditor. The lead auditor checks the mitigation comments from the protocol and publishes the Audit Report V1.2 with his responses to all comments. At this point, phase 1 of the audit is concluded.

#### Judging

The validity and severity of the findings are decided by 2-of-3 votes from the Judge, protocol team, and the lead auditor. Since the findings come from the lead auditor, if either the Judge or the protocol team agrees with the lead auditor, the finding is accepted.

#### Outputs

The outputs of this phase include:

- Audit Report V1.2
  The report contains all findings and recommendations from the lead auditor.
- System Analysis Report V1
  The lead auditor is responsible for writing a brief system analysis report, which describes the protocol from a security perspective.
- Work Repository with all comments from the lead auditor
  Auditors normally leave comments to facilitate their understanding and mark the process. This is a valuable asset that can greatly assist other auditors. The lead auditor is encouraged to leave comments in a kind of standard format to help other auditors.
- Video recording of the protocol walkthrough/brainstorm/QA by the lead auditor
  Once the initial audit report V1.0 is delivered, the Host arranges a session in which the lead auditor explains the protocol and answers questions from other auditors if any. This session is recorded and published to assist other auditors in subsequent phases.

### 4.2.2 Phase 2: Public Epochal Time-Boxed Bug Bounty

#### Inputs

All outputs from Phase 1 are transferred to Phase 2. Additionally, a communication channel is established between the protocol team and the public auditors to facilitate dialogue.

#### Duration

This phase is a public epochal time-bound bug bounty. The duration is typically the same as the duration allotted to the lead auditor, ensuring that the public auditors have ample time to review the protocol and identify vulnerabilities. As they begin with the lead auditor's comments, walkthrough explanation, and the audit report, this time is expected to be sufficient. We denote the bounty duration as $L_B$ and by default, we assume $L_B = L_P$. The Host can adjust the bounty duration if necessary according to various factors such as the protocol's complexity.

#### Execution

Any public auditor can participate in this phase without any participant limit.

Different from other public bug bounty models, this phase is strictly time-boxed and consists of multiple epochs, each lasting 8~24 hours. The duration of each epoch is determined by the Host, with the default assumption of 8 hours. The Host can adjust the epoch duration if necessary.

Duplicate submissions are permitted within an epoch, but a later epoch won't reward a bug already submitted in a previous epoch. For duplicate submissions within a single epoch, the quality rating (granted by the Judge) is used to determine the reward. The reason for allowing duplicates within an epoch is to encourage more hunters to submit their findings because they have a chance to win the reward even if they are not the first to find the bug. Leveraging the quality rating to "sort" the findings is to ensure that the submissions are of high quality and the reward is allocated to the most deserving hunter.

To prevent premature disclosure, hunters will initially submit just the hash of their findings and the full details are open to the judges only after a block concludes. The findings are published as soon as possible to help hunters avoid duplicate submissions.

The judgement process is transparent and allows for an appeal from auditors if they disagree with the judges. To aid judges in understanding the findings, auditors are strongly encouraged to provide a proof of concept (PoC). In this phase, only the High and Medium risk findings are considered.

Valid findings are published on the finding board as soon as they are identified, allowing the protocol team to initiate mitigation immediately.

The lead auditor is also involved in this phase and is incentivized to continue exploring the protocol to find more vulnerabilities. Although the lead auditor's findings will not be rewarded as they are considered "known issues from Phase 1", their score will be updated accordingly. The dynamic structure of the reward pool and audit score incentivizes the lead auditor to identify more vulnerabilities.

By the dynamic structure of the reward pool, the public auditors are incentivized enough to conduct a thorough audit. On the other hand, it is likely that there are few vulnerabilities left undiscovered assuming the lead auditor has done a good job and this gives a chance for the public auditors to win the high reward with a single submission.

Once the bounty period is over (all epochs are finished and judged), the Host delivers the Audit Report V2.0, containing all findings and recommended mitigation steps. The protocol team must address all findings (either fix or acknowledge them), and deliver the Audit Report V2.1, containing all responses to the findings.

This phase does not have a mitigation review process; this will be conducted in the next phase.

**NOTE:** Public auditors are encouraged to submit any findings that arise after the bounty period. These findings will be reviewed at the end of Phase 3 and, if not covered elsewhere, will be rewarded as part of the bug bounty pool.

#### Judging

The validity and severity of the findings are determined by a 2-of-3 votes among the Judge, protocol team, and the lead auditor. The Host may assist in triaging the findings and aiding the Judge in decision-making if necessary. Notably, the lead auditor, despite potential conflicts of interest, is not the final decision maker.

#### Outputs

The output of this phase is the Audit Report V2.0, containing all findings.

### 4.2.3 Phase 3: Selective Competition

This phase is primarily focused on reviewing the mitigations of all the findings from the previous phases. Any new vulnerabilities introduced during the mitigation process should be identified in this phase.

#### Inputs

All outputs from Phases 1 and 2 are transferred to Phase 3.

A small group of auditors, typically 3-5 including the lead auditor, are chosen as contestants based on their performance in the earlier phases and their auditor score.

A new communication channel is opened between the protocol team and the contestants.

#### Duration

This phase is a time-bound competition. The Host, in consultation with the lead auditor, estimates the necessary duration for this phase, typically recommended to be between 3 to 7 days. We denote the contest duration as $L_C$, with a default assumption of $L_C = 5$. The Host can adjust the contest duration if necessary.

#### Execution

The chosen contestants review the mitigated protocol and aim to find any additional vulnerabilities. The findings are not limited to mitigated issues, and contestants are encouraged to find any vulnerabilities in the protocol. All severity levels are considered in this phase.

The lead auditor continues their involvement in this phase, and is incentivized to find more vulnerabilities. The lead auditor's findings are rewarded as part of the contest pool and will affect their performance score.

After the contest concludes, a judging period commences during which the judges review all findings from the contestants and the lead auditor. They determine the validity and severity of the findings. The judging process is transparent, allowing auditors to appeal their findings.

Once judging begins, any additional submissions (after the public bounty time has concluded) are published, and the contestants collaborate with the judges to evaluate these findings. Contestants have an interest in this process as these findings will influence the final distribution of the reward pool.

Once judging concludes, the Host delivers the Audit Report V3.0, containing all findings and recommended mitigation steps. The protocol team must address all findings (either fix or acknowledge them), and delivers the Audit Report V3.1, containing all responses to the findings. The lead auditor then delivers Audit Report V3.2, containing responses to mitigation comments.

#### Judging

The validity and severity of the findings are determined by a 2-of-3 majority among the Judge, protocol team, and the lead auditor. Judges are incentivized to complete the judging process in a timely manner. We denote the judging duration as $L_J$, with a default assumption of $L_J = 3$. The Host can adjust the judging duration if necessary. It's noteworthy that this contest judging differs from other judgments in that it involves a smaller number of findings.

#### Outputs

The output of this phase is the Audit Report V3.2, containing all findings and comments regarding the fixes.

### 4.2.4 Phase 4: Final Review

The Host reviews the entire process and generates the final audit report. The lead auditor is encouraged to revise the system analysis report based on the deeper understanding of the protocol acquired during the process. We denote the duration of this phase as $L_F$ with a default assumption of $L_F = 2$.

## 4.3 Reward Pool Structure

The Client bears the cost of the audit, referred to as the reward pool, and the Host organizes the structure of the reward pool. The reward pool structure is dynamically designed to adequately incentivize the auditors and maximize the quality of audits. The Host is assumed to charge a fixed fee in addition to the reward pool.

<img src="img/pool.png" alt="Pool" width="80%"/>

- **Lead Auditor**: The lead auditor is greatly incentivized with a fixed guaranteed percentage ($P_L\%$) of the reward pool. It is recommended that $20 \leq P_L \leq 50$.
- **Bug Bounty**: A fixed percentage ($P_B\%$) of the reward pool is reserved for the bug bounty and is used to incentivize the public to identify vulnerabilities in the protocol **AFTER** the mitigation of findings from the first phase. It is recommended that $P_L \leq P_B < 50$. If no vulnerabilities are found during the bug bounty phase, the bug bounty pool is distributed to the lead auditor.
- **Dynamic Pool**: A fixed percentage ($P_D\%$) of the reward pool is reserved as a dynamic pool. This pool will be rewarded to the lead auditor or the bounty hunters based on the lead auditor's performance score. It is recommended that $P_D = 50 - P_L$.
- **Selective Competition Pool**: A fixed percentage ($P_C\%$) of the reward pool is reserved for the selective competition pool and is used to incentivize the contestants to identify vulnerabilities in the protocol **AFTER** the mitigation of findings from the second phase. It is recommended that $10 \leq P_C \leq 15$. As this phase allows for LOW risks, this pool is likely always to be distributed to the contestants.
- **Judge**: The judge is involved in all phases and incentivized by a fixed guaranteed percentage ($P_J\%$) of the reward pool. It is recommended that $5 \leq P_J \leq 15$.

### Default Pool Structure

The default pool structure is assumed to be $P_L=30$, $P_B=30$, $P_D=20$, $P_C=10$, $P_J=10$.

## 4.4 Process Overview

The overall process is as follows, assuming the default pool structure.

| Phase                    | Reward     | Participant       | Duration   | Result                                                            |
| ------------------------ | ---------- | ----------------- | ---------- | ----------------------------------------------------------------- |
| Solo Audit            | 30% (+20%) | Lead Auditor      | $L_P$ days | Audit Report V1.2, System Analysis Report V1, Diagrams, Walkthrough |
| PET Bug Bounty | 30% (+20%) | Public            | $L_B$ days | Audit Report V2.0                                                   |
| Selective Contest        | 10%        | Selected Auditors | $L_C$ days | Audit Report V3.1                                                   |
| Final Review             | 0          | Lead Auditor      | $L_F$ days | Final Audit Report, Final System Analysis Report                  |

## 4.5 Estimation of Time and Cost

The entire process's cost can be estimated starting from the cost of the lead auditor and the duration of their engagement.

As previously mentioned, the lead auditor estimates the duration for Phase 1 as $L_P$ days, and the Host sets the duration for the remaining phases as $L_B$, $L_C$, $L_F$ days. Due to the dynamic pool structure, the lead auditor is motivated to estimate the duration accurately.

Let's assume the lead auditor's daily cost for 100% dedication is $C_L$.

We estimate the lead auditor's dedication for each phase as follows: $D_P = 100\%$, $D_B = 50\%$, $D_C = 100\%$, $D_F = 0\%$.

The total cost for the lead auditor can be estimated as $C_L * (L_P * D_P + L_B * D_B + L_C * D_C) = C_L * (L_P + L_B/2 + L_C)$.

Assuming the lead auditor outperforms the public auditors, the lead auditor will receive $P_L + P_D\%$ of the reward pool (50% for the default structure). So, we can estimate the entire reward pool (i.e., the total cost) as $C_L * (L_P + L_B/2 + L_C) * 100 / (P_L + P_D)$.

The total turnaround time can be estimated as $L_P + L_B + L_C + L_J + L_F$ days.

_Example_
Assuming the lead auditor's engagement cost is $C_L = 2000\$$ per day and he estimated the duration for Phase 1 as $L_P = 10$ days. With the default pool structure and the duration of other phases as $L_B = L_P = 10$, $L_C = 5$, the total cost would be $2000 * (10 + 10/2 + 5) * 100 / (30 + 20) = \$80,000$, and the total turnaround would be approximately a month probably including the mitigation turnaround.

## 4.6 Additional Phases
The proposed model is flexible and can be adjusted to suit the protocol team's needs.
For instance, the Client may choose to add an additional phase to the audit process to address gas optimization issues.
The Client might also want to have another round of review from a reputable audit firm after the completion of the Diverge-Converge Model to get advice on the system architecture and/or deployment. This additional phase can be added to the end of Phase 3.
Theoretically, the more rounds of review, the better the quality of the audit. However, the cost of the audit will increase accordingly. The Client should carefully consider the trade-off between cost and quality.

## 4.7 Summary

In this section, we proposed a multi-phase audit model, the Diverge-Converge Model, which strives to maximize audit quality by incentivizing auditors appropriately and ensuring the protocol codebase undergoes at least three audit phases. The proposed model has several advantages over existing audit models:

- The protocol codebase undergoes at least three audit phases. This sequence, connected via a set of incentives and disincentives, is not equivalent to three separate audits; rather, it creates a potent competition among auditors.
- The model optimizes audit quality by properly incentivizing auditors. In particular, the lead auditor is highly incentivized, securing top-tier engagement critical for high-quality audits. Moreover, the dynamic reward pool structure also incentivizes public auditors. Depending on performance, a single public auditor could earn more than the lead auditor.
- The model is efficient. Minimizing the number of participants in each phase helps reduce the cost and time of the audit. Moreover, the transfer of all information from one phase to the next increases audit process efficiency. Findings are published as soon as possible, enabling the protocol team to start mitigation right away.
- The model's core is transparent and fair. Throughout the audit, auditors can communicate with each other, the protocol team, and the judges. A 2-of-3 decision-making process is used throughout, enhancing the fairness of the process.
- The lead auditor's extended engagement helps the protocol team build a long-term relationship with them.
- The model is flexible and can be adjusted to suit the protocol team's needs. For instance, Phase 2 could be performed by a limited number of auditors instead of a public community. Phase 1 could be performed as a traditional solo audit with a team of auditors rather than a single auditor.

# 5. Conclusion

This paper presents an in-depth exploration and critique of existing audit models, resulting in the proposal of a new, innovative model known as the Diverge-Converge Model. This model is crafted with the intention of maximizing the quality of audits, a critical aspect in the realm of Web3 space. By strategically incentivizing auditors and ensuring that the protocol codebase goes through a minimum of three comprehensive auditing phases, the model aims to enhance the audit quality significantly.

The unique strength of the Diverge-Converge Model lies in its ability to foster robust competition among auditors, backed by a dynamic reward pool structure. This structure ensures the engagement of top-tier auditors and encourages their continuous involvement throughout the process. Furthermore, the model emphasizes transparency and fairness, promoting efficient communication among auditors, the protocol team, and judges.

The Diverge-Converge Model introduces a novel approach to auditing in the Web3 space, addressing the shortcomings of existing models while presenting its unique advantages. As Web3 continues to grow and evolve, this model could serve as a new standard, guiding the way towards more effective and high-quality audits. Further experiments and implementations of this model will provide more insights and potential enhancements, contributing to the continuous improvement and refinement of auditing practices in the Web3 space.

# 6. Acknowledgements
We extend our sincere gratitude to the entire [Cyfrin](https://www.cyfrin.io/) team for their invaluable contributions and advice. Their insights and expertise were instrumental in refining and enhancing our ideas. Additionally, special thanks to [Josselin Feist](https://twitter.com/Montyly) from [Trail of Bits](https://www.trailofbits.com/) for reviewing the paper and offering his valuable insights and advice. Their combined collaboration played a pivotal role in the development and perfection of this work.


# 7. References

- [1] [DeFi Security Summit 2023 - Session 16: Audits Conventional vs Community Panel](https://www.youtube.com/watch?v=_Yul_fHUjr8&list=PL5r4vTR0gHj5JL62S9R0umY64ue6mfQhd&index=43)
- [2] [Code4rena](https://code4rena.com/)
- [3] [Sherlock](https://sherlock.xyz/)
- [4] [SpearbitDAO](https://spearbit.com/)
- [5] [AuditOne](https://auditone.io/)
- [6] [Solidity Metrics](https://marketplace.visualstudio.com/items?itemName=tintinweb.solidity-metrics) by [Consensys](https://www.consensys.net/)
