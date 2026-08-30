---
layout: single
title: "Tips for Algorithm Research"
permalink: /guides/algorithm-research/
author_profile: true
---

[← Back to Guides](/guides/)

## Types of Research Tasks

### T1: Improving an existing algorithm

A specific algorithm—such as Dijkstra’s shortest-path algorithm, PageRank, or SGD for optimization—is important and widely used. The research goal is to improve its performance, including speed, accuracy, scalability, robustness, or memory efficiency.

- **Example:** Speeding up the Fast Fourier Transform for large-scale data.
- **Example:** Making gradient descent methods more stable in non-convex optimization.

### T2: Designing a solution for a problem

Given a well-defined problem—such as detecting communities in networks, scheduling tasks, or learning embeddings—we want to find or design an algorithm to solve it.

- **Example:** Creating an algorithm for efficient graph coloring.
- **Example:** Designing a robust algorithm for image denoising.

---

## Common Procedure for Both Tasks

Regardless of whether you are working on T1 or T2, the following fundamental procedure should guide your research:

1. **Formulate the design or decision space**
   - Define the problem clearly, using a formal mathematical statement if possible.
   - Identify the canonical framework or standard algorithmic approaches used for it.
   - Ask: What assumptions are typically made? What input and output structures are expected?
2. **Identify aspects for improvement through literature review and gap analysis**
   - **For T1:** Identify where the current algorithm struggles. Is it too slow for large inputs? Does it fail under noise? Is it hard to parallelize?
   - **For T2:** Identify why existing solutions are unsatisfactory. Do they rely on unrealistic assumptions? Do they scale poorly? Do they fail in edge cases?
3. **Formulate clear research questions**
   - What specific property are you trying to improve: time, memory, robustness, or accuracy?
   - What trade-offs are you willing to accept?

---

## General Research Approaches

Algorithmic research can be pursued through two complementary lenses:

- **Top-down:** empirically driven, moving from an initial idea toward justification.
- **Bottom-up:** theory driven, moving from a framework toward an algorithm.

### Top-down Approach

This approach is common in many recent papers.

1. **Generate working ideas**
   - Use intuition, heuristics, or inspiration from related problems.
   - Do not worry too much about theory at the beginning; first find something that seems to work.
2. **Test quickly through experiments**
   - Run small-scale experiments to validate feasibility.
   - Benchmark against standard datasets or synthetic test cases.
3. **Refine and strengthen the idea**
   - Analyze failures and edge cases.
   - Improve the approach based on observed patterns.
4. **Support it with theory when possible**
   - Develop proofs, bounds, or formal justification once you have empirical evidence.
   - Even partial theoretical insights under specific assumptions can make the result more convincing.

**Example:** Many deep learning optimizers, including Adam and RMSProp, were discovered through empirical adjustments before formal convergence analyses were developed.

### Bottom-up Approach

1. **Establish a theoretical framework**
   - Define the mathematical objects and constraints of the problem.
   - Use tools from complexity theory, optimization, probability, or combinatorics.
2. **Analyze the limitations of existing methods**
   - Prove lower bounds or impossibility results, or identify structural weaknesses.
   - Use counterexamples to show why existing methods fail.
3. **Identify the key quantities that matter**
   - Examples include the spectral gap in graph algorithms, Lipschitz constants in optimization, and condition numbers in linear algebra.
4. **Design algorithms guided by theory**
   - Use the framework to derive new approaches.
   - Translate theoretical insights into implementable algorithms.

**Example:** The development of approximation algorithms for NP-hard problems is primarily bottom-up: first analyze the complexity, then design algorithms with provable guarantees.

---

## Comparison of Approaches

| Approach | Advantages | Limitations |
| --- | --- | --- |
| Top-down | Low initial cost; faster prototyping | Depends heavily on intuition or luck; can be hard to generalize; is less convincing without theory |
| Bottom-up | Systematic; provides guarantees and strong justification; produces durable and reusable results | Higher start-up cost; slower path to practical algorithms; requires a strong theoretical background |

---

## My Take

Many important algorithms, especially in machine learning, are discovered through the top-down approach. I personally believe the bottom-up approach is more principled, systematic, and meaningful. In practice, however, research is often not a binary choice between top-down and bottom-up. The most effective strategy is often a hybrid approach.

### Practical Tips

1. **Overlap effort**
   - Let experiments run while you explore theoretical frameworks.
   - Use experimental failures to guide which assumptions or theorems are worth studying.
2. **Iterate**
   - Move back and forth between empirical intuition and theoretical justification.
   - Each side strengthens the other: theory explains why an idea works, while experiments show whether the theory applies in practice.
3. **Be explicit about trade-offs**
   - When improving an algorithm, state what you sacrifice, such as speed versus accuracy or memory versus robustness.
   - When designing a new algorithm, clarify the assumptions under which it works best.
4. **Document your process**
   - Keep track of failed approaches; they are often useful later.
   - Organize results so you can clearly tell the story of your research.

---

## Common Pitfalls to Avoid

1. **Vague problem statements:** Always define the problem as clearly and formally as possible.
2. **Being unaware of related work:** Reinventing the wheel wastes time and weakens credibility.
3. **Neglecting negative results:** Failures are informative and can guide both theory and experiments.

[← Back to Guides](/guides/)
