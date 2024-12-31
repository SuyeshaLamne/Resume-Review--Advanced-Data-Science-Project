# Resume Screening Tool

## Introduction

Recruitment is a critical but time-intensive process for organizations. Manually screening resumes often takes hours or even days, and the sheer volume of applications can lead to great candidates being overlooked. To address this challenge, we developed the **Resume Screening Tool**, a project leveraging cutting-edge AI, vector databases, and an intuitive web interface to make resume screening faster, smarter, and scalable.

The project combines:
- A **Jupyter Notebook** for developing and testing the core logic.
- A **Streamlit app** to provide recruiters with an easy-to-use interface for practical application.

## Project Structure

The tool is built around two key components:
1. **Jupyter Notebook**: The development and testing hub where core logic is refined.
2. **Streamlit App**: A user-friendly web application that allows recruiters to upload resumes, enter queries, and receive detailed insights.

## Application Link
https://grp21resumellm.streamlit.app/

### Jupyter Notebook: The Development and Testing Hub

#### Key Functions:
1. **Setting Up APIs**:
   - **OpenAI API**: Used to generate embeddings and GPT-4 responses.
   - **Pinecone**: A vector database for efficient storage and querying of embeddings.

   Example:
   - A unique embedding is generated for each section of a resume and stored in Pinecone, enabling fast and accurate searches.

2. **Text Preprocessing**:
   - **PyPDF2**: Extracts text from resumes in PDF format.
   - **Cleaning and Chunking**: Tokenizes and splits the text into smaller sections (chunks) of 800 characters for efficient AI processing.

   Example:
   - Sections like "Work Experience" or "Skills" are treated as individual chunks, allowing focused AI analysis.

3. **Generating Embeddings**:
   - Text chunks are converted into embeddings using OpenAI's `text-embedding-ada-002` model. These embeddings capture the semantic meaning of the text.

   Example:
   - A chunk stating "Proficient in Python and data analysis" is represented as a unique embedding.

4. **Storing Embeddings in Pinecone**:
   - Embeddings are stored in Pinecone with metadata, enabling similarity searches based on recruiter queries.

5. **Testing Queries**:
   - Simulates recruiter queries to validate the tool's performance.

   Example Output:
   - Query: "What is the candidate’s experience with machine learning?"
   - Response: "The candidate has 2 years of experience in machine learning, including building predictive models and working with TensorFlow."

#### Why the Notebook is Critical:
- **Development Sandbox**: Enables testing and refinement of each tool component.
- **Debugging and Iteration**: Isolates issues for resolution without affecting the app.
- **Experimentation**: Facilitates optimization of parameters, AI models, and workflows.

### Streamlit App: The User Interface

#### Key Features:
1. **File Upload**:
   - Recruiters can upload resumes in PDF format. Text is extracted using PyPDF2 and displayed for verification.

2. **Text Chunking and Embedding Generation**:
   - Text is divided into smaller chunks, embeddings are generated, and the data is stored in Pinecone.

3. **Query Input**:
   - An input box allows recruiters to type specific questions (e.g., "Does the candidate know Python?").

4. **Matching Queries with Stored Data**:
   - Query embeddings are compared with stored embeddings in Pinecone to find relevant sections of resumes.

5. **AI-Generated Response**:
   - GPT-4 generates detailed, human-like responses to recruiter queries.

   Example:
   - Query: "What is this candidate’s experience with Python?"
   - Response: "The candidate has 3 years of experience with Python, including developing backend systems and working on data analysis projects."

6. **Visual Feedback**:
   - Displays matched text and AI-generated explanations, enabling quick decision-making.

### Integration of Notebook and Streamlit App
- The **Jupyter Notebook** handles technical groundwork (e.g., embedding generation, Pinecone integration, query handling).
- The **Streamlit app** provides a user-facing layer for accessible functionality.

## Benefits

1. **Efficiency**:
   - Processes resumes in seconds, saving hours of manual effort.
2. **Scalability**:
   - Handles large volumes of resumes seamlessly.
3. **Accuracy**:
   - Identifies relevant skills and experiences with precision.
4. **User-Friendly Interface**:
   - Intuitive design ensures quick adoption by recruiters.

## Challenges and Lessons Learned

1. **Handling Token Limits**:
   - Resolved by breaking resumes into smaller chunks to maintain efficiency without losing context.
2. **Integration Across Platforms**:
   - Synchronized multiple technologies (OpenAI, Pinecone, Streamlit) for seamless operation.
3. **Data Privacy**:
   - Implemented safeguards to ensure compliance with data privacy standards.

## Future Improvements

1. **Advanced Filters**:
   - Add filters for certifications, years of experience, and technical skills.
2. **Automated Interview Scheduling**:
   - Integrate calendar features for scheduling interviews directly through the app.
3. **Handling Non-Standard Resumes**:
   - Enhance capabilities to process resumes with tables, graphics, or unique layouts.

## Conclusion

The Resume Screening Tool bridges the gap between AI innovation and recruitment challenges. Combining OpenAI for natural language processing, Pinecone for data management, and Streamlit for an intuitive interface, this tool saves time, improves accuracy, and simplifies the hiring process.

### Author
- Suyesha

### License
This project is licensed under the MIT License. See the LICENSE file for details.

### Questions
For questions or feedback, feel free to open an issue or contact us via GitHub.
