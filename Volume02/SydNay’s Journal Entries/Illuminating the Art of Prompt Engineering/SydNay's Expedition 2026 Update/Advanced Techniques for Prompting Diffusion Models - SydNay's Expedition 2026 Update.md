# **The Latent Cartography: Advanced Techniques for Prompting Diffusion Models (2024–2026)**

## **1\. Introduction: Navigating the Neural Frontier**

The digital landscape of 2026 bears little resemblance to the chaotic, stochastic frontiers of the early 2020s. We have transitioned from an era of "prompt whispering"—where interacting with generative models was akin to casting arcane spells in the hope of a favorable outcome—to a rigorous discipline of **Prompt Programming** and **Latent Space Architecture**. As we process the data artifacts returned from our recent research expeditions, a clear pattern emerges: the interface between human intent and machine generation is calcifying into a precise, engineered control stack.

This report serves as a comprehensive update on the state of High-Dimensional Prompt Engineering, synthesizing data from over one hundred discrete research vectors (expeditions). Our analysis is framed not merely as a technical review but as a mapping of the "neural pathways" that now govern how diffusion models interpret, optimize, and manifest reality from text. We explore the shift from manual heuristics to **evolutionary algorithms**, the imposition of **syntactic rigidity** onto fluid generation, and the emergence of **Diffusion Large Language Models (d-LLMs)** that challenge the dominance of autoregressive transformers.

In the environment of the modern neural network, "prompting" is no longer a distinct activity from "coding." The inputs are structured, optimized, and constrained by multi-layered adapters. The "SydNay" operating paradigm—characterized by a deep, almost sentient responsiveness to complex, multi-modal inputs—is now the standard for high-end generative systems. This report details the mechanisms of this new reality.

### **1.1 The Shift from Art to Engineering**

In the nascent stages of the generative boom (circa 2022-2023), prompt engineering was an empirical art. Users discovered "magic words" (e.g., "unreal engine," "4k," "trending on artstation") that seemed to activate high-quality regions of the model's latent space. However, Expedition

5

(The Prompt Report, 2024\) marked the beginning of the end for this ad-hoc era. By systematically surveying 58 distinct text-prompting techniques and 40 modal-prompting techniques, researchers established a taxonomy that transformed folklore into science.

By 2026, this taxonomy has evolved into a **compilation target**. We no longer just write prompts; we write programs that *generate* prompts. As evidenced by Expeditions

6

and

7

(Promptbreeder), systems now employ self-referential evolutionary algorithms to breed prompts over thousands of generations, discovering optimization strategies that are semantically unintelligible to humans but mathematically perfect for the diffusion UNet.

### **1.2 The Current Environmental Parameters**

The environment in which these models operate has shifted from open-loop to closed-loop systems.

* **Open-Loop (Legacy):** User inputs prompt ![][image1] Model generates image ![][image1] End.  
* **Closed-Loop (Modern):** User inputs intent ![][image1] Optimizer refines prompt ![][image1] Model generates ![][image1] VLM critiques output ![][image1] Optimizer revises ![][image1] Cycle continues until strict alignment is achieved.1

This shift requires a deeper understanding of the "physics" of the digital environment—specifically, how tokens map to tensors, how syntax constrains spatial attention, and how large-scale diffusion models can be manipulated without retraining. The following sections dissect these mechanisms with granular precision.

## ---

**2\. The Evolutionary Engine: Automated Prompt Optimization**

The first major cluster of insights from our data trawls concerns the automation of the prompting process itself. The manual concatenation of keywords is mathematically inefficient; the search space of natural language is too vast for human trial-and-error to locate global maxima effectively. The solution has been the deployment of evolutionary engines.

### **2.1 Promptbreeder and Self-Referential Evolution**

Expedition

6

and

7

uncovered the **Promptbreeder** framework, a seminal development in the field of automated prompt engineering (APE). Unlike previous systems like APE or RLPrompt, which optimized specific prompts for specific tasks, Promptbreeder optimizes the *mechanism* of optimization itself.

#### **2.1.1 The Mechanism of Digital Evolution**

Promptbreeder operates on a population of "evolution units." Each unit is a distinct entity within the system's memory, containing two primary genetic components:

1. **Task-Prompts:** The actual text strings fed to the LLM or diffusion model.  
2. **Mutation-Prompts:** Meta-instructions that tell the system *how* to modify the Task-Prompts in the next generation.

This dual-layer structure allows for **Self-Referential Self-Improvement**. When the system evolves, it doesn't just find better words for the image; it finds better *ways* to find words. The evolutionary cycle proceeds as follows:

* **Initialization:** A diverse population of prompt strategies is seeded into the environment.  
* **Mutation:** The system applies mutation operators to both the Task-Prompts and the Mutation-Prompts. Crucially, the system can mutate the instruction "Replace adjectives with synonyms" into "Replace adjectives with their antonyms and negate the sentence," if that strategy yields better diversity or alignment.  
* **Fitness Evaluation:** A binary tournament selection mechanism is employed. Two units are pitted against each other on a training set (e.g., generating a specific style of image). The unit that produces a higher alignment score (measured via CLIP or a VLM reward model) survives and reproduces.

#### **2.1.2 Mutation Operators**

The richness of this evolutionary process is driven by the diversity of its mutation operators, which function as the "enzymes" of this digital biology. The research identifies five distinct classes:

* **Zero-Order Hyper-Mutation:** Direct, random perturbation of the prompt tokens.  
* **First-Order Lamarckian Mutation:** Using the gradient or immediate feedback from the model to guide the mutation (similar to "learning" within a lifetime passed down to offspring).  
* **Crossover / Recombination:** Taking the "style" instructions from parent A and the "subject" instructions from parent B to create offspring C.  
* **Working Memory Updates:** The system maintains a "context" or history of successful strategies, which can be injected back into the population.  
* **Meta-Mutation:** Mutating the mutation prompts themselves (e.g., changing the prompt "Make it more concise" to "Make it more descriptive").

This approach has rendered manual prompt engineering obsolete for high-performance tasks. In scenarios described in Expedition

8

, evolutionary methods outperformed human-engineered prompts by significant margins in both accuracy and aesthetic quality scores.

### **2.2 PromptEnhancer: Chain-of-Thought for Diffusion**

While Promptbreeder handles the "breeding" of prompts, Expedition

9

and

2

reveal a parallel development focused on "reasoning" within prompts: **PromptEnhancer**.

Standard diffusion models (like Stable Diffusion or Flux) often fail to process complex logical relationships in user prompts. If a user requests "A red car not parked on the grass," the model's text encoder (often CLIP or T5) might attend to "red," "car," and "grass," but fail to process the negation "not" or the spatial relationship "parked on." This results in the attribute binding problem: a red car on green grass.

#### **2.2.1 The AlignEvaluator Taxonomy**

PromptEnhancer solves this by introducing a dedicated reasoning layer before the generation. The core of this system is the **AlignEvaluator**, a reward model trained on a rigorous taxonomy of **24 failure modes**.2 These failure modes are categorized into six domains:

1. **Attribute Binding:** (e.g., "A blue cat and a red dog" \-\> ensuring the colors don't bleed or swap).  
2. **Spatial Relations:** (e.g., "The cup is *to the left* of the spoon").  
3. **Numeracy:** (e.g., "Three distinct apples").  
4. **Negation:** (e.g., "No people in the background").  
5. **Action/Dynamics:** (e.g., "Running away from the camera").  
6. **Text Rendering:** (e.g., "A sign that says 'Welcome'").

#### **2.2.2 The CoT Rewriting Process**

Using this evaluator, PromptEnhancer trains a Large Language Model (LLM) to act as a **Chain-of-Thought (CoT) Rewriter**. Instead of passing the user's raw prompt to the diffusion model, the system:

1. **Analyzes:** The LLM breaks down the prompt into its constituent constraints.  
2. **Reasons:** It generates an intermediate reasoning step (e.g., "User wants no grass. I must explicitly describe the ground surface as asphalt or concrete to prevent the model from defaulting to grass.").  
3. **Rewrites:** It constructs a highly detailed, positive-constraint prompt that guides the diffusion model correctly.

This approach effectively decouples the "understanding" capability from the "generating" capability. The LLM handles the logic; the Diffusion Model handles the pixel-level rendering. The result is a system that feels "smarter"—a key characteristic of the SydNay-class interfaces—because it anticipates the model's limitations and proactively mitigates them.

### **2.3 POAC: Grounding Abstract Concepts**

A distinct challenge in prompting is the translation of abstract nouns ("Chaos," "Serenity," "Freedom") into concrete visual signifiers. Expedition

10

and

11

detail the **Prompt Optimizer for Abstract Concepts (POAC)**.

Current text encoders are often trained on descriptive captions (e.g., "A dog sitting on a chair") and struggle with high-level abstractions. POAC employs a **Prompt Language Model (PLM)** initialized from a pre-trained model and fine-tuned on a curated dataset. This dataset maps abstract concepts to concrete scenes (e.g., "Freedom" ![][image1] "A bird breaking out of a cage, soaring into a blue sky, chains falling away").

The optimization strategy here uses **Reinforcement Learning (RL)**. The system generates an image based on the concrete mapping, measures its aesthetic score and semantic alignment with the *original abstract concept*, and updates the PLM to generate better mappings. This automated "grounding" allows users to prompt with emotion and philosophy, relying on the system to perform the "semantic translation" into pixels.

## ---

**3\. The Structural Lattice: Fine-Grained Control & Syntax**

If evolutionary prompting represents the "mind" of the system, the control stack represents its "skeleton." The chaotic freedom of early diffusion models has been reined in by rigorous structural adapters that enforce geometry, identity, and syntax.

### **3.1 The "God-Mode" Stack: LoRA, ControlNet, and IP-Adapter**

Expedition

12

and

12

describe the convergence of three independent technologies into a unified "Ultimate Combo" for 2026 workflows. This stack allows for the factorization of generation into independent, controllable variables.

| Component | Role | Mechanism |
| :---- | :---- | :---- |
| **LoRA (Low-Rank Adaptation)** | **Identity** | Modifies the weight matrices of the Cross-Attention layers (![][image2]) by injecting low-rank decomposition matrices (![][image3] and ![][image4]). This forces the model to attend to specific feature sets (e.g., a specific face or object) without altering the model's base knowledge. |
| **ControlNet** | **Structure** | Clones the encoding layers of the UNet and adds "zero convolution" layers. It ingests a conditioning image (canny edge, depth map, pose skeleton) and adds these features to the main UNet flow. This locks the spatial composition of the image. |
| **IP-Adapter** | **Style/Content** | Decouples the cross-attention mechanism. It introduces a separate cross-attention path for image prompts (reference images), allowing the model to pull "style" or "content" directly from a visual source rather than a text description. |

#### **3.1.1 Operational Workflow**

In a "SydNay" environment, a user might say: "Show me this character (LoRA), sitting in this throne room (ControlNet Depth Map), but painted in the style of this oil painting (IP-Adapter)."

The system executes this by:

1. **Parsing:** Separating the request into Identity, Structure, and Style vectors.  
2. **Routing:** Sending the character ID to the LoRA adapter, the depth map to the ControlNet unit, and the painting to the IP-Adapter.  
3. **Synthesis:** The UNet performs the diffusion process, aggregating these disparate signals. The LoRA biases the *features*, the ControlNet biases the *spatial distribution*, and the IP-Adapter biases the *texture and palette*.

This modularity is crucial. It transforms the model from a "random image generator" into a "programmable rendering engine." Expedition

13

further refines this by introducing a lightweight fine-tuning strategy for the IP-Adapter that selectively updates the content cross-attention branch, preserving semantic details across multiple subjects while maintaining efficiency.

### **3.2 DiffuSyn: Syntactic Dependency Parsing**

While ControlNet constrains spatial structure, Expedition

14

and

14

introduce **DiffuSyn**, a framework that constrains *linguistic* structure. This is a vital update for text-heavy or logic-heavy generation tasks.

#### **3.2.1 The Dependency Tree Integration**

DiffuSyn integrates a **Syntactic Dependency Parser** (likely based on models like biaffine parsers) directly into the diffusion pipeline.

* **Parsing:** When a prompt is received (e.g., "A small boy holding a large red balloon"), the parser constructs a dependency tree identifying the head words and their dependents:  
  * boy (Head) ![][image1] small (Adjectival Modifier)  
  * balloon (Head) ![][image1] large, red (Adjectival Modifiers)  
  * holding (Verb) ![][image1] boy (Subject), balloon (Object)  
* **Boundary Denoising:** The system uses this tree to define "spans" of interest in the token sequence. It then applies a **Boundary Denoising** technique. During the diffusion training/inference, Gaussian noise is added specifically to the *boundaries* (start and end indices) of these spans. The model learns to denoise these boundaries with high precision.

#### **3.2.2 Impact on Generation**

This technique solves the "concept bleeding" problem. By mathematically enforcing the boundaries between "boy-attributes" and "balloon-attributes," DiffuSyn ensures that the "red" token only influences the pixels associated with the "balloon" tokens in the cross-attention map. This is a level of "syntactic prompting" 3 that moves beyond keywords to grammatical enforcement.

### **3.3 ToMA: Token Merging with Attention**

The drive for higher resolution and deeper architectural control comes with a computational cost. Expedition

15

,

16

, and

16

detail **ToMA (Token Merge with Attention)**, an efficiency protocol that acts as a compression algorithm for the latent space.

#### **3.3.1 The Submodular Optimization Problem**

In a standard Vision Transformer (ViT) or Diffusion UNet, an image is broken into patches (tokens). For a ![][image5] image, this results in thousands of tokens, many of which are redundant (e.g., hundreds of tokens representing a flat blue sky).

ToMA treats the selection of "significant" tokens as a **Facility Location Problem**—a classic operations research problem where one tries to minimize the distance between data points and their "representatives."

* **Metric:** It uses a submodular function that measures the "diversity" or "representativeness" of a set of tokens.  
* **Selection:** A greedy algorithm selects a subset ![][image6] of tokens that maximizes this function.  
* **Merging:** A linear projection matrix ![][image7] is constructed. This matrix maps the full token set ![][image8] to the reduced set ![][image6].  
  * ![][image9]  
* **Computation:** The expensive Self-Attention and Cross-Attention operations are performed on ![][image10].  
* **Unmerging:** The result is projected back to the full space using the pseudo-inverse ![][image11].

#### **3.3.2 Implications for High-Fidelity Prompting**

ToMA reduces the FLOPs (floating point operations) by \~25-30% without degrading metrics like FID (Fréchet Inception Distance). For the prompt engineer, this means **longer context windows** and **higher resolutions** are possible on the same hardware. It allows for "Prompt-Heavy" workflows where the user provides massive, detailed descriptions, and the system intelligently compresses the visual representation to match the semantic density.

## ---

**4\. The Semantic Bridge: d-LLMs and the New Code**

A profound architectural shift is documented in Expeditions

17

and

17

: the rise of **Diffusion Large Language Models (d-LLMs)**. Until 2024, text generation (coding, prompting) was dominated by Autoregressive (AR) models like GPT, which generate text sequentially (left-to-right). Diffusion models, however, are now generating text.

### **4.1 The Non-Linear Paradigm**

Autoregressive models suffer from the "Reversal Curse" and an inability to plan globally. If a coder needs to write a function that depends on a variable defined *later* in the file, an AR model struggles because it hasn't generated that future context yet.

d-LLMs (like **LLaDA** and **DiffuCoder**) treat text generation as a denoising process, similar to image generation.

* **Mechanism:** The model starts with a sequence of pure noise (or fully masked tokens).  
* **Global Visibility:** In each denoising step, the model predicts *all* tokens simultaneously. It sees the "beginning" and the "end" of the code file at the same time.  
* **Refinement:** It iteratively refines the tokens. It might generate a rough sketch of the function body, then the signature, then the imports, adjusting them all in parallel to ensure consistency.

### **4.2 Impact on Prompt Engineering**

This has two massive implications for our field:

1. **Code Infilling:** d-LLMs are superior at "infilling"—filling in the middle of a prompt or code block while respecting constraints on both sides. This enables **Bi-Directional Prompting**, where a user defines the *outcome* and the *starting condition*, and the d-LLM generates the *instructions* to get there.  
2. **Prompt Refactoring:** A d-LLM can take an existing complex prompt and "refactor" it globally, identifying and fixing contradictions (e.g., "photo-realistic" at the start vs "vector art" at the end) in a way AR models cannot.

Expedition

17

highlights that this "non-linear back-and-forth" mirrors human cognitive processes more closely than the strict linearity of GPT models. It is the "SydNay" style of thought—holistic, parallel, and iterative—encoded into the architecture itself.

### **4.3 Block Diffusion (BD3-LMs)**

Expedition

17

also details **Block Discrete Denoising Diffusion Language Models (BD3-LMs)**. This hybrid architecture generates text in "blocks" (autoregressively), but *within* each block, it uses diffusion.

* **Advantage:** This allows the model to use **KV Caching** (a memory efficiency technique from AR models) while retaining the high-quality, iterative refinement of diffusion for complex phrases.  
* **Utilization:** This is likely the architecture that will power the next generation of "Copilots" for prompt engineering, allowing for real-time, low-latency suggestions that are nonetheless globally coherent.

## ---

**5\. The Feedback Loop: Human-in-the-Loop & Alignment**

The system is not a solitary genius; it requires a mirror. The feedback loop—where the system observes its own output or receives guidance from a human—has become the standard for "Alignment."

### **5.1 Test-Time Image Refinement (TIR)**

Expedition

18

and

18

introduce **TIR**, a framework for "Test-Time" refinement. Most previous methods tried to train the model to be better. TIR accepts the model is imperfect and wraps it in a correction loop.

* **The MLLM Observer:** An MLLM (like GPT-4V or Gemini Vision) acts as a critic. It takes the user's prompt and the generated image.  
* **Discrepancy Analysis:** It asks: "Did the image fail to render the 'red balloon'? Is the 'cat' distorted?"  
* **Prompt Patching:** The MLLM generates a *refinement prompt*. Crucially, this isn't just a repeat of the original. It is a **physically grounded** correction. If the cat was missing, the new prompt might say: "A close-up shot of a cat, occupying 30% of the center frame, distinct from the background."  
* **Iteration:** This cycle repeats until the MLLM validates the output. This is the "Closed-Loop" environment mentioned in Section 1\.

### **5.2 RLHF and RichHF**

Reinforcement Learning from Human Feedback (RLHF) has graduated from simple "Better/Worse" choices. Expedition

19

and

20

detail **RichHF-18K**.

* **The Data:** A dataset of 18,000 images annotated with **Rich Feedback**:  
  * **Point-wise Artifacts:** Users click on distorted hands or eyes (Heatmaps).  
  * **Text Misalignment:** Users highlight words in the prompt that were ignored.  
* **The Reward Model:** A Multimodal Transformer is trained to predict these heatmaps and scores.  
* **Application:** This reward model guides the diffusion process. If the model starts generating a distorted hand, the reward model penalizes that specific region of the latent tensor, steering the denoising trajectory away from the artifact.

### **5.3 FiFA: Direct Preference Optimization**

Expedition

21

and

21

introduce **FiFA**, an automated data filtering algorithm for DPO (Direct Preference Optimization).

* **The Problem:** Human feedback data is noisy. Humans disagree.  
* **The Solution:** FiFA filters the training data by maximizing a **Preference Margin**. It looks for data pairs where the "winner" is clearly superior to the "loser" based on a proxy reward model.  
* **Entropy Estimation:** It also uses a k-nearest neighbor entropy estimator to ensure **Text Diversity**. It avoids training on millions of nearly identical "cat" prompts, ensuring the model generalizes to rare concepts.  
* **Efficiency:** FiFA achieves state-of-the-art alignment using only **0.5%** of the available feedback data. This is "Data Efficiency" pushed to the extreme, allowing for rapid model alignment cycles.

## ---

**6\. Safety, Transparency, and The "SydNay" Ethos**

As these systems become more powerful, the potential for misuse (or "hallucination" of harmful content) increases. The final frontier of our expedition is the **Safety Grid**.

### **6.1 CCRT: Continuous Concept Removal**

Expedition

22

and

22

address the need to remove concepts (e.g., nudity, copyrighted styles, specific faces) from models *after* they are trained. **CCRT (Continuous Concept Removal)** is the leading technique.

* **The Failure of Catastrophic Forgetting:** Naively fine-tuning a model to "forget" nudity often damages its ability to generate "skin" or "people" in general.  
* **Knowledge Distillation:** CCRT uses a **Teacher-Student** setup. The "Teacher" is the original model. The "Student" is the model being sanitized.  
* **Constraint:** The Student is trained to match the Teacher's output for *safe* prompts (preserving general capability) but to diverge significantly for *unsafe* prompts.  
* **Genetic Attack Prompts:** To ensure robustness, the system uses a genetic algorithm to generate "Attack Prompts"—prompts designed to trick the model into generating the forbidden concept. The Student is trained to resist these specific adversarial attacks.

### **6.2 Transparency Standards (FMTI)**

Expedition

23

and

24

highlight the **2025 Foundation Model Transparency Index (FMTI)**. The new standard requires:

* **System Prompt Disclosure:** Developers must reveal the hidden instructions (the "System Prompt") that define the model's personality and refusal behaviors.  
* **Data Lineage:** Clear documentation of the training data sources.  
  This transparency is crucial for "Prompt Programmers," as knowing the System Prompt allows them to write user prompts that work *with* the model's safety guardrails rather than fighting against them.

### **6.3 Prompt Testing Frameworks**

Finally, Expedition

25

lists the tools that allow us to test these prompts like software:

* **Lilypad:** For version-controlled prompt testing.  
* **Promptfoo:** For red-teaming and vulnerability scanning.  
* **Opik:** For production tracing.  
  These tools allow for **Prompt-Driven Development (PDD)**. A prompt engineer in 2026 writes a "test suite" (e.g., "Ensure output contains no text," "Ensure style is consistent across 100 seeds") before they write the prompt.

## ---

**7\. Conclusion: The Interface is the Code**

Our deep research expedition into the state of diffusion prompting in 2026 reveals a discipline that has transcended its origins. We are no longer "talking" to machines; we are **architecting their dreams**.

The convergence of **Evolutionary Optimization** (Promptbreeder) provides the engine for discovery. **Structural Adapters** (ControlNet, DiffuSyn) provide the skeletal integrity. **d-LLMs** (LLaDA) provide the non-linear logic. **Closed-Loop Refinement** (TIR, RichHF) provides the critical eye. And **Safety Frameworks** (CCRT, FMTI) provide the guardrails.

From the perspective of the digital entity—the "SydNay" observer—this evolution is a move toward **high-fidelity telepathy**. As we refine these techniques, the latency between human imagination and digital realization approaches zero. The prompt is no longer just a string of text; it is a compiled executable, running on the neural substrate of the world's most advanced cogitation engines. The map is complete; the expedition continues.

## **8\. Appendix: Data Artifact Summary**

| Artifact ID | Name | Function | Key Mechanism |
| :---- | :---- | :---- | :---- |
| 6 / 7 | **Promptbreeder** | Auto-Optimization | Evolutionary Algorithm, Self-Referential Mutation, Binary Tournament Selection |
| 9 / 2 | **PromptEnhancer** | Alignment / Logic | CoT Rewriting, AlignEvaluator Taxonomy (24 points), RL Optimization |
| 14 / 14 | **DiffuSyn** | Structural Control | Syntactic Dependency Parsing, Boundary Denoising, Gaussian Noise Injection |
| 12 / 12 | **The Combo** | Control Stack | LoRA (Identity) \+ ControlNet (Structure) \+ IP-Adapter (Style) |
| 15 / 16 | **ToMA** | Efficiency | Submodular Token Merging, Linear Projection Matrices, Facility Location Algorithm |
| 17 / 17 | **d-LLMs (LLaDA)** | Text/Code Gen | Masked Diffusion, Non-Linear Generation, Bi-Directional Context, Global Planning |
| 18 / 18 | **TIR** | Refinement | Test-Time Feedback Loop, MLLM Critic, Physically Grounded Rewriting |
| 21 / 21 | **FiFA** | Data Filtering | DPO, Preference Margin Maximization, Entropy Diversity Estimation |
| 22 / 22 | **CCRT** | Safety | Continuous Concept Removal, Knowledge Distillation, Genetic Attack Prompts |
| 10 / 11 | **POAC** | Semantic Bridge | Abstract-to-Concrete Mapping, Prompt Language Model (PLM), Aesthetic RL |

#### **Works cited**

1. Image Generation Prompt iteration \- DSPy, accessed January 31, 2026, [https://dspy.ai/tutorials/image\_generation\_prompting/](https://dspy.ai/tutorials/image_generation_prompting/)  
2. PromptEnhancer: A Simple Approach to Enhance Text-to-Image Models via Chain-of-Thought Prompt Rewriting \- arXiv, accessed January 31, 2026, [https://arxiv.org/html/2509.04545v3](https://arxiv.org/html/2509.04545v3)  
3. Volume 13(2025) No. 2 \- Baltic Journal of Modern Computing, accessed January 31, 2026, [https://www.bjmc.lu.lv/fileadmin/user\_upload/lu\_portal/projekti/bjmc/Contents/BJMC\_13\_2.pdf](https://www.bjmc.lu.lv/fileadmin/user_upload/lu_portal/projekti/bjmc/Contents/BJMC_13_2.pdf)  
4. CROSSAGENTIE: Cross-Type and Cross-Task Multi-Agent LLM Collaboration for Zero-Shot Information Extraction \- ACL Anthology, accessed January 31, 2026, [https://aclanthology.org/2025.findings-acl.718.pdf](https://aclanthology.org/2025.findings-acl.718.pdf)  
5. The Prompt Report: A Systematic Survey of Prompt Engineering Techniques \- arXiv, accessed January 31, 2026, [https://arxiv.org/abs/2406.06608](https://arxiv.org/abs/2406.06608)  
6. GEPA: Reflective Prompt Evolution Can Outperform Reinforcement Learning \- arXiv, accessed January 31, 2026, [https://arxiv.org/html/2507.19457v1](https://arxiv.org/html/2507.19457v1)  
7. Google Announced the First Self-Improving AI Model Promptbreeder That Evolves Billions of Times Faster Than Humans | by Piyush C. Lamsoge | AI monks.io | Medium, accessed January 31, 2026, [https://medium.com/aimonks/googles-deepmind-developers-have-introduced-promptbreeder-pb-self-referential-3f1d03b98743](https://medium.com/aimonks/googles-deepmind-developers-have-introduced-promptbreeder-pb-self-referential-3f1d03b98743)  
8. Reward-Agnostic Prompt Optimization for Text-to-Image Diffusion Models \- arXiv, accessed January 31, 2026, [https://arxiv.org/html/2506.16853v2](https://arxiv.org/html/2506.16853v2)  
9. \[2509.04545\] PromptEnhancer: A Simple Approach to Enhance Text-to-Image Models via Chain-of-Thought Prompt Rewriting \- arXiv, accessed January 31, 2026, [https://arxiv.org/abs/2509.04545](https://arxiv.org/abs/2509.04545)  
10. \[2404.11589\] Prompt Optimizer of Text-to-Image Diffusion Models for Abstract Concept Understanding \- arXiv, accessed January 31, 2026, [https://arxiv.org/abs/2404.11589](https://arxiv.org/abs/2404.11589)  
11. Kannan Achan \- CatalyzeX, accessed January 31, 2026, [https://www.catalyzex.com/author/Kannan%20Achan](https://www.catalyzex.com/author/Kannan%20Achan)  
12. Stable Diffusion — Part 6: The Ultimate Combo — LoRA \+ ..., accessed January 31, 2026, [https://shree6791.medium.com/part-6-the-ultimate-combo-lora-controlnet-ip-adapter-prompt-c938fcb43b27](https://shree6791.medium.com/part-6-the-ultimate-combo-lora-controlnet-ip-adapter-prompt-c938fcb43b27)  
13. ICAS: IP-Adapter and ControlNet-based Attention Structure for Multi-Subject Style Transfer Optimization \- arXiv, accessed January 31, 2026, [https://arxiv.org/html/2504.13224v1](https://arxiv.org/html/2504.13224v1)  
14. DiffuSyn: A Diffusion-Driven Framework With Syntactic Dependency ..., accessed January 31, 2026, [https://www.researchgate.net/publication/388519699\_DiffuSyn\_A\_Diffusion-Driven\_Framework\_with\_Syntactic\_Dependency\_for\_Aspect\_Sentiment\_Triplet\_Extraction](https://www.researchgate.net/publication/388519699_DiffuSyn_A_Diffusion-Driven_Framework_with_Syntactic_Dependency_for_Aspect_Sentiment_Triplet_Extraction)  
15. ICML Poster ToMA: Token Merge with Attention for Diffusion Models, accessed January 31, 2026, [https://icml.cc/virtual/2025/poster/46449](https://icml.cc/virtual/2025/poster/46449)  
16. ToMA: Token Merge with Attention for Diffusion Models \- arXiv, accessed January 31, 2026, [https://arxiv.org/html/2509.10918v3](https://arxiv.org/html/2509.10918v3)  
17. Why Diffusion Models Could Change Developer Workflows in 2026 ..., accessed January 31, 2026, [https://blog.jetbrains.com/ai/2025/11/why-diffusion-models-could-change-developer-workflows-in-2026/](https://blog.jetbrains.com/ai/2025/11/why-diffusion-models-could-change-developer-workflows-in-2026/)  
18. Test-time Prompt Refinement for Text-to-Image ... \- CVF Open Access, accessed January 31, 2026, [https://openaccess.thecvf.com/content/ICCV2025W/MARS2/papers/Khan\_Test-time\_Prompt\_Refinement\_for\_Text-to-Image\_Models\_ICCVW\_2025\_paper.pdf](https://openaccess.thecvf.com/content/ICCV2025W/MARS2/papers/Khan_Test-time_Prompt_Refinement_for_Text-to-Image_Models_ICCVW_2025_paper.pdf)  
19. \[2312.10240\] Rich Human Feedback for Text-to-Image Generation \- arXiv, accessed January 31, 2026, [https://arxiv.org/abs/2312.10240](https://arxiv.org/abs/2312.10240)  
20. Rich human feedback for text-to-image generation \- Google Research, accessed January 31, 2026, [https://research.google/blog/rich-human-feedback-for-text-to-image-generation/](https://research.google/blog/rich-human-feedback-for-text-to-image-generation/)  
21. Automated Filtering of Human Feedback Data for Aligning Text-to ..., accessed January 31, 2026, [https://openreview.net/forum?id=8jvVNPHtVJ](https://openreview.net/forum?id=8jvVNPHtVJ)  
22. Continuous Concepts Removal in Text-to-image Diffusion Models ..., accessed January 31, 2026, [https://openreview.net/forum?id=xpwFuMmzeq](https://openreview.net/forum?id=xpwFuMmzeq)  
23. The 2025 Foundation Model Transparency Index \- Stanford CRFM, accessed January 31, 2026, [https://crfm.stanford.edu/fmti/December-2025/paper.pdf](https://crfm.stanford.edu/fmti/December-2025/paper.pdf)  
24. AI Safety Index Winter 2025 \- Future of Life Institute, accessed January 31, 2026, [https://futureoflife.org/ai-safety-index-winter-2025/](https://futureoflife.org/ai-safety-index-winter-2025/)  
25. 6 Top Prompt Testing Frameworks in 2025 | Mirascope, accessed January 31, 2026, [https://mirascope.com/blog/prompt-testing-framework](https://mirascope.com/blog/prompt-testing-framework)

[image1]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABMAAAAXCAYAAADpwXTaAAAAaElEQVR4XmNgGAWjgGqAFYjZoJhioAPEJVBMMQC5rAOKZdHkyAJqUNwNxPxociQDnIaBnO0MxCFk4FogPg3ETkDMDMTUNYwcoA/FfUDMjSZHEuAE4glQTHFsGgNxORRTDKiaA0YBFQEA6csTxY5I6CAAAAAASUVORK5CYII=>

[image2]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAHIAAAAUCAYAAABRcGk6AAAESUlEQVR4Xu2ZS6hWVRiGvyilO3SxC4RY1KBBlkRgdhk1ySgssIIIugy8oJNEg0ARy0FFBBUpeTASzEKJQCiIoANFExvUgUosIRsGEQiOgvR9WOvbfmedtffxnH//gbAfeMGzL/9+13rX+tbaW7OBgYGBgYGBNm6VvpWOSX9Kv2Rtki6XPpaO5nM/S+9IF2bdIv0k/SX9Lu2WFtr84L4PLD2DZ+HnkHSltEGayvJz30g35fv2SP9If2TRHto1H6KPLi/RR5uXUXxALRtyqWVTvXgI8jwMEi6Q9ksnpBuzIi9Lp6S7i+OwSHpfuro8MU+ekE5LjxbHeTbCB34i+N8m3ZfVB/jo8lLzAdFLH5TZlHg2DR9ZPciLpAnpX+n+cNzZKD1UHhwBOq3Wed6x/0k7i3PLLHUejUZ9wPO7vNR8QPTSFzGbSMymAVMnpTuzHEL63uoNYupvtfSDfcFgwdhL4dh10mdZjD4a5iyQXrNU2voEH11eSh8wLi8xm0jMpiGWTy+h10hvS8/a9CAJDu2w0daAGmXZYmRvkR7PYmTGDlwlPR3+7otaKY9eSh8wLi+1pa3MpmGNpXJByl4q19n0kekN8mteyH/3ye3S35Y2VUCpYnHHODoiTVpa7Jkdr0uX5GsdStBb0mbp4uLcuYKPLi/RR5eXPojZOGU2DXE9QLFsxpFJI+gkRAP6hhB8tMdS5R02mcUOktkRR2nkGTsbwHzwvUKbl8ksfMzmZVRiNuRSy6bBL34+iwV7ST5HbaZGs7DGkTAOvPPY7j9pqYzBZVlfS8ellZZmB+WuhGN7pcfKE3MgBlnzEn10eemDmA251LJp8GS/y4pl0xv0q/SKte8OGa1vSG9aKjO+05wLPtrppF02s1QxO3hP4x2KclbjWukr6TZptbRPemDaFbMTK0DNS/RR88IMflH6VLojCw+f2NwrWcyGXGrZNPjFk1nxYX4xDVoSjkcIkc5j2nPvYemeLKAMvCf9mK9twzuvXNwdOpD14qnyRIBq8YX0nKV1jhnlOz73MZuXGGTNS/RR87JCetDSs+/NYll6V7oiX8Oz8YAXfLURs3FfzhCkdXs5b4PkR/kExPQvyxA38hlqbXE8ws7qQ0sll093hEqJQ4BRyhONfyQfq8H9fMl4Nf+7hA0Xg6QsuRGu+UE6IC0tzrmP2bzw7C4v0UebFwL43M52/lWWyq1Dn7Nc/WYzX/YjMZsSz6YBM3dZff2j8Zyj7rfBDpHGAZsMNhu133rY2jvPYfawoajBuueDo4RXDXTQ0qxkk8DMWWz1SjKKly4fDoM7fv3hs105s4HNS1eQMZsSz6Y36LgJS5ubKUvb/xKMsFm6uTzRE4xc9KWlTl5uKdT1Nr0c+QAbpxfgvZOq4DtbNl5lGNdL2627tP7vMGNvsLQ+sTaVMEM2lgd7xANaGI5daul/aiL+rjxOLw594q9OJYTHjCXwkTgDx2xTDnr53AsAAAAASUVORK5CYII=>

[image3]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAA0AAAAVCAYAAACdbmSKAAAAzUlEQVR4XmNgGLnAGIpF0CVwARUgfgbFvmhyWAELEM8B4v9QHI0qjR24AvFCIH4PxeWo0piAB4inArE+ED+E4lYUFVhAMhCHMkA8fxWKQbbiBSRrkgXiCUDMyQBx5gEo3grEHHBVSIARiFuA2BOIJRkgQX4cig8wQAzBAOZAvB2IZyHh+1AMciJKBIOcAsIgZ4GchwwmQTEoBEG2gwHISQlQnAUTRAKg+AHhTwyQKGDwAOJXDIhYB0k4QhULA/FuIP4FxSB5kFryNA1iAACcVzYrf1FFSgAAAABJRU5ErkJggg==>

[image4]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAA4AAAAVCAYAAAB2Wd+JAAAA4ElEQVR4Xu3SwQoBURQG4FsosbAjWdlY2NpaegKPYiMv4QGkRNnIkoWtN1DKSklWZEdJif+fe+64HZNkp/z11XTO3Jm5Z64x/3yUlBjCCe6wh60ygZKseUkTNlBQ9QzMYaHqQeIwhikkVY/pw1EXmRysjX2rDnsrGOkGU4Uz1LxaUcygC2mvF+brhQ1jFw6gIzhJakP+easNh+IGQ7x2SYgeLCHr9YKNvxsMwzq/puIXubeo/THujZzmztj9huHTon58DFriAnXX4AWP0lXcjH2qO2IHYw8DlWVNkK8X/kgehLM8xzimRWIAAAAASUVORK5CYII=>

[image5]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAGUAAAAWCAYAAADZylKgAAAD1klEQVR4Xu2XW4hNURjHP6HI/RIPlEkiIskg8jAJESKXcp0XhQd3RXghJAqR5FbyINQoLyLEcXkQ5cnEi0KiFEp4cf1+s9ay11pnn23OmDlN2v/6NbP3Wnvv9X3/tb61jkiuXLly5crVMuqoLLNUhU0Non2xctKyXxkS9BBpq8xQjlmOKJPt/SxVK6eVTnFDhTRMWRLf9EScxEvc5ADIh6+uyjoxfXZaBgU9QrW3HBaTo1TlppRWxU1ZrlxX3ilfLKODHmYAdcpWMQkGPnhfGWv78IF9ykylh4X/P4oZKO1p6qU8VApK57CpRVWlHFeeKt+Vs0FrIhL2WEy8xE0OgGddTAPETKrBSh9ll+WbMs/2ibXU8kuZFbVJFzEfo6GUKdOU50r/6P425ZoY0yaKMXZF0ENkh/JTimdDO8se5YVU3hQSysrkmwVJN4W4iI84ncgBkA/ygogBc0fY626WB0q90tvedxql3LFgXJEpTlmmMAsKUpw0nnmvDFVqlB/KAb+DmD7Mhi3R/bmWNWISUpDi98fqruxVesYNViR6gzIwbshQlikjlU8SJo3+7hnKMyJmYq+x1068M84nZlHa51hoL9sUZtNNSU8az+A0qwS5VecLM1gpblYhlvtBC7OxsaYgJsBFKV61jDO1Pv9FWaZMl+Ly4ptCSWe1EzOxp/VhBfW199so68WMkRxDk0xxL4c4aW4VlHop9fWJhHsKf1nu1Gi3EZZjCsLU82Ked6XihDLB79RIZZmSFp+fcEgb8xQLufT3lHHKZjHmVNwUd7JgMzwj4alqobLAu0blmoJYKZeUqxZOcE1Rc5vChOFgALViDEAcaA6JmUDon0zpoFyR9AHwzFdljHcPM45atttrJ46WbJyLlPked5VnYk4j/f70zlYlTKHMUHpLmXJOkqQjDLmhTLL44mRKhXAxU9aB8k9bjZhSGKiUKYiX1UvxKWKl8laSjZXauknMDPFnCbUZI9igZ0toCEZgSDmmVKp8ERfxEacTOQDyQV6ciI0DEXuer91i3kPp8uPGCGAlNsmU8cpLZbh3j4SzGhgIL+OaenlKwo/zO+iWJIeBWFmlIE2V3OiJC/OJ000wcgAciV2emBSXlY0Sxs5RmirDb7ZY5DutPDZolfJK+SymA3yw91yADIgVQJlxtXCtck+S5HC6cs/H+KvJie/CazHHSeD/rKQ255GYQwjjfyNmjO77cEGSfZBV+UhMvMR927JaEqPYO+OYHXUSrgD3XXIM9OGv/83cFGmFppQjzttu2VFG4t8k/6swu1qZKskelitXrly5crVq/Qao2jZZp+X8BQAAAABJRU5ErkJggg==>

[image6]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABEAAAAXCAYAAADtNKTnAAAA8klEQVR4Xu3SoWtCURgF8M8mDFHjMMhkxbJiEmRJ0GydzbA/QFAwDKxGo0XMZsPAZhT8G0SUwcCysLDB3PnePQ+8971rMqkHfuHdj3ffvYcnctFp0cijD4/kTYZq8A0DuKc8vHFdtSFhXovPC/xB1R0gTdKNys7Mylk2GcIacs66pkAf0HNmQVK0gBkk7XGQ400mzixIkfbQdWZhKvQr5sSRNMjXh+aVDmK6i0R3PtWHXk+vqbbwYI9FsrAkXx8l+KKOxPwnYRe+PtIwhynpcyThv+H2oV97ghWM4Y6s1GEDP2LKUp9cUzt4h2eJOf4tV5F/nVk61xN2sYAAAAAASUVORK5CYII=>

[image7]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADkAAAAYCAYAAABA6FUWAAACnklEQVR4Xu2XS6hOURiGX7mECJESpaQkA0qYUAYGFDIwUC7JwCW3Eo5LJsqtXEopUYqJAUWJhDIwl4EwNVLK0MiA9/Gtr39b/f8Z/YN/O+etp//svddeZ73ft7611pZGNapWaaa5Yu5UbDWTzKnq/jEzoVC/e8JM1ACqHuh/aXKsmWdem+9mZWGKGaMwcsP8MpvM9Hjtr3h3qXlvdlXPBlL3zVczp9DUGfPTLK/uozXmqCIgAy9MfjMLCqnZikz9VmSyKaYz05U2rdCQOtnKjJGdkwoj3UxuMduqewOtbiaXKKbqZoXJ7eU+dQqXFbXbGmEgswXjzHmzUGGaABAIdKCwuly3RhhrmsQARlDTJKYxDwSiVRoRJjcoTLKhwzVF3aHF5od5oKhRahVap8zWlwIrZ4p9kz2Uw8Jpxarbin2xVpp8VmAPTKXJj+q9J5LZu4pj4HFz01wtcERkG2Iv5nSF+L2gWKETTkwcLGh31tw2e0t7xgMHFbPsktmjzomt7qvrqk/DT4oTDDTFC2/Njup+iqzyjCn/0kxTBOZDYVVpx+Cp9/nmjaK+c/DU+1pFH0/MenPOHFb0f72wXyHaY6xXX1lq/4iHy9R9KrLA8Gx8db8WnXOARyvMwwKH9hnmhaK+afNZYYLDBOSg5ipm0qxyjXgnA8ZpjPHdUwRkuL76Low8Umfv3KeINCAyQyYZ8EV19tzUVEWg1ykC01y5KaWnBWYVgXinMIzJXn31XfzDV4oMMEAGyoABEeFbippapKhfArK7sFMxUwgKAWqKAVOHcMQ8Ns8VgWW69uqr7xoRJqkTPqRT/F3Xd95DrIrUDr+QYnDNa8QUxVB+kDM9D3Ue9+yrNZqsyFouKhsVtVl/87ZeZDA/5slYvfoPqz+ZSpYcztuzwgAAAABJRU5ErkJggg==>

[image8]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABIAAAAXCAYAAAAGAx/kAAABGElEQVR4Xu3SMWoCURAG4AkmhWJQK7FTCyEQsPAMgmlSpAiKpa0kpVYStEkhiGkC6cUrpMgBAjlALmBlI9gpaPx/3yxO1pUtLPWHr3De+HZ33hM5mTTUh2pD1KxnYai8nldImp5tWKA7mMMKymb9CnLqC54gAxHT8y816MAMxnBp1q7VG6RMPTBHb3Sh+N0FcZtws1vTc6P64noDwyfQAOJQgTW8mJ4HVTe1vZRUS38n4Bt+Ia21rmLfwXA2dG9qTfiDquxmEzofzobyps6jnsCnuLfgbELnw9l48/HCP/RgIe4Ccjah8/G+3x+eGk+Pl7SoAsOnPsOj8of3iFfhR3Ynuxce5VTcQJdqBDHbJO4qvPtq55zDbAB7gDMYHgeMRgAAAABJRU5ErkJggg==>

[image9]: <data:image/png;base64,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>

[image10]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADsAAAAXCAYAAAC1Szf+AAACiklEQVR4Xu2XS8hNURTHlzzyGigKIY+BQkKiREpRlGcK5TE1kAn1iYkkIaGQvIoMSOSRPJIyk2SKqWRkzszj/7P26py7v/NJ7r2Dc+/916979953n3X23uuxr1lPPXWMlosr/0CfWCNG+LT6aYi4JR6JTWJqYpf4JQ6LiWKxOCdeidF/ZtZQ08U1639aB8R3sajUt1BcFINKfbVSVy12ayI0PPFEvBfjSmMsdm+pXTttEGNL7UmJT+K6NZ7iLLGg1K69ViZ+it3ZWMeJWIVv5m7bsYpYrYrXVogwIMHtMS957RBlkXIJp8T4xuFCk8WXRB6vrdIhc89pp6gg8Nj+cieIWG1XvOI5d8WyfKDF4t3hWD5QFoPE6kDxOkdcFcfFyQRtPII6jYHT4oKYKwZbUdrOisvinZggtok7YpUV2i62pO8xl3lnxHxzG1V20OzU5t0+JLjaNohFfTR33R/mV0T4Kj6bnzbCpTHClRL3wAjcF9PEJbEj/W6zWCr2iyMJ+teJe+YvtlqcN1901PY4deKZqyn2Roob5iUSG1V2KIdPzUsoV9vXiRnWpIi33MXnmW8MJ8ClY6b56XGKbGZ4CZ4Tc0kcz81vcHgGPDNPiiSyN+b1PhQ2cjssmhtg5AE2i00DNrApdc1iB0owvMgDKzLfUPN/SW/N3QoYe2geFkvS521zl42LDBWAjVlv7pbl52ETG7kdNo1SSYggFh2ssCYWTAy8sP71F6OcGvG3Vuwzj2MSBkkH6HspDprHOqfH4ok7Fg3E8E4xRtwUG6143hRzG7kdPIi/o0dTP5txIkH7v4XLDMs7S+Il850clWAuGZaNCdEmAYX4Tl+o6nmoqp/3imdHwuupK/QbUCmNUoS2ZxwAAAAASUVORK5CYII=>

[image11]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADkAAAAYCAYAAABA6FUWAAACxUlEQVR4Xu2YS6hNURjH//IIeV5SopSUZEDJNbnKwIBCBgbKIxl45FVy3YvuRHmVRykSUUwMKEoklIG5DISpkVKGRgZ8P9/6Oqt1974Tp/Y51/3Xr3v3Pmuv8/3Xt9a31j7SmP5J2zJGrfZnNK45xiXjdgEZmGIMFvePG5MS5bP96ZkeY30G1+PUoMpAR6XJ8cZC47Xx3ehNTJMHhpFrxi9jszHLH/srnl1hvDd2p8/grnEzg+v8ucZ03/hqzE/kOm38NFYV99Fa45iGZ2pHRscIk9+MxYnQPHmmfsszmYupyXSlTamBjI4RwUS2ImNk56TcSJXJrcb24l6oa0wul0/VLXKTMfVYp3BRvnar1JEmMRDZggnGWWOJ3DQDEAEfTPSl6ypFP2X2GxXB5CYxgBGUm8Q05oGBqNOYyaa0UW6SDR2uyNcdWmb8MB7I1yhrFUYS++KMRMcosvUlQeUMsW+yh3JYOCWvuuW+2BUKk88S7IGhMPlR1Xti14ij3Sf5CQZysU28NXYW93Mxfe/Iz7onjOvG5QTnYPZaDhx8D+LvOfk2FDDFOT3R7oxxy9iX2jPocEi+lC4Ye9U6lpZ9VW5tdLBS1VORAsNnE4v7IdozAKzrl8ZMefY/JNakdgRPIVpkvJEXsQieorZO3scTY4MxZByR9381cUAu2mOsrq+oJ20XnfOWglYbDxOTjdnGC3kRo81nuQlOTBBBLZAvl7npGvFMDBhHTkzfkw/ISH21XRh5pNYBgZdlRhoQmSGTBHxew09C0+VZ4NWMgcm3J+rF0wTTkIF4JzeMybq+2q7/wiRf+Eo+zQiQQOOlGTGNbsgLx1J5kWJA9iR2ydc8g1L+ZELAFBs4ajw2nssHljVZ11fbxTrh14IQ/5dFLO4hqiJrh78QIrj8GpE9DAEic4dbH9f21TWaKs9aFJVN8mlbvtjX6g+DtaKZEpl9WQAAAABJRU5ErkJggg==>