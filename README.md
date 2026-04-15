📘 AUTOMATED PAPER EVALUATION SYSTEM FOR SUBJECTIVE HANDWRITTEN ANSWERS
Now this is your complete system explanation, stitched properly — including BERT/SBERT + AI pipeline + system flow.
No fluff. This is how your project actually works end-to-end.

🧠 1. Core Objective
The system is built to:

Automatically evaluate subjective (theory) answers — especially handwritten ones — by comparing them with a model answer and generating marks + feedback.


⚙️ 2. High-Level Architecture
User Input (PDF/Image/Text)        ↓PDF Processing (Poppler)        ↓OCR (Text Extraction)        ↓Text Preprocessing        ↓Semantic Evaluation (SBERT / BERT)        ↓(Optional AI Feedback - Gemini)        ↓Score + Feedback        ↓Database Storage (MongoDB)        ↓Frontend Display (React)

🧩 3. Technologies Used & Their Roles
Frontend — React


UI rendering


File upload


Display results


👉 Works using components + state updates

Backend — Flask


API handling


Processing pipeline execution


AI integration


👉 Acts as the central controller

Database — MongoDB


Stores:


Students


Teachers


Evaluation results




👉 Flexible JSON storage

PDF Processing — Poppler + pdf2image


Converts PDF → images for OCR



OCR Engine — Gemini Vision API


Extracts handwritten text


👉 Critical for handwritten answer support

AI Models Used
1. Semantic Evaluation — Sentence-BERT
2. Contextual Understanding — BERT
3. Optional Feedback — Google Gemini

🧠 4. Core Working (Step-by-Step)

Step 1: Input Handling
User uploads:


Model Answer


Student Answer (PDF/Image/Text)



Step 2: PDF & Image Processing
PDF → Images → OCR → Extracted Text


Poppler converts PDF


OCR extracts text



Step 3: Text Preprocessing


Clean text


Remove noise


Normalize formatting



🧠 5. Semantic Evaluation Using BERT & SBERT
This is the core intelligence (your actual AI logic)

🔹 What is BERT?
BERT:


Understands words using bidirectional context


Uses transformer encoder + self-attention


How it works:
Sentence → Tokens → Embeddings → Transformer → Contextual Meaning
Example:


“bank” → understands meaning based on context



🔹 Problem with BERT


Not efficient for sentence comparison


Requires pair-wise processing



🔹 Solution: Sentence-BERT
SBERT modifies BERT to:

Convert full sentences into fixed-size vectors


🔄 SBERT Working
Model Answer → Vector AStudent Answer → Vector B
Then:
Similarity = cosine(Vector A, Vector B)

📏 Cosine Similarity Logic


1 → same meaning


0 → unrelated


Example:
0.85 → 8.5/100.60 → 6/10

🧠 What It Actually Evaluates


Concept similarity


Meaning overlap


Semantic closeness


👉 Not exact word matching

⚠️ Limitation
SBERT:


Doesn’t check structure


Doesn’t detect missing key points explicitly


Only measures similarity



🧠 6. (Optional) AI Feedback Generation
Using:
👉 Google Gemini

How it works:
Prompt sent:
Compare model answer and student answer.Give:- Marks- Strengths- Weaknesses- Suggestions

Output:
{  "marks": 7,  "feedback": "Good but missing key points",  "strengths": [...],  "weaknesses": [...]}

Important Insight


SBERT → scoring


Gemini → explanation



💾 7. Storage
MongoDB stores:


Evaluation results


Metadata (student, teacher, date)



🖥️ 8. Output Display
React shows:


Marks


Feedback


Downloadable reports



🔄 9. Complete System Flow
User Upload   ↓PDF → Image → OCR   ↓Text Extraction   ↓SBERT Embedding   ↓Cosine Similarity   ↓Score Generation   ↓(Optional Gemini Feedback)   ↓Store in MongoDB   ↓Display via React

⚠️ 10. Realistic Limitations
1. OCR Dependency


Bad handwriting → wrong evaluation


2. SBERT Limitation


Only similarity, not full grading logic


3. AI Variability (Gemini)


Non-deterministic responses


4. No Rubric-Based Evaluation


No strict marking scheme



🚀 11. Possible Improvements


Point-wise evaluation (key concepts)


Hybrid scoring (SBERT + rules)


Fine-tuned models


Batch evaluation


Diagram understanding



🧩 Final Understanding
👉 Your system is fundamentally:
Input → Text → Embedding → Similarity → Score
Enhanced with:
AI → Human-like feedback

🔥 One-Line Truth

This is not a rule-based grading system — it is a semantic similarity + AI-assisted evaluation system.
