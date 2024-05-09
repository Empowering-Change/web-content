---
title: "The age-old concept of GIGO (Garbage In, Garbage Out)!"
seoTitle: "Understanding GIGO: Impact on Data Quality"
seoDescription: "Explore how the GIGO principle impacts AI, perpetuating errors and biases through flawed input and output cycles"
datePublished: Thu May 09 2024 05:32:08 GMT+0000 (Coordinated Universal Time)
cuid: clvyta3ws000008lae2cu2kai
slug: the-age-old-concept-of-gigo-garbage-in-garbage-out
tags: ai, artificial-intelligence, programming, augmented-intelligence

---

In the context of artificial intelligence, machine learning, and data analysis, GIGO refers to the idea that the quality of the output is only as good as the quality of the input. If the input data is flawed, biased, or inaccurate, the resulting output will likely be flawed, biased, or inaccurate as well.

Now, regarding the question of whether GIGO is self-referential and self-perpetuating:

**Self-referential:** Yes, GIGO can be self-referential in the sense that the output of a flawed system can be used as input for another system, perpetuating the errors and biases.

*As Al systems become more capable, we would like to enlist their help to supervise other Als. We experiment with methods for training a harmless Al assistant through self-improvement, without any human labels identifying harmful outputs. The only human oversight is provided through a list of rules or principles, and so we refer to the method as 'Constitutional Al'. The process involves both a supervised learning and a reinforcement learning phase. In the supervised phase we sample from an initial model, then generate self-critiques and revisions, and then finetune the original model on revised responses. In the RL phase, we sample from the finetuned model, use a model to evaluate which of the two samples 1s better, and then train a preference model from this dataset of Al preter-ences. We then train with RL using the preference model as the reward signal, i.e. we use 'RL from AI Feedback' (RLAIF). As a result we are able to train a harmless but non-evasive Al assistant that engages with harmful queries by explaining its objections to them. Both the SL and RL methods can leverage chain-of-thought style reasoning to improve the human-judged performance and transparency of Al decision making. These methods make it possible to control Al behavior more precisely and with far fewer human labels.*

This is evident in the first excerpt, the abstract of Anthropic’s “Constitutional AI” paper, where biases in AI models can result from poor understanding of the issues being modeled, and these biases can be hard to spot and perpetuate over time.

**Self-perpetuating:** Yes, GIGO can also be self-perpetuating, as the flawed output can be used to train or update other systems, creating a cycle of error and bias propagation.

*Figure 2 caption: "We show harmlessness versus helpfulness Elo scores (higher is better, only differences are meaningful) computed from crowdworkers' model comparisons for all 52B RL runs. Points further to the right are later steps in RL training. The Helpful and HH models were trained with human feedback as in \[Bai et al., 2022\], and exhibit a tradeoff between helpfulness and harmlessness. The RL-CAI models trained with Al feedback learn to be less harmful at a given level of helpfulness. The crowdworkers evaluating these models were instructed to prefer less evasive responses when both responses were equally harmless; this is why the human feedback-trained Helpful and HH models do not differ more in their harmlessness scores."*

This is demonstrated in the second exceprt from the same foundational paper, where the authors describe a method for training a harmless AI assistant through self-improvement, without human labels identifying harmful outputs. While this approach aims to mitigate the GIGO problem, it still relies on the AI system's ability to evaluate and revise its own output, which can be prone to errors and biases.

In summary, GIGO can be both self-referential and self-perpetuating, as flawed input can lead to flawed output, which can then be used as input for other systems, perpetuating the errors and biases.

# The Bigger Picture

Why are we so fearful of statistical machines synthesizing our own human knowledge? Sounds like humanity should have a conversation with our therapist… God/Allah/Ganesh/FSM/{}, are you listening? Maybe it’s time we confess that we haven’t learned so much since all those creation stories about being kicked out of paradise.