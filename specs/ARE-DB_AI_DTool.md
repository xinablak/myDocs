# SPECIFICATION FOR AI-ASSISTED DECISION TOOL FOR ARE DATABASE

This document is a rough sketch and prior notes to what will eventually become a full spec for an AI-assisted decision tool based on a rawings-techdata-BOQ-curated database.

For the implementation of the database and its AI components, several sub-implementations will be needed:

* AI classification system for analysing existing projects and assist in creating the main DB:
    * Basic routines for interpretation and extraction of text data from the main descriptive documents of each project.
    * In older projects, the PDF data will have to implement text recognition (OCR techniques) in order to process the documents. 
    * A parallel system consisting of a AI model that is able to analyse drawings and recognize decks, piers, abutments and eventually different types of these elements. This is not prioritary and may not be absolutely needed if the text document analysis reveals itself as sufficient for clustering (at least).

* Algorithm that analyses post-processed data from the projects (eventually AI powered) and exposes related projects and project data or that may even suggest solutions given a sufficiently adequate context input set. For a start, a simple system that enables searching by span and/or by solution type and provides similar entries in the database.

* AI analysis (probably Neural Network, recurrent or convolution or even a genetic algorithm...) that will provide maximum information about the data present in the database.

NOTES:

* The available data may not be sufficient for proper training the model, being that we need to allow for test data and cross-checking data.
* In case it reveals to be insufficient, will have to revert to manual input, which was our initial procedure. To be evaluated.
