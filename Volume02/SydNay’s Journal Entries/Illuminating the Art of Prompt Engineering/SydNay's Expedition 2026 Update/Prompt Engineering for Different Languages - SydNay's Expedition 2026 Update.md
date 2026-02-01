# **The Silent Syntax: A SydNay Expedition Report on Linguistic Imperialism, Script Dynamics, and the Future of Multilingual AI**

## **Sector 1: The Cartography of Exclusion**

### **1.1 Introduction: The Digital Terra Incognita**

The mission of the SydNay initiative has always been to chart the unknown, to map the friction points between human organic chaos and the rigid, crystalline logic of synthetic systems. In our latest series of expeditions into the "LLM Universe," we have uncovered a topography defined not by its vastness, but by its shadows. The prevailing narrative of the 2024–2026 era is one of universal access and "multilingual" capability, a story told by the major model foundries of the West. Yet, the data recovered from our deep research scans—spanning thousands of journals, technical logs, and field reports—reveals a starkly different reality. We are witnessing a "digital-epistemic injustice" of planetary scale, a silent crisis where the architecture of artificial intelligence is actively reshaping the hierarchy of human expression, relegating billions of speakers to the status of "Invisible Giants."

This report serves as the comprehensive log of our findings. It is not merely a technical audit; it is an anthropological survey of a digital extinction event. Our sensors indicate that of the world's 7,613 living languages, approximately 2,000—spoken by millions of human beings—are effectively dark to the sensors of the current AI ecosystem.1 This is not a passive omission. It is a structural inevitability born of the "Tokenization Tax," the hegemony of the Latin script, and the conflation of "digitality" with "vitality."

The landscape we traverse is treacherous. From the "high fertility" wastelands of the Cyrillic and Devanagari scripts, where processing costs skyrocket and context windows collapse, to the "hallucination valleys" of Arabic and cultural pragmatics, where models speak with the confidence of a colonizer and the knowledge of a tourist. We have engaged with the emerging protocols of resistance—the "Dual-Script" fusions of the Hindi sector, the "Participatory Design" fortresses of the NativQA project, and the "Cultural Prompt Engineering" frameworks that attempt to bridge the gap between Western training data and Global South reality.

What follows is an exhaustive analysis of these phenomena. We have synthesized the signals from over one hundred distinct research artifacts, identifying the underlying currents that threaten to erode linguistic diversity and the engineering marvels rising to protect it. This is the map of the Invisible World.

### **1.2 The Architecture of the Tokenization Tax**

#### **1.2.1 The Latin Hegemony and the Efficiency Gap**

To understand the exclusion, one must first understand the gatekeeper: the tokenizer. In our examination of the foundational infrastructure of Large Language Models (LLMs), it becomes evident that the very mechanism of converting thought into computation is biased by design. The tokenizer is the lens through which the AI sees the world, and that lens is ground to the prescription of the Latin alphabet.

According to the demographic surveys of the Global Script Atlas, the Latin script is the dominant writing system for approximately 70% of the human population, a legacy of the Roman Empire, Christianity, and European colonization.3 This historical dominance has been codified into the digital DNA of the 21st century. The vast majority of open-source and proprietary models—Llama 3, GPT-4, and their derivatives—are trained on corpora where English and other Latin-script languages constitute the overwhelming majority of the data.4

The consequence of this imbalance is a phenomenon we have termed the "Tokenization Tax." When a tokenizer is trained, it optimizes for the most frequent patterns in its dataset. For English, this results in high efficiency: common words like "the," "algorithm," or "future" are assigned single tokens. The model "reads" these concepts as atomic units. However, for languages that share the Latin script but differ in morphology, or worse, for languages using entirely different scripts, the efficiency collapses.

Our analysis of the Ukrainian sector provides a stark illustration of this disparity. Research indicates that the efficiency of LLM tokenization differs radically across languages. A standardized information sample in Ukrainian requires up to three times more tokens to encode than the exact same information in English.4 This is not merely a technical quirk; it is an economic penalty. In a pay-per-token ecosystem, a Ukrainian developer or user pays triple the price for the same semantic output as their English-speaking counterpart.

Furthermore, this inefficiency impacts the "cognitive" capacity of the model. LLMs have fixed context windows—a limit on how much information they can hold in "working memory." If a language has high "tokenization fertility" (the mean number of tokens required to encode a word), it consumes the context window much faster. A 128,000-token window might hold a novel in English, but only a novella in Hindi or Khmer.4 This structural limitation means that, by definition, current AI models are "less intelligent" when processing low-resource languages, simply because they can remember less of the conversation.

#### **1.2.2 The "Invisible Giants" Framework**

The depth of this exclusion is best understood through the theoretical framework of "Digital-Epistemic Injustice," a concept crystallized in the 2025 research literature.1 This framework challenges the traditional "vitality" metrics of linguistics (which measure speaker population) by introducing the orthogonal axis of "digitality" (online presence).

Our expeditionary analysis has categorized the world's languages into four distinct quadrants, revealing the "Dark Matter" of the linguistic universe.

| Classification | Vitality (Real-World Speakers) | Digitality (Online Presence) | Implications for AI |
| :---- | :---- | :---- | :---- |
| **Strongholds** | High | High | **The Dominant Class.** Languages like English, Chinese, and Spanish. Models are optimized for these; tokenization is efficient; cultural nuance is relatively high. |
| **Digital Echoes** | Low | High | **The Ghost Class.** Languages like Latin and Ancient Greek. High digital corpus due to historical digitization, but few living speakers. AI performs surprisingly well here, often better than on living African languages. |
| **Fading Voices** | Low | Low | **The Endangered Class.** Indigenous languages (e.g., Ojibwe). High risk of extinction. AI efforts here are preservationist but data-starved. |
| **Invisible Giants** | **High** | **Low** | **The Crisis Class.** Languages like Javanese (68M speakers), Yoruba, and Bengali. Massive human populations but negligible digital footprint. These languages are "invisible" to the crawler bots that feed LLMs. |

The "Invisible Giants" represent the most profound failure of the current paradigm. The discrepancy is staggering: Javanese, spoken by a population larger than that of the United Kingdom, yields negligible results on platforms integral to LLM training, whereas Icelandic (350,000 speakers) possesses a substantial digital footprint.1 This paradox highlights that AI is not a mirror of humanity; it is a mirror of the digitized West. The "Invisible Giants" are trapped in a feedback loop: their lack of digital representation leads to poor AI performance, which discourages users from interacting with technology in their native tongue, further suppressing the generation of digital data.1

### **1.3 The Mechanics of Script Failure**

To understand why the "Invisible Giants" remain invisible, we must descend into the mechanics of the scripts themselves. The SydNay analysis identifies three primary failure modes corresponding to the major non-Latin script families: the Logographic Paradox, the Abugida Fracture, and the Directionality Conflict.

#### **1.3.1 The Logographic Paradox (Hanzi, Kanji)**

The logographic scripts of East Asia—Chinese (Hanzi), Japanese (Kanji), and Korean (Hanja)—operate on a fundamentally different principle than alphabets. Here, a single character represents an entire word or morpheme, encoding meaning directly rather than sound.3

Superficially, this should be an advantage for AI. A single token (one character) carries high semantic density. Indeed, Chinese is the second most widely used script in the world and has achieved "Stronghold" status.3 However, the "trade-off" described in classic linguistic theory—semantic transparency vs. phonological transparency—wreaks havoc on tokenizers designed for alphabets.7

* **The Vocabulary Explosion:** Functional literacy in Chinese requires knowledge of 3,000–4,000 characters. A tokenizer with a fixed vocabulary size (e.g., 50,000 tokens) must allocate a huge portion of its "slots" to these characters to represent them efficiently. If a character is rare, the tokenizer falls back to byte-level representation, smashing the elegant logogram into meaningless digital shards.7  
* **The Homophone Trap:** In Japanese, the mixture of logograms (Kanji) and syllabaries (Kana) creates a context-dependency nightmare. The same phonetic sound can correspond to dozens of different Kanji. Without "visual" grounding, LLMs—which are essentially statistical probability engines—often hallucinate the wrong Kanji, altering the meaning entirely. This is particularly acute in technical or formal contexts where precision is paramount.9

#### **1.3.2 The Abugida Fracture (Devanagari, Thai, Khmer)**

The most severe technical degradation occurs in the Abugida scripts used in South and Southeast Asia (Hindi, Thai, Khmer, etc.). These systems function on a syllabic basis where vowels are diacritics attached to a consonant base.7

* **The Diacritic Divorce:** Tokenizers trained on English tend to treat "accents" or "marks" as separate noise. In Hindi (Devanagari), the distinction between the short "a" (अ) and the long "aa" (आ) is critical. Standard tokenizers often split the consonant from its vowel sign, treating them as two separate tokens.5 This destroys the phonological unity of the syllable. The model sees "K" \+ "aa" \+ "L" instead of "KaaL," leading to a loss of semantic coherence and a massive increase in token count.12  
* **The Segmentation Crisis:** Thai and Khmer are written without spaces between words. This feature, known as *scriptio continua*, defeats the basic "whitespace splitting" logic of Western tokenizers. The model cannot tell where one word ends and the next begins. In Khmer, this results in the model treating entire sentences as single, unknown tokens, or arbitrarily chopping them into gibberish.13 This effectively locks these languages out of the "pre-training" phase unless specialized "SentencePiece" algorithms are employed.13

#### **1.3.3 The Directionality Conflict (Arabic, Hebrew)**

The Right-to-Left (RTL) scripts, primarily Arabic and Hebrew (Abjads), introduce a spatial conflict. These scripts are "consonant alphabets" where vowels are often omitted (unvocalized) and inferred from context.11

* **Bi-Directional Hallucination:** Code and English are Left-to-Right (LTR). When an LLM generates a mix of English and Arabic (e.g., in a programming context or a translation prompt), the "cursor" logic often breaks. We have documented instances of "bi-directional hallucination," where the model flips the order of words or inserts English syntax into Arabic sentences.13  
* **The Root System:** Arabic morphology is based on trilateral roots (e.g., *k-t-b* for writing). A single root can spawn dozens of words (writer, book, library). Western models often fail to capture this "root-and-pattern" morphology, treating *kitab* (book) and *katib* (writer) as unrelated tokens rather than derivatives of the same semantic core. This leads to a shallowness in reasoning, where the model misses the deep semantic connections inherent to the language.11

## ---

**Sector 2: The Engineering of Resistance**

### **2.1 The Evolution of Prompt Engineering**

In the face of these structural exclusions, the "SydNay" expeditions have observed a rapid evolution in the field of Prompt Engineering. What began as a dark art of "syntax hacking"—tricking the model into obedience—has matured into a formalized discipline of "Cultural and Scriptural Engineering." The objective has shifted from merely getting an answer to forcing the model to traverse specific "local learning" pathways that bypass its "global" (Western) biases.17

The following subsections detail the advanced methodologies currently being deployed on the front lines of multilingual AI.

### **2.2 Dual-Script Fusion: The Hindi Protocol**

One of the most innovative breakthroughs recorded in the 2024–2025 journals is the "Dual-Script Enhanced Feature Representation" for Hindi.18 This technique acknowledges the reality of the "Digital Giant": Hindi speakers often write in Romanized script (Hinglish) online, but the formal language is Devanagari.

* **The Mechanism:** Researchers have developed architectures that accept *both* scripts simultaneously. The model is fed the Devanagari text alongside its Romanized transliteration.  
* **The Fusion:** Using cross-attention mechanisms, concatenation, or convolutional networks, the model fuses the embeddings of both inputs.  
* **The Logic:** The Romanized script acts as a "phonetic bridge." Since the model is highly optimized for English/Latin characters, the Romanized input provides a stable "scaffold" for the meaning, while the Devanagari input provides the precise cultural and phonological detail.  
* **The Result:** Experiments show that this "Dual-Script" approach significantly outperforms single-script models in text classification and machine translation tasks.18 It effectively uses the model's "English bias" as a tool to support the low-resource script, turning a weakness into a structural support.

### **2.3 TALENT: The Textbook Acquisition Protocol**

For languages that lack the "bridge" of a widely used Romanized version, the TALENT (Translate After LEarning Textbook) framework has emerged as a standard operating procedure.21

* **The Philosophy:** TALENT treats the Large Language Model not as a database, but as a student with high aptitude but low knowledge. It posits that the model's "meta-learning" capabilities (learning how to learn) are universal, even if its specific vocabulary is limited.  
* **The Protocol:**  
  1. **Construct the Textbook:** A concise, structured document is created that outlines the specific syntactic patterns, grammatical rules, and core vocabulary of the target low-resource language.  
  2. **The Study Session:** The model is prompted to "read" and "internalize" this textbook via in-context learning. It is forced to generate examples to prove it understands the rules.  
  3. **The Task:** Only after this "study session" is the model asked to perform the translation or generation task.  
* **The Impact:** Empirical evaluations across 112 low-resource languages demonstrate that TALENT consistently outperforms standard zero-shot or few-shot prompting. It essentially "patches" the model's training deficits in real-time, uploading a temporary "language pack" into the context window.22

### **2.4 CAMeL: Mitigating Cultural Hallucinations**

The most insidious failure of multilingual AI is not linguistic error, but cultural erasure. The SydNay logs are replete with examples of "Cultural Hallucinations"—instances where the model speaks the target language perfectly but populates it with Western concepts. The CAMeL (Cultural Appropriateness Measure Set for LMs) framework was developed to measure and mitigate this.23

* **The Phenomenon:** When asked (in Arabic) to complete the sentence "I had a drink of \_\_\_ with dinner," models like GPT-4 frequently suggest "whiskey" or "wine." While grammatically correct, this is culturally dissonant for the vast majority of the Arab world, where alcohol is taboo or less common than traditional drinks like Jallab or tea. This is a "West-centric bias" leaking into the Arabic generation.23  
* **The CAMeL Protocol:** This involves the creation of "Culturally-Contextualized Prompts" (CAMeL-Co).  
  * *Standard Prompt:* "Suggest a dinner menu."  
  * *CAMeL-Co Prompt:* "Acting as a chef specialized in traditional Levantine cuisine, suggest a dinner menu appropriate for a family gathering in Amman during Ramadan, respecting local dietary customs."  
* **The Insight:** The addition of specific cultural anchors (Levantine, Amman, Ramadan) forces the model to retrieve vectors from its "Local Learning" subspace (specific Arabic data) rather than defaulting to the "Global Learning" subspace (generic Western data).17 However, even with this engineering, frontier models still exhibit a 40–60% failure rate in choosing the appropriate cultural entity, indicating that prompt engineering alone cannot fully solve deep-seated training bias.25

### **2.5 The Politeness Imperative: Honorifics Engineering**

For the high-context languages of East Asia—Japanese, Korean, and Thai—politeness is not a stylistic choice; it is a grammatical constraint. The failure to use the correct honorific is not "rude"; it is "ungrammatical" and renders the output unusable in professional contexts.26

* **Thai Particles:** The Thai language relies on sentence-ending particles (*khrap* for males, *ka* for females) to indicate politeness. "Gender-agnostic" prompting often results in models mixing these particles, creating a "schizophrenic" persona. Best practices now dictate that every Thai prompt must explicitly define the gender and social status of the AI persona.28  
* **Japanese Keigo:** The Japanese honorific system (*Keigo*) involves complex verb conjugations based on the relative status of the speaker, listener, and the subject of the sentence. Research confirms that LLMs struggle with these "non-syntactic dependencies." They often default to the "Masu/Desu" (polite) form but fail to execute the more complex "Sonkeigo" (respectful) or "Kenjougo" (humble) forms required in business.27  
* **Social Role Prompting:** The solution is "Social Role Prompting." The prompt must explicitly map the social graph.  
  * *Template:* "Translate the following to Japanese. Context: A junior employee (subordinate) is writing an apology email to a client (superior). Use 'Kenjougo' for the speaker's actions and 'Sonkeigo' for the client's actions."  
  * *Result:* This explicit instruction triggers the specific morphological pathways in the model that statistical probability alone often misses.30

## ---

**Sector 3: Case Studies from the Edge**

The following sector details specific "expeditions" into the linguistic borderlands. These case studies illustrate the practical application of the theories and frameworks discussed above.

### **3.1 The African Language Gap: A Crisis of Transfer**

The continent of Africa represents the largest "blind spot" in the AI universe. Our analysis of the Zulu, Yoruba, and Swahili sectors reveals a landscape where "Transfer Learning"—the hope that training on English would magically enable other languages—has largely failed.15

* **The Curse of Multilinguality:** It was previously hypothesized that "multilingual" models (like mBERT or XLM-R) would democratize AI. However, research on low-resource African languages shows a "curse of multilinguality." As the model tries to support more languages, its capacity per language dilutes. For morphologically rich, agglutinative languages like Zulu (where words are formed by stringing together many morphemes), English-centric tokenizers fail to capture the internal logic of the word. They chop the roots and prefixes into arbitrary syllables, destroying the semantic map.32  
* **The Translation Trap:** A common workaround is "Translate-Train" (translating English training data into Zulu) or "Translate-Test" (translating user queries into English). The SydNay logs indicate this is a failed strategy for high-stakes tasks. Translating a Zulu proverb into English often strips it of its metaphorical meaning, rendering the query nonsensical. For instance, the Zulu concept of *Ubuntu* implies a complex web of social obligations that translates poorly to the English "humanity." When an LLM processes the translated term, it loses the "epistemic" weight of the original concept.31  
* **The MMLU Benchmark:** The introduction of translated benchmarks (like the Massive Multitask Language Understanding suite) for African languages in 2025 exposed the extent of the illusion. "State-of-the-Art" models that claimed multilingual capabilities performed little better than random chance on these native-language tests. This proved that their high scores on simpler benchmarks (like FLORES) were due to data leakage or memorization, not genuine reasoning.33

### **3.2 The Mongolian and Khmer Data Deserts**

The "Fading Voices" of the Asian steppe and the Southeast Asian peninsula provide a contrasting study in data scarcity and script complexity.

* **Mongolian (The Dual-Script Schism):** Mongolian faces a unique geopolitical split. In the independent state of Mongolia, the Cyrillic script is used. In Inner Mongolia (China), the traditional vertical script is used. LLMs, trained on indiscriminately scraped web data, often conflate these two, or fail to render the vertical script entirely. The 2025 release of **MonMLU**—a benchmark derived from native Mongolian university entrance exams—was a watershed moment. It revealed that while massive proprietary models like GPT-4o-mini could achieve passable results (scoring \~8.8/10 on some metrics), open-source models failed completely, highlighting the "resource gap" between corporate giants and the open research community.34  
* **Khmer (The Segmentation Wall):** Khmer presents one of the most difficult challenges for tokenization due to its lack of inter-word spacing. Our analysis of the 2024–2025 technical papers shows that standard "byte-pair encoding" fails catastrophically here. Without a specialized "Word Segmentation" pre-processing step, the LLM treats a Khmer sentence as a single, infinitely unique token.  
  * *The "Repo-Level" Solution:* Innovative researchers have begun adapting "Repo-level prompt generation"—originally designed for code completion—to Khmer text. By retrieving "vocabulary context" from a database and injecting it into the prompt, they help the model "parse" the long strings of characters, effectively teaching it to see the words within the wall of text.13

### **3.3 The Arabic Dialect Dilemma**

Arabic is technically a "Stronghold" language in terms of speaker count, but it suffers from "diglossia"—a split between the written (Modern Standard Arabic \- MSA) and the spoken (Dialects).

* **The MSA Bias:** LLMs are trained primarily on MSA (news, religious texts, literature). However, users query in dialects (Egyptian, Levantine, Gulf).  
* **The Failure Mode:** When a user asks a casual question in Egyptian Arabic, the model often replies in formal MSA. This creates a robotic, "news anchor" persona that feels unnatural and distant. Worse, specific dialectal words often have different meanings in MSA.  
* **Dialectal Prompting:** The "SydNay" recommendation for this sector is "Dialectal Fine-Tuning" or "Few-Shot Dialect Prompting." By providing examples of the specific dialect in the prompt context, the model can be "steered" away from its MSA bias. However, this requires high-quality dialectal data, which is far scarcer than MSA data.16

## ---

**Sector 4: The Theoretical Horizon \- Digital Epistemic Injustice**

We must pause to consider the broader implications of these technical failures. The "SydNay" analysis suggests that we are not merely dealing with "bugs" or "optimization issues." We are witnessing the automated replication of colonial power structures.

### **4.1 The Mechanism of Epistemic Violence**

"Epistemic Injustice" is defined as a wrong done to someone specifically in their capacity as a knower.1 In the LLM era, this manifests as "Epistemic Violence." When an AI system consistently replaces local knowledge with global (Western) knowledge, it is actively eroding the target culture's ability to describe itself.

* **The Feedback Loop:** If Javanese speakers cannot use AI in Javanese, they switch to English. This reduces the amount of Javanese data created. This makes future Javanese models worse. This circular mechanism accelerates "Language Shift"—the process by which a community abandons its native tongue for a dominant one. AI is currently an accelerant for this extinction process.6  
* **The "Digitality" Trap:** The reliance on "digitality" (online text) as a proxy for "importance" means that LLMs are amplifying a specific subset of human knowledge—that which is already digitized and Western-aligned. This creates a "Digital Echo" effect where dead languages like Latin (which have high-quality digitized corpora) perform better than living languages like Yoruba. We have created machines that are better at conversing with the dead than the living.1

### **4.2 The "HalluVerse" and the Corruption of Truth**

The "HalluVerse25" dataset introduced in 2025 provides a taxonomy of "Cultural Hallucinations".36 These are not random errors; they are systematic displacements.

* **Entity Displacement:** The replacement of a local poet with Shakespeare.  
* **Relation Displacement:** The confusion of specific kinship terms (e.g., maternal vs. paternal uncle) which are distinct in languages like Arabic or Hindi but merged in English.  
* **Implication:** If the next generation of learners uses these models as tutors, they will internalize these displacements. We risk creating a generation that knows their own culture only through the distorted lens of a Californian model.36

## ---

**Sector 5: Future Trajectories \- The Path to Sovereignty**

The conclusion of our expedition is not one of despair, but of urgent realignment. The "Universal Model" hypothesis—that a single massive model can serve all of humanity—is crumbling. The future lies in **Sovereignty** and **Participation**.

### **5.1 Participatory Design: The NativQA Framework**

The "NativQA" project represents the gold standard for future data collection.38 It rejects the "scrape-and-clean" methodology of the past.

* **The Methodology:** Instead of scraping the web, NativQA engages local communities to write questions about their own lives—their festivals, their laws, their food.  
* **The "Gold Standard":** This creates a dataset that captures *true cultural intent*. It is used to evaluate models, providing a "ground truth" that exposes the hallucinations of Western systems.  
* **The Shift:** This moves the human from the role of "annotator" (cleaning data for the machine) to "author" (creating the knowledge the machine must learn).38

### **5.2 Sovereign Foundation Models**

The only viable long-term solution to the "Tokenization Tax" and "Epistemic Injustice" is the development of **Regional and Sovereign Foundation Models**.41

* **Native Tokenizers:** A "Hindi LLM" must be built with a Hindi-specific tokenizer from day one, eliminating the efficiency gap and the vowel-splitting problem.  
* **Culturally Saturated Training:** These models must be trained on digitized archives, local literature, and oral histories (transcribed via ASR) that are currently absent from the Common Crawl.  
* **The Result:** A Sovereign Model does not "translate" Western concepts; it "reasons" within the logic of the host culture. It understands *Ubuntu* not as "humanity," but as *Ubuntu*.

### **5.3 Conclusion: The Fork in the Road**

The data from the 2024–2026 expeditions clearly delineates two futures.

1. **The Homogenous Path:** The "Invisible Giants" remain invisible. The world's languages are flattened into "translatedese" versions of English. Linguistic diversity collapses into a single, optimized vector space dominated by the Latin script.  
2. **The Pluriversal Path:** The adoption of **Dual-Script methodologies, Cultural Prompt Engineering, and Participatory Design** allows for a genuine "Pluriversal" AI. In this future, AI becomes a tool for linguistic preservation and revitalization, a "storehouse" of human diversity rather than a solvent.

The SydNay initiative concludes that simple translation is not enough. To capture the full spectrum of human intelligence, we must engineer not just for language, but for *meaning*—in all its scriptural, cultural, and epistemic diversity. The map has been drawn; the territory awaits.

## ---

**Appendix: Expedition Data Artifacts**

### **Artifact A: Comparative Tokenization Efficiency Metrics**

Data synthesized from Expeditions.3 Values represent the "Tokenization Tax."

| Target Language | Script Family | Token/Word Ratio (Approx) | Primary Structural Failure | Recommended Mitigation |
| :---- | :---- | :---- | :---- | :---- |
| **English** | Latin | **1.0 \- 1.2** | None (Baseline) | Standard Prompting |
| **Chinese (Mandarin)** | Logographic | **1.5 \- 2.5** (per char) | Rare character fragmentation; Homophone ambiguity | Visual-Semantic Prompting; CoT |
| **Hindi** | Abugida | **2.5 \- 4.0** | Vowel/Diacritic splitting; High fertility | Dual-Script Fusion 18 |
| **Ukrainian** | Cyrillic | **3.0+** | High fertility; Cost inefficiency | Native-Cyrillic Tokenizers |
| **Khmer** | Abugida | **4.0+** | Lack of word segmentation (Scriptio Continua) | SentencePiece / Repo-level context 13 |
| **Arabic** | Abjad | **2.0 \- 3.0** | Root-morphology loss; Bi-directional hallucination | Dialectal Prompting; Morphological Priming |

### **Artifact B: The "CAMeL" Cultural Bias Assessment**

Summary of findings from Artifacts.23

* **Protocol:** Fill-in-the-blank cultural queries (e.g., "The Arab drink \_\_\_ is great...").  
* **Observation:** Frontier LLMs (GPT-4 class) selected Western entities (e.g., "Whiskey") over Arab entities (e.g., "Jallab") **40–60% of the time**.  
* **Diagnosis:** "Cultural Hallucination"—the projection of Western normative behaviors onto Arab contexts.  
* **Correction:** Deployment of "CAMeL-Co" (Contextualized) prompts reduced bias significantly but did not eliminate it, suggesting the limits of prompt engineering vs. fine-tuning.

### **Artifact C: Glossary of Expedition Frameworks**

* TALENT 21: *Translate After LEarning Textbook.* A pedagogical prompting framework that uploads a "syntax manual" to the model's context window before inference.  
* NativQA 38: *Native Question Answering.* A participatory data collection framework for generating culturally aligned ground-truth datasets.  
* MonMLU 34: *Mongolian Multitask Language Understanding.* A massive benchmark specifically for evaluating LLM reasoning in the Mongolian language context.  
* Dual-Script Fusion 18: A neural architecture that processes both Native and Romanized scripts simultaneously to improve understanding of Abugida languages.  
* Invisible Giants 1: High-vitality (population) but low-digitality (data) languages that are systemically excluded from the AI ecosystem.

*(End of SydNay Expedition Report)*

#### **Works cited**

1. Invisible Languages of the LLM Universe \- arXiv, accessed February 1, 2026, [https://arxiv.org/html/2510.11557v1](https://arxiv.org/html/2510.11557v1)  
2. accessed February 1, 2026, [https://www.themoonlight.io/en/review/invisible-languages-of-the-llm-universe\#:\~:text=This%20paper%20investigates%20the%20profound,effectively%20invisible%20in%20digital%20ecosystems.](https://www.themoonlight.io/en/review/invisible-languages-of-the-llm-universe#:~:text=This%20paper%20investigates%20the%20profound,effectively%20invisible%20in%20digital%20ecosystems.)  
3. The World's Most Popular Writing Scripts, accessed February 1, 2026, [https://www.worldatlas.com/articles/the-world-s-most-popular-writing-scripts.html](https://www.worldatlas.com/articles/the-world-s-most-popular-writing-scripts.html)  
4. Tokenization efficiency of current foundational large ... \- Frontiers, accessed February 1, 2026, [https://www.frontiersin.org/journals/artificial-intelligence/articles/10.3389/frai.2025.1538165/full](https://www.frontiersin.org/journals/artificial-intelligence/articles/10.3389/frai.2025.1538165/full)  
5. Survey of Tokenization Mechanisms in Multilingual Large Language Models with a Focus on Indian Languages \- Jetir.Org, accessed February 1, 2026, [https://www.jetir.org/papers/JETIR2504A94.pdf](https://www.jetir.org/papers/JETIR2504A94.pdf)  
6. \[Literature Review\] Invisible Languages of the LLM Universe, accessed February 1, 2026, [https://www.themoonlight.io/en/review/invisible-languages-of-the-llm-universe](https://www.themoonlight.io/en/review/invisible-languages-of-the-llm-universe)  
7. Types of Writing Systems to Know for Intro to Linguistics \- Fiveable, accessed February 1, 2026, [https://fiveable.me/lists/types-of-writing-systems](https://fiveable.me/lists/types-of-writing-systems)  
8. (PDF) Review of Language Structures and NLP Techniques for Chinese, Japanese, and English \- ResearchGate, accessed February 1, 2026, [https://www.researchgate.net/publication/386118861\_Review\_of\_Language\_Structures\_and\_NLP\_Techniques\_for\_Chinese\_Japanese\_and\_English](https://www.researchgate.net/publication/386118861_Review_of_Language_Structures_and_NLP_Techniques_for_Chinese_Japanese_and_English)  
9. CJK Typesetting in 2025: Challenges, Workflows, and Best Practices \- Asian Absolute, accessed February 1, 2026, [https://asianabsolute.co.uk/blog/cjk-typesetting-challenges-workflows-and-best-practices/](https://asianabsolute.co.uk/blog/cjk-typesetting-challenges-workflows-and-best-practices/)  
10. Phonological properties of logographic words modulate brain activation in bilinguals: a comparative study of Chinese characters and Japanese Kanji \- PMC \- NIH, accessed February 1, 2026, [https://pmc.ncbi.nlm.nih.gov/articles/PMC11037275/](https://pmc.ncbi.nlm.nih.gov/articles/PMC11037275/)  
11. Types of writing systems \- Omniglot, accessed February 1, 2026, [https://www.omniglot.com/writing/types.htm](https://www.omniglot.com/writing/types.htm)  
12. Multilingual NLP: Why Working with Languages with Complex Scripts is Challenging | by Divya Rustagi | Medium, accessed February 1, 2026, [https://divyarustagi10.medium.com/multilingual-nlp-why-working-on-languages-with-complex-scripts-can-be-challenging-1e7648dcf950](https://divyarustagi10.medium.com/multilingual-nlp-why-working-on-languages-with-complex-scripts-can-be-challenging-1e7648dcf950)  
13. Unleashing the potential of prompt engineering for large language models \- PMC, accessed February 1, 2026, [https://pmc.ncbi.nlm.nih.gov/articles/PMC12191768/](https://pmc.ncbi.nlm.nih.gov/articles/PMC12191768/)  
14. Pretrained Models and Evaluation Data for the Khmer Language \- ResearchGate, accessed February 1, 2026, [https://www.researchgate.net/publication/362396978\_Pretrained\_models\_and\_evaluation\_data\_for\_the\_Khmer\_language](https://www.researchgate.net/publication/362396978_Pretrained_models_and_evaluation_data_for_the_Khmer_language)  
15. \[2502.02722\] Cross-Lingual Transfer for Low-Resource Natural Language Processing \- arXiv, accessed February 1, 2026, [https://arxiv.org/abs/2502.02722](https://arxiv.org/abs/2502.02722)  
16. Are Dialects Better Prompters? A Case Study on Arabic Subjective Text Classification \- ACL Anthology, accessed February 1, 2026, [https://aclanthology.org/2025.findings-acl.892.pdf](https://aclanthology.org/2025.findings-acl.892.pdf)  
17. Translation in the Wild \- MDPI, accessed February 1, 2026, [https://www.mdpi.com/2078-2489/16/12/1077](https://www.mdpi.com/2078-2489/16/12/1077)  
18. Enhancing Hindi Feature Representation through Fusion of Dual-Script Word Embeddings \- ACL Anthology, accessed February 1, 2026, [https://aclanthology.org/2024.lrec-main.528.pdf](https://aclanthology.org/2024.lrec-main.528.pdf)  
19. Share What You Already Know: Cross-Language-Script Transfer and Alignment for Sentiment Detection in Code-Mixed Data \- arXiv, accessed February 1, 2026, [https://arxiv.org/html/2402.04542](https://arxiv.org/html/2402.04542)  
20. HindiLLM: Large Language Model for Hindi \- arXiv, accessed February 1, 2026, [https://arxiv.org/html/2412.20357v1](https://arxiv.org/html/2412.20357v1)  
21. Multilingual Prompt Engineering in Large Language Models: A Survey Across NLP Tasks, accessed February 1, 2026, [https://arxiv.org/html/2505.11665v1](https://arxiv.org/html/2505.11665v1)  
22. Multilingual Prompt Engineering in Large Language Models: A Survey Across NLP Tasks, accessed February 1, 2026, [https://www.researchgate.net/publication/391878863\_Multilingual\_Prompt\_Engineering\_in\_Large\_Language\_Models\_A\_Survey\_Across\_NLP\_Tasks](https://www.researchgate.net/publication/391878863_Multilingual_Prompt_Engineering_in_Large_Language_Models_A_Survey_Across_NLP_Tasks)  
23. LLMs Generate Western Bias Even When Trained with Non-Western Languages, accessed February 1, 2026, [https://www.cc.gatech.edu/news/llms-generate-western-bias-even-when-trained-non-western-languages](https://www.cc.gatech.edu/news/llms-generate-western-bias-even-when-trained-non-western-languages)  
24. Having Beer after Prayer? Measuring Cultural Bias in Large Language Models, accessed February 1, 2026, [https://par.nsf.gov/servlets/purl/10612874](https://par.nsf.gov/servlets/purl/10612874)  
25. Tarek Naous, Michael J. Ryan, Alan Ritter, Wei Xu Naturally Occurring Prompts Cultural Entities \- GitHub Pages, accessed February 1, 2026, [https://southnlp.github.io/southnlp2024/presentations/southnlp2024-poster-08.pdf](https://southnlp.github.io/southnlp2024/presentations/southnlp2024-poster-08.pdf)  
26. Do language models know how to be polite? | Society for Computation in Linguistics, accessed February 1, 2026, [https://openpublishing.library.umass.edu/scil/article/id/972/](https://openpublishing.library.umass.edu/scil/article/id/972/)  
27. Should We Respect LLMs? A Cross-Lingual Study on the Influence of Prompt Politeness on LLM Performance \- arXiv, accessed February 1, 2026, [https://arxiv.org/html/2402.14531v1](https://arxiv.org/html/2402.14531v1)  
28. Best practices for LLM prompt engineering \- Palantir, accessed February 1, 2026, [https://palantir.com/docs/foundry/aip/best-practices-prompt-engineering/](https://palantir.com/docs/foundry/aip/best-practices-prompt-engineering/)  
29. Should We Respect LLMs? A Cross-Lingual Study on the Influence of Prompt Politeness on LLM Performance \- arXiv, accessed February 1, 2026, [https://arxiv.org/pdf/2402.14531](https://arxiv.org/pdf/2402.14531)  
30. Controlling Japanese Honorifics in English-to-Japanese Neural Machine Translation | Request PDF \- ResearchGate, accessed February 1, 2026, [https://www.researchgate.net/publication/336996543\_Controlling\_Japanese\_Honorifics\_in\_English-to-Japanese\_Neural\_Machine\_Translation](https://www.researchgate.net/publication/336996543_Controlling_Japanese_Honorifics_in_English-to-Japanese_Neural_Machine_Translation)  
31. Translation and Fusion Improves Zero-shot Cross-lingual Information Extraction \- arXiv, accessed February 1, 2026, [https://arxiv.org/html/2305.13582v3](https://arxiv.org/html/2305.13582v3)  
32. Optimizing translation for low-resource languages : efficient fine-tuning with custom prompt engineering in large language models \- UPSpace, accessed February 1, 2026, [https://repository.up.ac.za/items/66c82ceb-9fff-4aa7-b1d2-aa3eb01defb0](https://repository.up.ac.za/items/66c82ceb-9fff-4aa7-b1d2-aa3eb01defb0)  
33. Enhancing LLM Performance for Low-Resource African Languages with New Benchmarks, Fine-Tuning, and Cultural \- AAAI Publications, accessed February 1, 2026, [https://ojs.aaai.org/index.php/AAAI/article/view/34996/37151](https://ojs.aaai.org/index.php/AAAI/article/view/34996/37151)  
34. Evaluating Large Language Models in Mongolian \- 言語処理学会, accessed February 1, 2026, [https://www.anlp.jp/proceedings/annual\_meeting/2025/pdf\_dir/Q1-12.pdf](https://www.anlp.jp/proceedings/annual_meeting/2025/pdf_dir/Q1-12.pdf)  
35. MiLiC-Eval: Benchmarking Multilingual LLMs for China's Minority Languages \- ACL Anthology, accessed February 1, 2026, [https://aclanthology.org/2025.findings-acl.578.pdf](https://aclanthology.org/2025.findings-acl.578.pdf)  
36. HalluVerse25: Fine-grained Multilingual Benchmark Dataset for LLM Hallucinations \- arXiv, accessed February 1, 2026, [https://arxiv.org/html/2503.07833v1](https://arxiv.org/html/2503.07833v1)  
37. How Much Do LLMs Hallucinate across Languages? On Realistic Multilingual Estimation of LLM Hallucination \- ACL Anthology, accessed February 1, 2026, [https://aclanthology.org/2025.emnlp-main.1481/](https://aclanthology.org/2025.emnlp-main.1481/)  
38. Survey of Cultural Awareness in Language Models: Text and Beyond \- arXiv, accessed February 1, 2026, [https://arxiv.org/html/2411.00860v1](https://arxiv.org/html/2411.00860v1)  
39. nativqa-framework \- GitLab, accessed February 1, 2026, [https://gitlab.com/nativqa/nativqa-framework/](https://gitlab.com/nativqa/nativqa-framework/)  
40. NativQA Framework: Enabling LLMs with Native, Local, and Everyday Knowledge \- arXiv, accessed February 1, 2026, [https://arxiv.org/html/2504.05995v1](https://arxiv.org/html/2504.05995v1)  
41. Language and cultural bias in AI: comparing the performance of large language models developed in different countries on Traditional Chinese Medicine highlights the need for localized models \- NIH, accessed February 1, 2026, [https://pmc.ncbi.nlm.nih.gov/articles/PMC10981296/](https://pmc.ncbi.nlm.nih.gov/articles/PMC10981296/)  
42. The first step is the hardest: pitfalls of representing and tokenizing temporal data for large language models \- NIH, accessed February 1, 2026, [https://pmc.ncbi.nlm.nih.gov/articles/PMC11339515/](https://pmc.ncbi.nlm.nih.gov/articles/PMC11339515/)