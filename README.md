# Digital Therapeutics (DTx) for Online Gambling Addiction Prevention

### 📖 Publication Acknowledgment
This repository contains the core codebase for the research paper: 
**"Digital Therapeutics (DTx) and site analysis using generative artificial intelligence to prevent recurrence of online gambling addiction"** 
*   **Published in:** Journal of the Korea Institute of Information and Communication Engineering (Vol. 23, No. 1).
*   **Authors:** Seoyeon Han, Sanghyun Yoo, Hayoung Oh.

---

## 📌 Project Overview
Online gambling addiction possesses high relapse rates due to easy accessibility and anonymity. Traditional blocking-oriented policies are often ineffective. This project proposes an active, personalized **Digital Therapeutics (DTx) system** that detects gambling sites in real-time and intervenes by generating customized warning messages and visual stimuli to suppress addictive behaviors.

As the **Lead Author**, I designed the end-to-end AI pipeline, focusing on balancing real-time inference speed with high classification accuracy, and architecting a personalized Generative AI intervention system.

## 🛠️ Architecture & Core Files

The project is structured into four main codes using python, representing the complete machine learning pipeline:

### 1. `Gambling_Classification.ipynb` (Dual-Classification Pipeline)
*   Implemented a dual-classification structure to accurately identify gambling sites.
*   The model first categorizes URLs into harmful vs. normal webpages, and subsequently classifies harmful pages into online casinos vs. other illegal websites.

### 2. `Gambling_FineTuning.ipynb` (Model Optimization via LoRA)
*   To enable real-time detection without latency, I applied **Parameter-Efficient Fine-Tuning (PEFT)**.
*   Specifically utilized **LoRA (Low-Rank Adaptation)** applied twice on a DistilBERT architecture. This approach expanded the parameters for better accuracy without degrading inference speed.

### 3. `Gambling_InferenceTime_check.ipynb` (Performance Evaluation)
*   Conducted rigorous testing to ensure real-time applicability.
*   **Result:** The LoRA-optimized DistilBERT model achieved a high F1-score with an average inference time of **199.1ms**, a 28.3% reduction in latency compared to baseline hybrid models.

### 4. `Gambling_Image_Generation.ipynb` (GenAI Intervention Pipeline)
*   Developed a 3-step prompt chain using **Langflow and OpenAI's GPT-4o**.
*   **Step 1 & 2:** Analyzed user vulnerability using the Gambling Pathways Questionnaire (GPQ) and matched it with cognitive behavioral therapy (CBT) strategies.
*   **Step 3:** Generated highly personalized warning messages in real-time.
*   Integrated **DALL-E 3** via ChatCompletion API to translate these texts into immediate, high-impact visual warnings, which proved highly effective in qualitative interviews with recovering patients.

## 💡 Key Takeaways
This project bridges Information Science and AI by combining meticulous psychological metadata (GPQ) with advanced ML optimization (LoRA). It demonstrates that AI can be leveraged not just for analytics, but as a proactive, empathetic tool for mental healthcare.
