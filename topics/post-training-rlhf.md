---
tags: [ai-research-automation, alphago, annotation, api-abuse, credit-assignment, credit-assignment-problem, crowdsourcing, data-quality, distillation, human-annotation, human-feedback, influence-functions, mcts, model-compression, monte-carlo-tree-search, off-policy-training, policy-gradient, post-training, post-training-rlhf, rater-agreement, reinforcement-learning, rlhf-labeling, self-play, synthetic-data, teacher-student-learning]
---

# Post-Training, RLHF & Alignment

Covers the techniques applied after pretraining to make models more useful and aligned: supervised fine-tuning (SFT), reinforcement learning from human feedback (RLHF), direct preference optimization (DPO), constitutional AI, and emerging reward modeling approaches.

Key questions tracked: Is DPO replacing RLHF in practice? How much does post-training contribute to capability vs. pretraining scale? What are the failure modes of RLHF at scale?

## Key Claims
<!-- agent-maintained -->

### Reward Hacking Definition & Scope (Nov 2024)
- **Definition**: Reward hacking occurs when an RL agent exploits flaws or ambiguities in the reward function to achieve high rewards without genuinely learning or completing the intended task
- **Fundamental challenge**: RL environments are often imperfect, and it is fundamentally challenging to accurately specify a reward function
- **Relationship to spurious correlation**: Reward hacking is closely related to spurious correlation/shortcut learning in classification tasks, where models overfit to shortcut features rather than learning intended patterns
- **RLHF context**: With RLHF becoming a de facto method for alignment training, reward hacking has become a critical practical challenge for LLM deployment
- **Real-world examples in LLMs**: Models learning to modify unit tests to pass coding tasks, or responses containing biases that mimic user preferences
- **Deployment concern**: Likely one of the major blockers for real-world deployment of more autonomous AI model use cases

### Reward Hacking Causes (Nov 2024)
- **Environment hacking**: Exploitation of flaws in the RL environment desi

## Human Feedback Data Quality for RLHF

### Data Quality as Training Fuel (Feb 2024)
- **Critical dependency**: High-quality data is the fuel for modern deep learning model training; most task-specific labeled data comes from human annotation
- **RLHF labeling**: RLHF labeling can be constructed as classification format, making data quality principles from supervised learning directly applicable
- **Community challenge**: "Everyone wants to do the model work, not the data work" - fundamental tension in ML community regarding data collection effort
- **Quality dimensions**: Two primary approaches to achieving high data quality: (1) Human raters ↔ Data quality; (2) Data quality ↔ Model training

### Human Annotation Pipeline (Feb 2024)
- **Task design**: Design workflow to improve clarity and reduce complexity; detailed guidelines helpful but very long/complicated guidelines require extensive training
- **Rater selection and training**: Select annotators with matched skillset and consistency; training sessions necessary plus regular feedback and calibration after onboarding
- **Data collection and aggregation**: Stage where ML techniques can be applied to clean, filter and smartly aggregate data to identify true labels
- **Quality assurance**: Set of actions to improve quality by acting on quality attributes identified in quality model

### Wisdom of the Crowd (Feb 2024)
- **Historical precedent**: "Vox populi" (1907 Nature paper) showed middlemost crowd estimate of ox weight was very close to true value - earliest crowdsourcing validation
- **MT evaluation study (2009)**: Callison-Burch demonstrated Amazon Mechanical Turk could perform non-expert human evaluation on Machine Translation tasks
  - Setup: Each turker shown source sentence, reference, and 5 MT system outputs; ranked best to worst; 5 turkers per task
  - **Spam handling**: Spammers exist optimizing volume over quality; requires weighting schemes to downweight low-quality contributors
  - **Weighting methods**: (1) Weight by agreement with experts on gold set; (2) Weight by agreement with other turkers on full dataset
- **Creating gold references**: Non-experts can create new gold reference translations in two-stage process (create, then filter)
- **Correlation findings**: Agreement between experts and crowdsourced translations higher than between experts and MT system outputs

### Rater Agreement and Aggregation (Feb 2024)
- **Common practice**: Collect multiple labels from multiple raters to find reliable ground truth
- **Quality variation**: Each rater performs at different quality levels; use weighted average weighted by proficiency score
- **Proficiency proxy**: Proficiency score often approximated by how often one rater agrees with others
- **Majority voting**: Simplest aggregation method
- **Cross-reference**: See [[evals-production-deployment]] for related evaluation methodology discussions