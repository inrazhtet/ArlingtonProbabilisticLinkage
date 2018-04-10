# ArlingtonProbabilisticLinkage
### Administrative datasets deduplication and linkage

*This repository is **not** for reproducibility. It is to highlight a portion of the work I have done via some code snippets. The datasets are under strict confidentiality agreement.*

#### Problem Statement

The Department of Human Services in Arlington stores client data of different services in different format and databases. With being unable to link all these different client datasets, the department is unable to answer fundamental questions like how many **unique** clients are they serving in a single day? What are the demographics of those clients?

#### Objective

Our objective is to demonstrate to the stakeholders that by using probablistic linkage we would be able to

1. Remove duplicate client information within each data system (a single data system corresponds to certain line of services).
2. Link different data system which has not shared any primary and foreign key. 

For objective 1, the internal departmental solution is using exact matching. For objective 2, we are coming up with a solution for the department.

#### Team

The lead Principal Investigator of the Team is [Aaron Schroeder](https://www.bi.vt.edu/faculty/Aaron-Schroeder). Sayali Phadke, a Ph.D. Statistics student at Penn State University and I were the two Data Science for Public Good Fellows on the team.

#### Deliverables

1. We have a symposium poster that outlined our approach with some initial results of one dataset.
2. We have an intermediate results report that details the results of all three datasets that we applied the linkage method to.
3. We have the results of a first cut of joining all three **previously unlinkable** datasets. (The results are under intermediate results report as well.) 

##### Result highlights

Out of three datasets, for the first objective we reduce the number of duplications upon their existing method by

1. 0.3% for the first dataset
2. 32% for the second dataset
3. 25.43% for the third dataset

Systemwide, we have a starting total of *147,611* clients. With our method we are able to join all three datasets and remove *4765* clients that exist across all three systems. In other words, there are approximately ~5,000 clients who use three different services from three different divisions of the department of human services in Arlington.

#### Datasets

As a proof of concept, we deploy probabilistic linkage on the following three datasets.

1. Behavioral Health for Children and Aging Population dataset
2. Economic Independence dataset
3. Community Service dataset

#### Some of my contributions to the project

