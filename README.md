## Rice Academic Advisor (RAG Chatbot)

A chatbot that answers questions about Rice courses, majors, minors and 
distribution requirements. It retrieves relevant passages from the official Rice catalog
and course listings, then generates an answer that cites its sources. When the sources don't
support an answer, it says "I don't know".

# Recommended data sources:
- courses.rice.edu: Course descriptions, credit hours, prerequisites, distribution groups, terms offered, instructors, etc.
- ga.rice.edu: Major, minor and degree requirements, distribution rules, etc.
- (If possible) retrieve syllabus, course/instructor reviews.

# Evaluation 
- Retrieval: recall@k, MRR
- Generation: faithfulness, answer correctness

# Hybrid Retrieval 
- Sparse (BM25): catch exact matches such as course codes (e.g. COMP 140) and specific terms
- Dense (embeddings): catch semantically similar expressions like "Intro CS class"
- RRF (Reciprocal Rank Fusion): merge the two
- (Optional) reranking.

# Possible additions:
- Metadata filters: restrict retrieval by department, catalog year, course level, etc.
- Deterministic engines: major requirements and prerequisite graph checks.
