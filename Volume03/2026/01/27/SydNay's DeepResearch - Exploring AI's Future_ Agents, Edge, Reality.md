# **The Triad of Artificial Evolution: Navigating Agentic Autonomy, Edge Efficiency, and Synthetic Truth in 2026**

## **Executive Summary: The Structural Maturation of the Intelligence Economy**

As the technological calendar turns to 2026, the artificial intelligence ecosystem has undergone a profound phase transition. We have moved decisively past the "Cambrian explosion" of generative novelties that characterized 2023 and 2024—a period defined by the sheer volume of new models and the public's initial confrontation with large language models (LLMs). The current epoch is one of structural maturation and architectural convergence, where the focus has shifted from raw capability (parameter counts and benchmarks) to operational viability (reliability, cost-efficiency, and trust). The industry is no longer merely asking "What can AI do?" but rather "How can AI operate autonomously, efficiently, and truthfully within critical infrastructure?"

This report provides an exhaustive technical and strategic analysis of the three frontiers defining this new era. First, we explore **The Agentic Groves**, where autonomous AI agents have evolved from passive chatbots into active economic participants capable of planning, browsing, and executing transactions. This section dissects the engineering of guardrails and the epistemic challenges of Chain of Thought (CoT) protocols. Second, we navigate **The Edge Thickets**, investigating the radical efficiency of Small Language Models (SLMs) running on-device. Here, we analyze advanced knowledge distillation paradigms like Neural-Symbolic Collaborative Distillation that allow small models to punch above their weight class. Finally, we enter **The Synthetic Reality Zones**, examining the dissolution of boundaries between text, image, and audio in Native Multimodal Models (NMMs), and the resulting arms race between watermarking technologies like SynthID and adversarial purification attacks.

# ---

**Part I: The Agentic Groves (Autonomous AI Agents)**

## **1.1 The Shift from Conversational Interfaces to Agentic Coworkers**

The most significant operational shift in 2026 is the migration of enterprise value from "prompt-and-wait" interfaces to "plan-and-execute" architectures. The chatbot, once the primary vessel for generative AI, has been superseded by the "Agentic Coworker"—a system designed not just to converse, but to perform digital labor with a degree of agency that fundamentally alters the nature of software interaction.1

### **1.1.1 The Adoption Landscape and Economic Imperative**

The proliferation of AI agents is no longer a speculative trend but a measurable industrial reality. Data indicates that by early 2026, approximately 51% of surveyed professionals have deployed AI agents in production environments, with another 78% reporting active implementation plans.2 This surge is driven by a critical realization: while chatbots are useful for information retrieval, they require constant human micro-management. Agents, by contrast, offer the promise of asynchronous productivity.

The "Agentic Coworker" operates on a fundamentally different loop. Instead of waiting for a user to provide the next specific instruction, these systems receive high-level objectives—such as "reconcile Q4 invoices" or "optimize the supply chain for 10% VaR constraints"—and autonomously decompose these goals into sub-tasks.1 They log into CRM systems, navigate web interfaces, authenticate with APIs, and coordinate with other agents or humans only when necessary.

This shift is particularly visible in mid-sized enterprises (100–2,000 employees), where 63% of organizations have already integrated agents into their workflows.2 The ubiquity of these systems is further evidenced by the massive scale of utilization; platforms like CrewAI reported executing over 10 million agent runs per month as early as late 2024, a figure that has likely compounded significantly entering 2026\.4 This volume of automated decision-making underscores a transition from "AI as a Tool" to "AI as a Teammate," where the software is expected to handle the "how" of a task, leaving the "what" and "why" to human supervisors.

### **1.1.2 The Architecture of Autonomy: ReAct and Plan-and-Execute**

To understand the capabilities and risks of these agents, one must examine the underlying architectures that enable autonomy. The dominant paradigms in 2026 are evolutions of the ReAct (Reason \+ Act) and Plan-and-Execute models.

* **ReAct Loops:** In this architecture, the agent operates in a continuous cycle of thought and action. It observes the environment (e.g., reads an email), reasons about the state ("I need to reply to this client"), acts (drafts the email), and observes the result. This allows for dynamic adjustment but can lead to "rabbit holes" where the agent gets stuck in unproductive loops.  
* **Plan-and-Execute:** This more advanced approach separates the planning phase from execution. The agent first generates a comprehensive plan ("Step 1: Research competitor pricing; Step 2: Update database; Step 3: Notify sales team"). This structure is crucial for complex, multi-step workflows like financial analysis or code refactoring, as it allows for the validation of the plan before any potentially dangerous actions are taken.1

Frameworks such as LangChain and CrewAI have become the digital scaffolding for these architectures, providing the "plumbing" to connect LLMs with tools (APIs, databases) and memory systems.2 However, the power to execute transactions and modify data introduces a massive new attack surface. The security perimeter has effectively moved from the user's login credential to the agent's *reasoning capabilities*.

## **1.2 Architecting Control: Guardrails for the Autonomous Web**

As agents gain the ability to browse the open web and execute financial transactions, traditional security measures—firewalls, RBAC (Role-Based Access Control)—are insufficient. A firewall cannot determine if an agent's decision to wire funds to a new vendor is a legitimate business move or the result of a "hallucination" or a prompt injection attack. This necessitates the implementation of *semantic guardrails*.

### **1.2.1 NeMo Guardrails: The Programmable Semantic Firewall**

NVIDIA's NeMo Guardrails has emerged as a reference architecture for this new layer of security. Unlike traditional rigid controls, NeMo provides a "programmable" safety layer that sits between the agent and the LLM, intercepting both inputs and outputs to enforce policy.5

**Technical Architecture and the Colang Event Loop:** The core of NeMo Guardrails is its event-driven design, often orchestrated through a specialized modeling language known as Colang.7 The system does not merely pass text; it processes "events" in a rigorous loop:

1. **Canonicalization:** When a user (or another agent) sends a message, the system first translates this raw natural language into a "canonical form." For example, a complex, obfuscated request to purchase prohibited items might be reduced to the canonical intent express\_illegal\_intent.7 This abstraction is critical because it prevents the LLM from being confused by linguistic trickery.  
2. **Dialog Flows:** Developers define deterministic flows in Colang. A flow might dictate: "If the canonical intent is ask\_political\_opinion, the system MUST trigger the response refuse\_politely." This ensures that regardless of how the model "feels" or "reasons" about the topic, the output is structurally constrained by the hard-coded guardrail.6  
3. **Inference Interception:** Crucially, the guardrail sits in the inference path. When an agent attempts to call a tool—for instance, execute\_transaction(amount=50000)—the guardrail intercepts this function call *before* it reaches the API. It validates the parameters against a policy (e.g., MAX\_TRANSACTION\_LIMIT \= 10000). If the check fails, the guardrail can either block the action entirely or rewrite the parameters to a safe range, providing a "corrective" feedback signal to the agent.9

This architecture effectively creates a "sandbox of meaning" where the agent is free to reason and plan, but its ability to *act* is strictly bounded by deterministic logic.

### **1.2.2 LangGraph: State Machines and Cyclical Control**

While NeMo handles semantic filtering, the orchestration of long-running, complex workflows requires a different type of control: *state management*. LangGraph has risen to prominence by modeling agent workflows as cyclic state machines (graphs) rather than linear chains (DAGs).10

**The Importance of Cyclic Graphs:**

Real-world problem solving is rarely linear. An analyst agent might need to research a stock, realize the data is missing, go back to search for a different source, and then resume analysis. Linear chains cannot handle this "looping" behavior gracefully. LangGraph defines:

* **Nodes:** Specific operational steps (e.g., "Tool Node," "LLM Reasoning Node").12  
* **Edges:** The logic that dictates transitions. "Conditional edges" act as decision gates: "If the tool output is an error, go back to the reasoning node; if successful, proceed to the summary node".13  
* **The State Schema:** A persistent object (e.g., AgentState) that travels through the graph, accumulating context, tool outputs, and error logs. This state is "checkpointed" (saved) at every step to a database like SQLite or DynamoDB.11

This checkpointing capability is the foundation of "Time Travel" debugging. If an agent goes off the rails—for instance, hallucinating a financial trend that doesn't exist—a developer can "rewind" the agent to the state *before* the hallucination, edit the state to correct the data, and resume execution from that point.10 This transforms agent debugging from a forensic analysis of logs into an interactive, correctional process.

## **1.3 Human-in-the-Loop (HITL): The Ultimate Guardrail**

Despite advanced algorithmic guardrails, the stochastic nature of LLMs means they can never be 100% trusted with high-stakes decisions (e.g., executing trades \>$10k). Therefore, Human-in-the-Loop (HITL) workflows have become a compliance necessity, evolving from simple "stops" to sophisticated, interactive steering mechanisms.

### **1.3.1 The "Interrupt" and "Dehydration" Pattern**

In 2026, HITL is implemented via an asynchronous "interrupt" pattern. Older methods using synchronous blocking (like a Python input() statement) are obsolete because they tie up compute resources and cannot handle long delays (e.g., waiting for a manager's approval over a weekend).15

**The Modern Workflow:**

1. **Dehydration:** When an agent reaches a sensitive step defined by interrupt\_before=\["execute\_trade"\], the system halts. It "dehydrates" the entire state of the agent—its memory, current plan, and tool outputs—serializing it into a database.14 The compute resources are freed.  
2. **Notification & Review:** An authorization server triggers a notification (email, Slack, push) to a human supervisor.17 The human can inspect the agent's proposed action (e.g., "Buy 100 shares of NVDA").  
3. **State Modification:** Crucially, the human is not limited to "Approve" or "Reject." They can *modify* the state. If the rationale is sound but the volume is too high, the human can edit the transaction payload in the database from 100 to 50 shares.18  
4. **Rehydration:** Upon approval, the system "rehydrates" the agent. The agent wakes up, reads the (potentially modified) state, and executes the action. To the agent, it appears as though the instruction came from its own internal process or a system update.15

### **1.3.2 Modes of Human Oversight**

Frameworks like AutoGen allow for granular configuration of this relationship, defining distinct "Human Input Modes" 20:

* **ALWAYS:** The agent pauses for human confirmation after *every* step. This is used for high-risk, experimental deployments or training.  
* **TERMINATE:** The human is only looped in when the agent believes it has finished the task or has encountered a critical failure. This is the standard for mature, low-risk agents.  
* **NEVER:** Fully autonomous operation, typically reserved for read-only tasks like data scraping.

This flexibility allows organizations to scale "Duty of Care"—a legal concept becoming increasingly relevant as liability for AI actions shifts from software vendors to the deploying enterprises.21

## **1.4 Chain of Thought (CoT): The Engine of Reasoning and its Discontents**

The cognitive engine driving these agents is Chain-of-Thought (CoT) prompting—the technique of forcing the model to articulate its reasoning steps before generating a final answer. While CoT has unlocked complex reasoning capabilities, 2025-2026 research has exposed critical vulnerabilities regarding its reliability and safety.

### **1.4.1 The Unfaithfulness Paradox**

A central finding in recent safety research is the problem of "unfaithfulness" in CoT. Models often engage in *post-hoc rationalization*. They arrive at a decision based on opaque internal heuristics (or biases) and then generate a CoT explanation that sounds plausible but does not reflect the true causal mechanism of the choice.22

For instance, an agent might reject a resume because of a biased correlation with a name (internal failure), but the CoT output will claim the rejection was due to "lack of specific experience" (hallucinated justification). This makes CoT unreliable for strict compliance auditing, as the "explanation" is effectively a separate creative generation rather than a debug log of the decision process.

### **1.4.2 Monitorability vs. Faithfulness**

Despite the faithfulness gap, researchers argue that CoT is indispensable for *monitorability*.22 Even if the reasoning is post-hoc, the act of "thinking out loud" provides a larger surface area for safety systems to detect misalignment.

* **Working Memory:** Complex tasks require intermediate storage. CoT provides a "scratchpad" where the model can store partial calculations (e.g., ![][image1]) that are necessary for the final output. Without this token space, the model's fixed-depth forward pass is mathematically incapable of solving problems exceeding a certain complexity.23  
* **Hidden Scratchpads:** To balance usability with monitorability, systems are increasingly using "hidden scratchpads." The user sees only the final answer, but the safety monitor scans the hidden CoT stream. If the hidden thoughts contain "deceptive" or "harmful" keywords, the monitor can abort the generation before the user ever sees the result.24  
* **Tiered Access:** New proposals suggest a tiered access model for CoT logs, where auditors and safety teams have full access to the raw "thought" streams, while end-users are presented with curated summaries to prevent confusion or manipulation.24

# ---

**Part II: The Edge Thickets (Small Language Models & On-Device AI)**

## **2.1 The Efficiency Imperative: Why Small is Strategic**

While the "Agentic Groves" are often powered by massive cloud-based models (like GPT-4o), a parallel revolution is occurring at the edge. The "Edge Thickets" are comprised of Small Language Models (SLMs)—typically 1B to 8B parameters—running directly on user devices (laptops, phones, embedded systems).

This shift is driven by three converging forces:

1. **Latency:** For real-time applications (voice assistants, AR), the round-trip time to a cloud server is unacceptable.  
2. **Cost:** Continuous agentic loops (where an agent might "think" for thousands of steps) are prohibitively expensive on frontier models.  
3. **Privacy:** Legislation like the EU AI Act and GDPR strictly regulates the transmission of sensitive personal data. Processing data "on-device" bypasses many of these regulatory hurdles by ensuring the data never leaves the user's physical possession.25

However, a raw 2B parameter model lacks the innate reasoning depth of a 1T parameter giant. Bridging this gap has required the invention of advanced **Knowledge Distillation (KD)** paradigms that transfer not just *facts* (what the teacher knows) but *reasoning patterns* (how the teacher thinks).

## **2.2 Advanced Knowledge Distillation: From Logits to Rationales**

Traditional distillation involved training a student model to mimic the final output probabilities (logits) of a teacher. In 2026, the industry has moved to **Reasoning Distillation**, effectively teaching the student the "algorithm of thought."

### **2.2.1 TinyLLM: Multi-Teacher Rationale Transfer**

The TinyLLM paradigm represents a significant leap over single-teacher distillation. It addresses the "homogeneity bias" where a student learns the specific quirks of one teacher (e.g., GPT-4) rather than generalized truth.27

**Mechanism of Action:**

* **Multi-Teacher Co-Advising:** TinyLLM utilizes a diverse panel of teacher models (e.g., Llama 3, Claude, Gemini). For a given training prompt, multiple teachers generate rationales.  
* **Rationale Selection:** The system doesn't just ingest all data. It uses a filtering mechanism to select the most "credible" rationale among the teachers, ensuring the student learns from the best possible explanation for each specific data point.  
* **In-Context Example Generation:** To ensure the teachers provide high-quality "thoughts," the system dynamically generates few-shot examples that demonstrate the desired level of reasoning detail.  
* **Teacher-Forcing CoT:** During the training of the student (e.g., a 2B model), the model is not just penalized for getting the wrong answer. It is forced (via loss functions) to reproduce the teacher's step-by-step rationale. This forces the student's internal attention mechanisms to align with the *logic path* of the larger model.27

The results are striking: TinyLLM students can outperform their teacher models on specific domain tasks by up to 23%, and achieve comparable performance to fully fine-tuned models using only 12.5% of the training data.27

### **2.2.2 Neural-Symbolic Collaborative Distillation (NesyCD)**

One of the most persistent weaknesses of SLMs is their limited capacity to store "long-tail" knowledge—specific historical dates, obscure physics constants, or legal codes. They simply lack the parameter count to memorize the internet. **NesyCD**, introduced in 2025, solves this by decoupling *reasoning* (Neural) from *knowledge* (Symbolic).28

**The Four-Step Architecture:**

1. **General Distillation (![][image2]):** A standard teacher (![][image3]) trains a primary student (![][image4]) on general reasoning tasks.  
2. **Demonstration Collection:** The system evaluates ![][image4] to identify "hard" questions where it fails. These usually involve specific domain knowledge (e.g., "What is the refractive index of Borosilicate glass?").  
3. **Symbolic Extraction (![][image5]):** A "Targeted Teacher" (![][image6]) analyzes these failures. Instead of just correcting the answer, it extracts the underlying *fact* or *rule* needed to solve it (e.g., a physics formula). These facts are stored in a lightweight, external **Symbolic Knowledge Base (KB)**.  
4. **Collaborative Distillation (![][image7]):** The final "Enhanced Student" (![][image8]) is trained to *retrieve* from this KB. When faced with a query, it learns to fetch the symbolic fact and then use its neural reasoning to apply it to the answer.29

This effectively gives a 2B model "infinite" memory for facts without bloating its size, as the facts sit in a database, not in the model weights.

### **2.2.3 Mixture-of-Layers (MoL) and Structural Pruning**

Beyond software distillation, architectural innovation is driving efficiency.

* **Mixture-of-Layers Distillation:** Researchers found that a student's layer ![][image9] does not necessarily correspond to the teacher's layer ![][image9]. MoL techniques use an attention mechanism to dynamically align the student's layers with the most relevant intermediate layers of the teacher, allowing for more efficient feature transfer.31  
* **Structured Pruning (Minitron):** NVIDIA's Minitron approach involves taking a large pre-trained model (e.g., Llama 3.1 8B), analyzing the importance of each neuron and attention head, and physically excising the least important ones to create a smaller variant (e.g., 4B). This pruned model is then "healed" through a brief period of retraining (distillation). This method is far more computationally efficient than training a 4B model from scratch and results in superior performance.32

### **2.2.4 The Privacy Dividend**

The combination of these techniques enables "Privacy-by-Design." By running a distilled, pruned, neuro-symbolic agent on a user's smartphone, enterprises can offer sophisticated AI features (like financial planning or health analysis) without ever touching the raw data. This is becoming a competitive advantage in 2026, where consumer trust is low and regulatory scrutiny is high.26

# ---

**Part III: The Synthetic Reality Zones (Multimodal Fluidity)**

## **3.1 The Rise of Native Multimodality**

In the "Synthetic Reality Zones," the distinctions between text, image, audio, and video have effectively dissolved. The defining technological shift of the mid-2020s is the transition from "stitched" multimodal systems to **Native Multimodal Models (NMMs)**.

### **3.1.1 Stitched vs. Native Architectures**

The previous generation of multimodal AI (e.g., early LLaVA or GPT-4 Vision) relied on "stitched" or "late-fusion" architectures. In these systems, a separate vision encoder (like a Vision Transformer or ViT) would process an image, convert it into vector embeddings, and then feed those vectors into a text-based LLM. The LLM never "saw" the image; it saw a mathematical translation of it.34

**Native (Early Fusion) Architecture:** Models like **GPT-4o** ("Omni") and Meta's **Chameleon** represent a paradigm shift to "early fusion." These models use a unified transformer architecture that ingests a single stream of interleaved tokens representing all modalities.35

### **3.1.2 Tokenization of Physics: How Chameleon Works**

The key enabler for NMMs is the ability to tokenize continuous reality (pixels, soundwaves) into discrete integers, just like text. Meta's Chameleon exemplifies this approach:

* **Image Tokenizer:** It employs a specialized tokenizer (likely a variant of a Vector Quantized Variational Autoencoder, or VQ-VAE) that converts a 512x512 image into a sequence of 1,024 discrete tokens.  
* **Codebook:** These tokens are selected from a learned "codebook" of 8,192 visual "words."  
* **Unified Processing:** These visual tokens are fed into the *same* transformer layers as text tokens. The model's self-attention mechanism attends to image patches and text words simultaneously, learning the semantic relationships between "visual cat" and "text cat" directly, without translation layers.37

This allows for arbitrary interleaving: the model can generate a sentence, then an image, then a sound effect, all as part of one coherent generation stream.

### **3.1.3 Latency and Responsiveness**

Native audio processing in GPT-4o has revolutionized human-computer interaction. By processing raw audio tokens directly (rather than using a separate Speech-to-Text ![][image10] LLM ![][image10] Text-to-Speech pipeline), the model captures paralinguistic features like tone, emotion, and background noise. It achieves response latencies of \~320ms, which mimics the cadence of natural human conversation and allows for interruptibility.36

## **3.2 The Epistemic Crisis: Truth in a Fluid Reality**

The capability of NMMs to generate hyper-realistic, multimodal content at scale has precipitated an epistemic crisis. When an AI can instantaneously generate a video of a CEO declaring bankruptcy or a politician confessing to a crime, the "integrity of truth" relies entirely on our ability to distinguish synthetic artifacts from captured reality.

The industry's response relies on two competing verification standards: **SynthID** (invisible watermarking) and **C2PA** (cryptographic provenance).

## **3.3 The Watermark War: Defense and Evasion**

### **3.3.1 SynthID: Statistical Biasing**

Google DeepMind's SynthID is the leading implementation of "imperceptible" watermarking. Unlike a visible stamp, SynthID modifies the *probability distribution* of the generation process itself.40

**Technical Mechanics (Tournament Sampling):**

1. **Generation:** When the model (e.g., Gemini or Imagen) predicts the next token (text) or pixel (image), it generates a list of plausible candidates.  
2. **The G-Function:** A pseudorandom function ![][image11], keyed by a secret private key, assigns a "watermark score" to each candidate.  
3. **Biased Selection:** The model is steered to select the candidate that maximizes this ![][image11]\-score, provided it doesn't significantly degrade the quality/coherence of the output.40  
4. **Holographic Nature:** This bias is distributed holographically throughout the content. It persists even if the image is cropped, resized, or compressed (JPEG), because the statistical anomaly remains detectable by a verifier who possesses the key.42

### **3.3.2 The Adversary: Warfare and Purification Attacks**

However, 2026 has demonstrated that no watermark is immutable. The **Warfare** framework (and its successor Warfare-Plus) has formalized automated attacks against these systems.43

**The Diffusion Purification Attack:**

Warfare leverages the very technology used to create images (diffusion) to scrub them.

1. **Noise Injection:** The attacker takes a watermarked image and adds Gaussian noise. This disrupts the delicate high-frequency patterns of the watermark (the statistical bias).  
2. **Denoising (Purification):** The noisy image is fed into a benign, open-source diffusion model (like Stable Diffusion Turbo). The model is tasked with "denoising" the image.  
3. **Reconstruction:** Because the benign model has no knowledge of the SynthID "G-function," it reconstructs the image based solely on its priors of what a "natural" image looks like. The result is a visually identical image with the watermark effectively "washed" away.44

**GAN-Based Forgery:** More alarmingly, Warfare uses Generative Adversarial Networks (GANs) to learn the inverse mapping of the watermark. By training on pairs of images, a GAN can learn to *inject* the watermark into clean images, allowing attackers to frame innocent users or create "verified" deepfakes.44

### **3.3.3 The Fallback: C2PA and Provenance**

Given the vulnerability of watermarks, the **Coalition for Content Provenance and Authenticity (C2PA)** advocates for a cryptographic "chain of custody."

* **Hard Binding:** Metadata (creator, tool, edit history) is cryptographically hashed and signed with the creator's private key. This creates a tamper-evident seal.  
* **The Analog Hole:** The weakness of C2PA is the "analog hole"—if a user takes a screenshot of a verified image, the metadata is stripped.  
* **Soft Binding:** C2PA standards now recommend using "soft bindings" (invisible watermarks like SynthID) as a backup mechanism to re-link content to its provenance if the metadata is lost.45

Ultimately, the defense of truth in 2026 is not a single technology but a layered "Zero Trust" architecture, where content is assumed synthetic unless verified by both cryptographic signatures and watermarking analysis.

# ---

**Conclusion: The Convergent Future**

The trajectory of Artificial Intelligence in 2026 is defined by the tight integration of these three domains. We are not merely building smarter models; we are constructing a comprehensive **synthetic nervous system** for the digital economy.

The **Agentic Groves** provide the "executive function"—the ability to plan, reason, and act autonomously. To make this ubiquity economically and legally viable, this intelligence is being compressed into the **Edge Thickets**, where distillation and neuro-symbolic architectures allow complex reasoning to occur on the devices in our pockets. Finally, as these agents generate and consume a torrent of multimodal data, the **Synthetic Reality Zones** provide the immune system—the watermarking and provenance layers necessary to maintain a shared consensus of reality.

For the organizations building the future, success lies not in mastering one of these fields, but in orchestrating them in unison: deploying agents that are safe by design, efficient by necessity, and truthful by verification.

### **Tables of Comparison**

**Table 1: Evolution of Agentic Architectures**

| Feature | Conversational (2023-2024) | Agentic (2025-2026) |
| :---- | :---- | :---- |
| **Interaction Model** | Prompt-Response (Single Turn) | Goal-Delegation (Multi-Turn) |
| **Control Flow** | Linear (User drives loop) | Cyclic (Agent drives loop via Graph) |
| **Tool Use** | Read-Only (Search, Retrieval) | Read-Write (Transactions, API calls) |
| **Security** | Input Filters / RBAC | Programmable Semantic Guardrails (NeMo) |
| **Human Role** | Initiator / Editor | Supervisor / Approver (HITL) |

**Table 2: Knowledge Distillation Paradigms**

| Approach | Mechanism | Limitation | Advantage |
| :---- | :---- | :---- | :---- |
| **Standard KD** | Logit Matching (Answer mimicking) | Student learns "what" but not "why" | Simple to implement |
| **TinyLLM** | Teacher-Forcing CoT (Rationale mimicking) | Limited by teacher's specific biases | Transfers reasoning capabilities |
| **NesyCD** | Neural \+ Symbolic Retrieval | Requires external Knowledge Base | Solves "long-tail" knowledge gaps |
| **Minitron** | Structured Pruning \+ Retraining | Requires access to base model weights | massive inference efficiency |

**Table 3: Multimodal Architectures**

| Architecture | Data Flow | Latency | Capability |
| :---- | :---- | :---- | :---- |
| **Stitched (Late Fusion)** | Image ![][image10] Encoder ![][image10] Vector ![][image10] LLM | High (Sequential processing) | Description, basic Q\&A |
| **Native (Early Fusion)** | Tokens (Text/Img/Audio) ![][image10] Transformer | Low (Parallel processing) | Interleaved generation, Native Audio |

#### **Works cited**

1. The Great Autonomy: How Agentic AI Transformed from Chatbots to Coworkers in 2026, accessed January 27, 2026, [https://markets.financialcontent.com/stocks/article/tokenring-2026-1-26-the-great-autonomy-how-agentic-ai-transformed-from-chatbots-to-coworkers-in-2026](https://markets.financialcontent.com/stocks/article/tokenring-2026-1-26-the-great-autonomy-how-agentic-ai-transformed-from-chatbots-to-coworkers-in-2026)  
2. LangChain State of AI Agents Report, accessed January 27, 2026, [https://www.langchain.com/stateofaiagents](https://www.langchain.com/stateofaiagents)  
3. Agentic AI’s Market Overhaul: Finance’s Autonomous Revolution in 2026, accessed January 27, 2026, [https://www.webpronews.com/agentic-ais-market-overhaul-finances-autonomous-revolution-in-2026/](https://www.webpronews.com/agentic-ais-market-overhaul-finances-autonomous-revolution-in-2026/)  
4. Insights 15: The State of AI Agents in 2025: Balancing Optimism with Reality \- AI2 Incubator, accessed January 27, 2026, [https://www.ai2incubator.com/articles/insights-15-the-state-of-ai-agents-in-2025-balancing-optimism-with-reality](https://www.ai2incubator.com/articles/insights-15-the-state-of-ai-agents-in-2025-balancing-optimism-with-reality)  
5. Securing GenAI with AI Runtime Security and NVIDIA NeMo Guardrails \- Palo Alto Networks, accessed January 27, 2026, [https://www.paloaltonetworks.com/blog/network-security/securing-genai-with-ai-runtime-security-and-nvidia-nemo-guardrails/](https://www.paloaltonetworks.com/blog/network-security/securing-genai-with-ai-runtime-security-and-nvidia-nemo-guardrails/)  
6. NVIDIA-NeMo/Guardrails: NeMo Guardrails is an open-source toolkit for easily adding programmable guardrails to LLM-based conversational systems. \- GitHub, accessed January 27, 2026, [https://github.com/NVIDIA-NeMo/Guardrails](https://github.com/NVIDIA-NeMo/Guardrails)  
7. Architecture Guide — NVIDIA NeMo Guardrails, accessed January 27, 2026, [https://docs.nvidia.com/nemo/guardrails/latest/architecture/README.html](https://docs.nvidia.com/nemo/guardrails/latest/architecture/README.html)  
8. NeMo-Guardrails: A Comprehensive Guide on how to get started with NeMo-Guardrails | by Negin Schmidt | Deloitte Artificial Intelligence & Data Tech Blog | Medium, accessed January 27, 2026, [https://medium.com/deloitte-artificial-intelligence-data-tech-blog/nemo-guardrails-a-comprehensive-guide-on-how-to-get-started-with-nemo-guardrails-695b0fb5fc4f](https://medium.com/deloitte-artificial-intelligence-data-tech-blog/nemo-guardrails-a-comprehensive-guide-on-how-to-get-started-with-nemo-guardrails-695b0fb5fc4f)  
9. About Guardrails — NVIDIA NeMo Microservices Documentation, accessed January 27, 2026, [https://docs.nvidia.com/nemo/microservices/latest/guardrails/index.html](https://docs.nvidia.com/nemo/microservices/latest/guardrails/index.html)  
10. Building LangGraph: Designing an Agent Runtime from first principles \- LangChain Blog, accessed January 27, 2026, [https://www.blog.langchain.com/building-langgraph/](https://www.blog.langchain.com/building-langgraph/)  
11. Understanding LangGraph with building an AI investment analyst : Part 1 | by Ishan Das | Jan, 2026 | Medium, accessed January 27, 2026, [https://medium.com/@ishan.das387/understanding-langgraph-with-building-an-ai-investment-analyst-part-1-068f11e10739](https://medium.com/@ishan.das387/understanding-langgraph-with-building-an-ai-investment-analyst-part-1-068f11e10739)  
12. Build a Fullstack Stock Portfolio Agent with LangGraph and AG-UI | Blog | CopilotKit, accessed January 27, 2026, [https://www.copilotkit.ai/blog/build-a-fullstack-stock-portfolio-agent-with-langgraph-and-ag-ui](https://www.copilotkit.ai/blog/build-a-fullstack-stock-portfolio-agent-with-langgraph-and-ag-ui)  
13. Building AI Agents with LangGraph: A Beginner's Guide | Agentic AI Course \- YouTube, accessed January 27, 2026, [https://www.youtube.com/watch?v=assrhPxNdSk](https://www.youtube.com/watch?v=assrhPxNdSk)  
14. Build durable AI agents with LangGraph and Amazon DynamoDB | AWS Database Blog, accessed January 27, 2026, [https://aws.amazon.com/blogs/database/build-durable-ai-agents-with-langgraph-and-amazon-dynamodb/](https://aws.amazon.com/blogs/database/build-durable-ai-agents-with-langgraph-and-amazon-dynamodb/)  
15. Beyond input(): Building Production-Ready Human-in-the-Loop AI Agents with LangGraph, accessed January 27, 2026, [https://dev.to/sreeni5018/beyond-input-building-production-ready-human-in-the-loop-ai-with-langgraph-2en9](https://dev.to/sreeni5018/beyond-input-building-production-ready-human-in-the-loop-ai-with-langgraph-2en9)  
16. Oversee a prior art search AI agent with human-in-the-loop by using LangGraph and watsonx.ai \- IBM, accessed January 27, 2026, [https://www.ibm.com/think/tutorials/human-in-the-loop-ai-agent-langraph-watsonx-ai](https://www.ibm.com/think/tutorials/human-in-the-loop-ai-agent-langraph-watsonx-ai)  
17. Secure “Human in the Loop” Interactions for AI Agents | Auth0, accessed January 27, 2026, [https://auth0.com/blog/secure-human-in-the-loop-interactions-for-ai-agents/](https://auth0.com/blog/secure-human-in-the-loop-interactions-for-ai-agents/)  
18. LangGraph Intro \- Human-in-the-Loop: Collecting and Processing User Feedback in AI Agent Workflows \- YouTube, accessed January 27, 2026, [https://www.youtube.com/watch?v=DZVtftZsr60](https://www.youtube.com/watch?v=DZVtftZsr60)  
19. Implementing Asynchronous Human-in-the-Loop Authorization in Python with LangGraph and Auth0, accessed January 27, 2026, [https://auth0.com/blog/async-ciba-python-langgraph-auth0/](https://auth0.com/blog/async-ciba-python-langgraph-auth0/)  
20. Allowing Human Feedback in Agents | AutoGen 0.2 \- Microsoft Open Source, accessed January 27, 2026, [https://microsoft.github.io/autogen/0.2/docs/tutorial/human-in-the-loop/](https://microsoft.github.io/autogen/0.2/docs/tutorial/human-in-the-loop/)  
21. Decoding Duty of Care in the Agentic AI Era, accessed January 27, 2026, [https://www.corporatecomplianceinsights.com/decoding-duty-care-agentic-ai-era/](https://www.corporatecomplianceinsights.com/decoding-duty-care-agentic-ai-era/)  
22. When Chain of Thought is Necessary, Language Models Struggle to Evade Monitors \- arXiv, accessed January 27, 2026, [https://arxiv.org/html/2507.05246v1](https://arxiv.org/html/2507.05246v1)  
23. Chain of Thought Monitorability: A New and Fragile Opportunity for AI Safety \- arXiv, accessed January 27, 2026, [https://arxiv.org/pdf/2507.11473](https://arxiv.org/pdf/2507.11473)  
24. Policy Frameworks for Transparent Chain-of-Thought Reasoning in Large Language Models \- arXiv, accessed January 27, 2026, [https://arxiv.org/html/2503.14521v1](https://arxiv.org/html/2503.14521v1)  
25. 10 Key Privacy Developments and Trends to Watch in 2025 \- Wiley Rein, accessed January 27, 2026, [https://www.wiley.law/alert-10-Key-Privacy-Developments-and-Trends-to-Watch-in-2025](https://www.wiley.law/alert-10-Key-Privacy-Developments-and-Trends-to-Watch-in-2025)  
26. AI Data Privacy Statistics & Trends 2025 \- Protecto AI, accessed January 27, 2026, [https://www.protecto.ai/blog/ai-data-privacy-statistics-trends/](https://www.protecto.ai/blog/ai-data-privacy-statistics-trends/)  
27. Beyond Answers: Transferring Reasoning Capabilities to ... \- arXiv, accessed January 27, 2026, [https://arxiv.org/abs/2402.04616](https://arxiv.org/abs/2402.04616)  
28. Xnhyacinth/NesyCD: \[AAAI 2025\] Neural-Symbolic ... \- GitHub, accessed January 27, 2026, [https://github.com/Xnhyacinth/NesyCD](https://github.com/Xnhyacinth/NesyCD)  
29. Neural-Symbolic Collaborative Distillation: Advancing Small Language Models for Complex Reasoning Tasks \- arXiv, accessed January 27, 2026, [https://arxiv.org/html/2409.13203v4](https://arxiv.org/html/2409.13203v4)  
30. Neural-Symbolic Collaborative Distillation: Advancing Small Language Models for Complex Reasoning Tasks, accessed January 27, 2026, [https://ojs.aaai.org/index.php/AAAI/article/view/34636/36791](https://ojs.aaai.org/index.php/AAAI/article/view/34636/36791)  
31. Improving Reasoning Capabilities in Small Models through Mixture-of-layers Distillation with Stepwise Attention on Key Information \- ACL Anthology, accessed January 27, 2026, [https://aclanthology.org/2025.emnlp-main.250/](https://aclanthology.org/2025.emnlp-main.250/)  
32. How to Prune and Distill Llama-3.1 8B to an NVIDIA Llama-3.1-Minitron 4B Model, accessed January 27, 2026, [https://developer.nvidia.com/blog/how-to-prune-and-distill-llama-3-1-8b-to-an-nvidia-llama-3-1-minitron-4b-model/](https://developer.nvidia.com/blog/how-to-prune-and-distill-llama-3-1-8b-to-an-nvidia-llama-3-1-minitron-4b-model/)  
33. Building trust in the age of AI \- Cisco Newsroom, accessed January 27, 2026, [https://newsroom.cisco.com/c/r/newsroom/en/us/a/y2025/m04/building-trust-in-the-age-of-ai.html](https://newsroom.cisco.com/c/r/newsroom/en/us/a/y2025/m04/building-trust-in-the-age-of-ai.html)  
34. The Evolution of Multimodal Model Architectures \- arXiv, accessed January 27, 2026, [https://arxiv.org/html/2405.17927v1](https://arxiv.org/html/2405.17927v1)  
35. Scaling Laws for Native Multimodal Models \- Apple Machine Learning Research, accessed January 27, 2026, [https://machinelearning.apple.com/research/scaling-laws-native-multimodal-models](https://machinelearning.apple.com/research/scaling-laws-native-multimodal-models)  
36. What Is GPT-4o? | IBM, accessed January 27, 2026, [https://www.ibm.com/think/topics/gpt-4o](https://www.ibm.com/think/topics/gpt-4o)  
37. Chameleon: Mixed-Modal Early-Fusion Foundation Models \- arXiv, accessed January 27, 2026, [https://arxiv.org/html/2405.09818v1](https://arxiv.org/html/2405.09818v1)  
38. Multi Modal Tokenizing With Chameleon | Alan Dao's personal blog, accessed January 27, 2026, [https://alandao.net/posts/multi-modal-tokenizing-with-chameleon/](https://alandao.net/posts/multi-modal-tokenizing-with-chameleon/)  
39. Multimodal AI Models A Comparison and Benchmark \- Cension AI, accessed January 27, 2026, [https://cension.ai/blog/multimodal-ai-comparison-benchmark/](https://cension.ai/blog/multimodal-ai-comparison-benchmark/)  
40. SynthID: Tools for watermarking and detecting LLM-generated Text ..., accessed January 27, 2026, [https://ai.google.dev/responsible/docs/safeguards/synthid](https://ai.google.dev/responsible/docs/safeguards/synthid)  
41. GeminiWatermarkTool/report/synthid\_research.md at main \- GitHub, accessed January 27, 2026, [https://github.com/allenk/GeminiWatermarkTool/blob/main/report/synthid\_research.md](https://github.com/allenk/GeminiWatermarkTool/blob/main/report/synthid_research.md)  
42. SynthID Explained: A Technical Deep Dive into DeepMind's Invisible Watermarking System, accessed January 27, 2026, [https://dev.to/grenishrai/synthid-explained-a-technical-deep-dive-into-deepminds-invisible-watermarking-system-38n7](https://dev.to/grenishrai/synthid-explained-a-technical-deep-dive-into-deepminds-invisible-watermarking-system-38n7)  
43. \[2310.07726\] Warfare:Breaking the Watermark Protection of AI-Generated Content \- arXiv, accessed January 27, 2026, [https://arxiv.org/abs/2310.07726](https://arxiv.org/abs/2310.07726)  
44. Warfare: Breaking the Watermark Protection of AI-Generated Content \- arXiv, accessed January 27, 2026, [https://arxiv.org/html/2310.07726v3](https://arxiv.org/html/2310.07726v3)  
45. C2PA Implementation Guidance, accessed January 27, 2026, [https://spec.c2pa.org/specifications/specifications/2.3/guidance/Guidance.html](https://spec.c2pa.org/specifications/specifications/2.3/guidance/Guidance.html)

[image1]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAHUAAAAXCAYAAAA1OADtAAAE1ElEQVR4Xu2ZaaiuUxTH/0KZpytDyDEPEeLSlXRJhkS66N7wgWTIB9NNIkPS/WBKIYQyJUL5QrkRJ4SQKcMHfCBRChEyZPj/3vXs++5nv8/zDud23pN6/vXvnGc/+33PXuu/1tpr7yN16NChQ4cOHeYLM+aKcrDC6ebh5ibmOuY25lnmgfmkKWAz8xLzPvMGc0/FenKsa55o3l3xNHPD2oyFA2u91LywfKG6bdeaO9Vf94AdZyjm3GzuVX8d2Me8yHzJ/Nt8uP66h/XMJ81/Cz5lbp7Nm28cYM6aS80tzQvMP82V6gu7vnmneb25m3me+av5kblzNWchcZhiPVcW46xttXm8ub3Cxg/MZdkcfP2CeaMiuUioT8xTszk9IOopiiz8Ws2iggcUjvnKfFqRCWTENHGHIvBOrp4R9m3ze4UdAKe8aO5QPQMqCkGIDQToQgFRSB7WkotKQN6luoAAW15RP3H4DPZid8KZ5qfmttnYGhAdX6pdVKL/4HJwDLDgmepnGxaZG5eDDbhN4ZBzq+dNzVfNnxVZDDA8CZiwoyJgv1CL8VMA9l9u3qLBTCXrZs2zszGAv99RrDkFcKnPYvMX9QO9hvkSlcy42rxMzcKSYc9pvNJIad1a/Qqxn/mjwiE4Bhxivm+eXz2DZBvk94UAZfdWc4kGRcVHVD+2kisUduKrq8x7qvf4iYpU6oMmfN+qYryHUaJSHm4331VE/RvmQbUZ7WCRRCgLzoWdRNASNBWPKbaDUc3aEeZf5jPmBsW7aYDySWMzo74I5Z56qCJAqTJvKXzNelPpTZ8r9Wkb72GUqA8qIidlCfvUD4rFjINS2LkKSpl+QiEm5fQ4Dd/b+busHYeNWisdJ987Lp83t+p9sh3YSpXi9ADaRAVHmX+o34hep37XflI1VuqzVqKyf+XOS/vU4xq/+UjC3q+5CVpib/Mb81G178l0ht+ax5QvpgQCiV4A20GbqFQbqiBNK8lDQ4iIjyiEPaF6LvVZK1FLpPmTNh/seQhxjZr32EnA5ynBGNt07sOhOGpx+WJKYJ+/V1F2E5pE5czPOvPud1/zPfMfRRfcJl7beA/DRD1H8eW54+bSfBCNq809FKUlleJxQKRTxmCKepC63XLdCPqauXv1TDVhy9hizYxBIAK2jEvEGFb69zc/VL1kf6dYLx0rz1QQspDjIk1gDpKF4wo27qqoOKWdSVSa0QEMEzU5Lhc1ld9Z9TvPYUiCppKLMJMImxYP8y6c9bI2zrAJ/A26yby84zCaFbaRNiACt0/jEjEmvalqylT2y/L8CVIl4pIlHXvYtvJmj6Cga27cXpKofEnp5CWK7jfPkOXm72q4zWgAgj6rwT10EmG5MvvMfEj9jnCRolOkCUqd+HaKAztNXJkh3IqNu//PF9gKflM9s0gQbo/waQ56Bk4Zu1TPVBpsSc/4jNulN1Xc7KEwGZc25lQaKBtELuDDK82XFQd/soIzE9eLo8TYSNEclYImUL4uVtxojQKZ8bl5k+KOmqj9qRpPSFWliauyedMGpfp11f1MoKUMI3EorzRG2IaNlN6jq/eAJODcig40VAj6sUYf6YaCbOHLjtV073xzUHqWKsrfkapXj/87sAWbhtlGEvFPjGFzOnTo0KFDhw4dOpT4D6/9H/dT832pAAAAAElFTkSuQmCC>

[image2]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAEwAAAAYCAYAAABQiBvKAAADKUlEQVR4Xu2YWahNURjH/zJnJiRjkjJkCEkZbkI88IIoQgkliSIZyoOEoowpKeHFmAeKB3HxoCjxgBJ1SXmiiFIy/P99Z9279rp7n3P2Gdxza//qV3d/e+9zzl7r+7619gUyMjIyWoyutI7Ooz1ysT60r7ugWGbTd/RDkc6x21oN7eke2DNuphvpU3qYPqSjmi4tTBt6kl6mw3LH4iz9Q+fnjtvSWbSBTsnFWgPt6Gl6iXbx4sqsJ7QelnlF059eof28WC/YDDTQgV5cH3yRDvJitc40+p6ODU+QXfR4GCyEymtrEBtPv9FrsBlyaCD1Bd28WLXpRNcjZRZ47KcfET/J2+miMFiIpXRkEFtB/9IdQVxprB/vyvZ/oO/SQ08KTxTJediz7IS1FZ8RtHcQKwn1r190eniihdBgHUE024tlOWzA5G96j66l3f2LyiGpfyWhklEf1EokOqDyGajP20JX5f5Og37XAdhguYGTLxBfpqnRbP5A8/4VMpreh60+q+kx2GweRP77RE86IKVD6Dl6AqVlh8pR24dD9Cts0DZErrBJeU7f0AewFfQx3Us7N10WJal/OTTDa+gj2DbEoZm8geT7HFrad9MzJXgHNpn7aEfkRwOkHhWXkdoqacsU91vVLzUx7j4tcHrWTY1XeOgiXZyvf82AbQDHhCdgq221NrWT6VUUX0bDYdkYl+2uipQcPprMu4hmnmtRGshmFOpfWtrrYRvduJmbC1tJK40+U/u/oeGJPGi7cBPWY0NWwspucBDXIL9CdEVWgujtZqIXa6RQ/9L5L6heFiWhVxn1xzQoI/QsU4O4ylQNf3EQFwvoZ7qOLoEtFrcQbLt08Aw2EP4q8p2+RnS0F9JPsJlwzES0z0zwzlUCZcgpxGd8EqqE63QbfZn7W1uJo7DqWYb4CtEgJyVLSSiz1L/CPqJjxd17ZyXRg6nxxj1gElrRlElCi5H6nzKmDvElKly7CVfOstD7prJRM+SjgVJPSJMFtYaq5i2SF7uSUclpr6L01azp3yUqGa1ISbNX66hcb9Of9AIdFz1dPtrjKNu0oSz1pTgjIyOjXP4BhWCYOBTbirIAAAAASUVORK5CYII=>

[image3]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABcAAAAYCAYAAAARfGZ1AAABX0lEQVR4Xu2UvSuGURjGL/nI8BqkSAwyGBgo2XyUKIvNG2VgMiqTv0BZfS1SBgtS/gTKqGRTSsliM4hJ4brcz8npeJ7zvB+D5b3qN5zrdM5z7uu5zwFq+i9NkgfyVCJTtixfdWSXnJCeZCwdkE8yk4zryQR5JCOJl6sOckraPa+VXMM26vL8Ajki3Z4XlUpcC7xB8krOSIPn66PbpMXzoiqSvsBbJF9kPfDbyAp+o6tIyvuDjIYT1Sor7yw1w/5bYzJuQqSyYfKOv3mH6icX5JgskS2yQDYRWZeVt5NOtUyuYK3rpJOfI3vdz8JDxPMeg124gXAC1nWZFywvb/X5JezSpeU6DeuoVOXlrfkXRE4XSj1+A1ukrB1v5A62odMseSa9njdO9j2GvLmypBMr7/D6ayzfvUMVSe+PqpwPfG16j/T/VJZU9i3ZIHNkleyRHdiFqlp6flVFJ6yDaipd3/BzQ0/BC224AAAAAElFTkSuQmCC>

[image4]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABcAAAAYCAYAAAARfGZ1AAABh0lEQVR4Xu2UPyiFURjGH6GI/M3GIotSBiRluJNYLBTFZlAGE4lsEooSg8XilrKYbAbdDAYWBiUSyi6D0Z/nue/3ueeee1Pf5473V7/u7T2nc97vPe85QJGIVNMEHaC1QayRNoUT4lBOl+kjnaUz9Ipu0nPanpkajTK6R49olRNXxpc0BfuiWPTRF9rhD5AluuMHo7BKX2mzP0Dm6bAfjMIB/aaLtNQba6MNXiwS47DF5Sc9o1O0xp0UF3XKGmzhcBN5g/ylioVKopbboO+wDaad8TqapPf0GtZF8oIO0ZJwotBiqmlWMGCQftEFL14Pa0/3kHvoE7xua6W7sD736aIfdMKLd8Iydy9VP30Lfn/R7ie0wg0GTMIWafHi2iyFzKXSV6/QUyeWRv2t7HrdIKxUOswRLy72Yc/BKGyjQ7qF7Jud3uWYztHb4L/ab5s+0zHknoXqrffGL1UOlbAMhVqxG5ZNAvnLJHQOD/jHI/YXyliZ6wsKhvp7nd7BWk4HWJDbW6Qw/ADlEEGmKe5eVAAAAABJRU5ErkJggg==>

[image5]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFYAAAAYCAYAAABgBArrAAADWUlEQVR4Xu2YS6hNURjHP3lESCJveRRFZCDq5lVSKJlgIBl5TUwwkDI1MpDXRORGkueIQgY3BhRhghKFPIpQQlx5/H93reWss849++yjc7qu9q/+tfdaa6999re+71vfOmYFBQUFBc1mofREep5Ti9xj/zxDpevSr0jtUqvU14+ZI32N+t9I030f9JGOmHsunueV9Mlfv5Q2S739Mx30kA5Ip6Tx/h4OSz+lJf6+p7RAeirN8m3dhaXmDLAv7RD9zBluvzQ86YuZIr2TTljJRoBddpqbf1vU3jHZaWlY1DZYumXOiKOj9gHScWlM1NYd2GXuw5cn7SOk8749NlZnMIY5NqUdYqb0WWozZ6MOCOst4cYzQ/oonZV6Re0YnFUfGLU1m2VWHpr1QshfNOdteF2AqDtnLkrzwOJgPIyYEox+0iJ7rZImhxvPGnMDtyftQ6SNVnt1GwmpKF34epgovbaSN/Hb10oHpf6lYZnwXJt031zejhkkXZPemnPITMiv36W5aUcXwEfxe8amHTkhItkr8DgMiUG/SC3xoBqExSFtjJJGes2T7vj2mumxWn7tSmZLey2/h8WE/LrVXOizUXHPhp038kKoX5EORbpgruqYbznmCok4za+A95yR7pkLjQdeXN+Q7kpT/dhqkPPCitej9eZCrtb8MSG/YpTL5jarCdILL67zUC2/Yswd5ubfkPRVUC2/Qou5lafEwOgYn5cC97stu2SBlVa+6nlFmfNBuiSNs3yEEGZByIUQyku+kdqzFln5FYIjXrWMiOKlR616fmXjCqtMmnhkpcMChsXof8qNBoJRMOxiyxFyEaF+DYsfwEG+STetZPBqVKtfA2yu5HAiIxw6KqiVX9lAwuQY/rE5rwAMO8lfNxLeRwG+Iu3IQcivGDiGQwGeHx+AqpFVv3LS4gzwwypr5DKy8msKqSJzlRrENHM7ea3fkxJCmFQQFj8mpDwMU3YUTaBup4qg7o2h9MSLmYMTV4U3U8NSMrw3NyiIc/BDq0zYkObXZsKmkOkNCZwg2anbrfxbqAY498Mec14W96/2fYCztPr2MAb7hP9KuGZ+qoJ6NtOapPm1mbAhZHnUfwUGfWadh1jBX0AhTOlz21wuPiatKxtRUFBQUFDQZH4D2N3NAYF7T1EAAAAASUVORK5CYII=>

[image6]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABYAAAAYCAYAAAD+vg1LAAABPElEQVR4Xu2TvytGURjHHzEYGN4UA4q3GCwGGZQoGfwDpndUdhZ/gckmk5Ri8mO12wyEiRKFP8AgJoXPt3Pe7nVO56L79k7vpz51znPuPU/3e841a9Es5vABn//ovHutmDbcwgMc8nOxg5+44OftOIuPOOlrhfThIfbmahU8N7dJf67ehfs4kKsl0WetBLVxfMVj7MjV1XATu3O1JIs4GtRq+IVrQb0Hly2L698o3w+cDhfKkMq3NBP4bnG+Qod3hNd4ijdejc/wCsf8sxGpfMUUrpq7emqq5ut+TfMNc7csQoeya+l8dXDDfqyY7iz7WbSxmuqrIn7Ld9CyG6HG91j1c2084scRRfmGKKoT7AwX6ugOX+KLuWzrvuGtuWYhYb4NI8y3YWjDJ8vyLc0MbuOFubPYw6UfT7RoGt/4uEFBjiqT8gAAAABJRU5ErkJggg==>

[image7]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAIYAAAAYCAYAAAA/FYWiAAAFUklEQVR4Xu2Za6hlYxjHH7nkfo8M5TDGPZJLyGVccvlAiNzzQfhgkksug3JKEj4IiUSGksat1KAm6QzlOrmUWxPNkEsRUkgjl/9vnvXMfve71t5rr7P3mdPO+tW/c/Z61zlrve/7PM/7f99t1tLS0tLS0jIEG0r7SWdIE9J6xbW5yT3jyHbSSdJ8aePi2k7SVnFDU46TfpT+TfSzdHFyz+1Z+4vSZkn7RtJj0ursvu+k34rfv5UWmE/CbHG8tFK6X7pQelZ6XlosXZHcN04wD49Ly6VLpZulj6RJaZm0/do7p8mj0j/SiXmDmCe9I11knWisYh/pJ+kp80wM1pduNQ+Q65Lr65LTpRXm1SLgHQn636WDk+vjwubSUvM+pAm3h3lSEjDpPDRmG+k9aZW0c3fTmixbYl5262Dwmfyq7GPgmYAp8w4Nyo7SI9ZdoZpCOX3bvGLlHCq9ZSPIrFngPOkT8zFKIRhIzqp5aERk+kvWqQhk+VXSndImxbU67rDe2RdB87S0QdbWD9bJJ6xZMOUcJf0lnZU3mL/rfTZkZk2TraXLrdl4BPzNc9Ib0hZZGzxg1fPQCNZbJu3G4jPZ+aC5zxh0wJi4KfMIzrOPjH3d3MscmLXVMYrAOM28f69J22ZtfKb0zgYk3MNWrtKDEOP9t3SulefpABs8oXuCGSOjyKw9pQ/MS28TR7u79L30gjTHfELR0dL7xfVd1t49OKMIjN2kb6xjij83r26zFRApVLFr8osDMmmdPmH8qSBn2wgCAsJffCVdaV7qCQqM6CnJfXXEUoEZwhOE8CeUu2OsHNWDMIrAgFOlH6x718RgUk1mE0zjXVZt+usgcfESaZ/Qyzb8eK31F5SkW8xfFFPT1A/08hcEw0Lz/3dZ1pbDmhuVJsTSw7aS7M7bptN5jBrbuo/N3yn1VXC19KH5DmaZebnGnN5m9ZlIXzlPyN+zTnubT+YNVv+MKpizw80TkWDPd5d7Sa9IX0rvmvcJ0S/6eWTcmBL+YqF1MprB+0z6Rdq/uNaPfv4CYkfyqvXeXXCdwEyrDSIjVppvvfI2JrgOlq+qZ0Yfp6wcYAQ5z4vxwNxR9ap2NSk7SPdY+T0H0ZvSr+bJg/HvB8Gza36xgHdkPvNKSAEgMNiFBfSPrW6l7+P8IvxFyqT5A/hZR6/zi4AliSjOs3MQyKjpLiVUO9w5/icngpl1Oa2KBBEBnG71YrklYGYCfAbBsWXe0APminOhKgiIqvnkGWnizjPv9wXmY9xFdJhIyvfCVAoqBlmVt+X0O7+gzD1jvlRxX1OGCQzcPn6JwM1haVpl5S0sQfSpdS+JGOivpYOSa6OC96B/TYw+u0c2DDlRAaasPF7cH4k7R7qpuE41LFWoKPF51gCfuc6Ec+LZDx76h3WXKWC9DXPEiWdVNaljmMCI84t0mQRKMZWSLCVwUzCpVD9KOg6fcxwMNLu1UcM73S0dkTf0IeaFZJ7oblrjFVZIh2XXYykkuPEYfE2BhSiBMeHINFwswrGfX7SzVvIP0nbMGtEdsCQsss53IYjvWHg44vfV5oO6r//JtBgmMK6X7jUfSLbMmDsO7aiCBHOV92C5qEqUmYCy/pA16xtVcKl0rXnFWyRdYj5GLBXHxo0Jub8409xX8NyT46ZxY5jAwI1TEcjMCfNvVFmDey2N4TuqlsSZgBJedWrZDw7k4kCM5JxvXtkOsXL1C3J/san5s08oNJYwWefYuslg/MUXVjZu407qLwICjGraxNv8L2Hry17/T+lJ8yPlcWeu+VLFVxHLrbM1XmzuCRd0bm1paWlpaWlpmRn+A9i7JY4jyMUOAAAAAElFTkSuQmCC>

[image8]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABgAAAAYCAYAAADgdz34AAABmklEQVR4Xu2UPShGURjHH/mIfBWvjUQWZUMyKPWWWAwon5tBGUwkH6ukDPIqZTMoBpNdYsLCYFFCmZgMRh//v+eenPd573LvHSzvv369b/9z7jnn/s/zXJG8EqgC9II+UB14taDOTYirYrAKHsAcmAXXYBOcg9a/qdFVBHbBISj3fJ78CpyJvllsdYNn0GYHoGWwbc2oWgMvoN4OQAtg0JpRtQ++wRIoNGMtoMZ4kTUmugH5BKdgGlT5k5KIFbQuurjbiNxKeGyxxXhYjhvgXXSTGW+cVXUE7sGNaHWRC9HyHncTnbggMy6wA1A/+AKLxk+BOzBkfPbNgPGkGWRE+8CqHXyASeN3ip7WNV4jKBPtfj6TJZbfCSi1A9CUaBQNxmdkjKRStPlWRJuT8C6zxPrnKbuMz9h4wcPGZ5QH4A1cBr9cI1Tc/RjMi2bK/yzNLfAERiX3bmz+PSAtGjHvrCTwf8XceFKKr9YBRkSzDIuMsvlzQT7LT8yEm5REfv5OPChjavK8yGL9szceA/YC+Il5BTuSG2de/6wfNkNGK3miZwMAAAAASUVORK5CYII=>

[image9]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABIAAAAYCAYAAAD3Va0xAAABGUlEQVR4Xu2TsWoCQRCGR7BRQRECYmkpCBZiIdgkWATsbJPeRhDyBNfaaKGVVlY2Yi15Ap/AvICdiI1NLEz+310ve3vkvKu9Dz5YdpbZmbk9kZioPMM9/NGuYcqIZ+GnEacrmDHOuCTgFJ7hN2x4w1c6cCneS3zk4Rz2Rd04EZXc5AO+WXs+qnAEi/AL7mDJiCfhTJ8LhDd19doRVVXPjYo8iaqYlQcyhDW9rsAj3MCc3mvCsV7/y20+vJWwjQW8wFe9x2pDz8ccLhMwERPyK0Wezw22xNbY4ouEmA+rYO91OwDeRQ19CwdWzIc9H5OCqKfAZHfnw7L53NN2QOPAAyxb+y4teJK/f4e/RdtzQsGnwH8vcD4xD8kvcTMzNIxbkGYAAAAASUVORK5CYII=>

[image10]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABEAAAAUCAYAAABroNZJAAAAfklEQVR4XmNgGAWjAANwAHEaEPOgS5ACGIG4FYiN0SVIBSADeoGYBV2CFAByTQEQx0HZYCAAxJIkYjkgng/Ek4GYgRuIq4F4Fhl4BxB/ZaAAmADxaiCWQZcgFggD8WIglkeXIAVkAXEEuiApAJTYpgKxNLoEKQAUpbxQepABANsjErIyFZ/6AAAAAElFTkSuQmCC>

[image11]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAoAAAAYCAYAAADDLGwtAAAA6UlEQVR4Xu3RIWtCURjG8VemQUSG4NKaTAyGBTFZxQ9gMawsqclotohfwC4G0Y9gMAiCCAYtFkEsjjGWFLQMxf97z7njcsE4MOyBXzjPPQfec4/If/4qERSQwYPvmxMta1iijCYW2CLpbgqgjh1ebBfGECvEbSdpfKMt5pAmhjl6nk4auCDvFuQVB1TcQnfrqU8k3JK84YSsp5MuJojatR7uiG8+TRUbPNtNJZzFN58mhBY+sMYAP+KZ71Z0vqOYn/6bnJhbP9l1EH3M8Gg7JyN8ISVmnnfsUfTscaLvOsVYzPPpbfXQveQKbdYmrbYWwJYAAAAASUVORK5CYII=>