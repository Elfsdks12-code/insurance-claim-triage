# Insurance Claim Triage System

# 1. Overview
This project is a prototype of an AI-powered insurance claim triage system for property damage. Users can submit a description of the incident, upload photos, and optionally provide supporting PDF documents, such as inspection reports or repair estimates.

The system checks the submitted information and uses AI to support the initial assessment of the claim. It also uses information from historical claims to help with the assessment. The goal is to make the first stage of claim processing more structured and efficient.


# 2. Architecture
The project consists of several components:

 - Frontend: A web interface for submitting claim information and viewing results.

 - Backend: A Python API that receives submissions and coordinates the processing steps.

 - AI processing: A language model is used to validate submissions and support claim assessment.

 - Historical claim retrieval: Qdrant is used to search for relevant information from historical claims.

 - Supporting tools: Additional tools and sample data support the assessment process.

Separating these components makes the project easier to understand, maintain, and extend.


# 3. Setup
To run the project locally:

 - Copy .env.example to .env.

 - Configure the required environment variables and service credentials.

 - Start the services using the provided Docker Compose configuration and Makefile.

 - Open the frontend at http://localhost:3001 when using the configured local ports.

The required services and credentials must be configured before the full application can be tested.

# 4. Design Considerations and Trade-offs
The project separates the frontend, backend, AI processing, and historical claim retrieval into different components. This makes it easier to maintain individual parts and identify problems.

Using historical claim data can provide useful context for a new submission. However, similar past claims do not necessarily have the same circumstances or outcome.

AI can help organize information and support an initial assessment, but its results should not be treated as a final insurance decision. Validation and safety checks are therefore important parts of the workflow.


# 5. Limitations
The complete end-to-end workflow still needs to be tested. Further work could include improving error handling, adding automated tests, and evaluating the quality of the assessment results against the provided evaluation data.

The system is intended as a prototype and should not be used to make real insurance decisions without further testing and appropriate human review.
