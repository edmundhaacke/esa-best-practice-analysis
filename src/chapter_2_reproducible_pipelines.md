# Reproducible Analytical Pipelines

Analytical tasks can vary in their nature, from quick turn-around to long-term pieces. Short-term projects may develop into a longer-term commission within the team; or be revisited or refreshed in the future. There is also an organizational need to avoid duplicative work, thus work may be passed on to others. With this in mind, guidance on developing reproducible analytical pipelines should be followed where possible, proportionate and reasonable.'

## What it is

A Reproducible Analytical Pipeline (RAP) is an automated statistical and analytical process (Government Analysis Function, 2022). The benefits are:

1. Improved quality of analysis - easier to quality assure than manual processes
2. Increased trust in analysis by producers, managers and users
3. More efficient process
4. Improved business continuity and knowledge management

## RAP attributes

1. Minimization of manual steps, and where absolutely required, these should be documented
2. Built in open source software, e.g. R or Python
3. Peer reviewed to ensure process is reproducible, and meets the necessary requirements below
4. Audit trail using version control i.e. through Git
5. Open to anyone, with limitations, for example restricted or confidential data
6. Follow good practice for quality assurance
7. Contains well commented code, embedded documenetation, and version controlled within the product

Pipelines can further be developed through:

- functions and code modularity
- unit testing of functions
- error handling for functions
- documentation for functions
- packaging
- code style
- input data validation
- logging of data and the analysis
- continuous integration and dependency management

## References

- Government Analysis Function, (2022). Reproducible Analytical Pipelines. Available via <https://analysisfunction.civilservice.gov.uk/support/reproducible-analytical-pipelines>