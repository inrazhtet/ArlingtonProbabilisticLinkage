# ArlingtonProbabilisticLinkage
### Administrative datasets deduplication and linkage

*This repository is **not** for reproducibility. It is to highlight a portion of the work I have done via some code snippets. The datasets are under strict confidentiality agreement.*

#### Problem Statement

The Department of Human Services in Arlington stores client data of different services in different format and databases. As the department is unable to link all these different client datasets, it is unable to answer fundamental questions like how many **unique** clients are they serving in a single day? What are the demographics of those clients?

#### Objective

Our objective is to demonstrate to the stakeholders that by using probablistic linkage we would be able to

1. Remove duplicate client information within each data system (a single data system corresponds to a certain line of services).
2. Link different data system which has not shared any primary and foreign key. 

For objective 1, the internal departmental solution is using exact matching. We are hoping to deploy probabilistic linkage to deliver better results. For objective 2, we are coming up with a solution for the department.

#### Team

The lead Principal Investigator of the Team is [Aaron Schroeder](https://www.bi.vt.edu/faculty/Aaron-Schroeder). Sayali Phadke, a Ph.D. Statistics student at Penn State University and I were the two Data Science for Public Good Fellows on the team.

#### Deliverables

1. In this repository, we have a symposium poster that outlined our approach with some initial results of one dataset.
2. In this repository, we have an intermediate results report that details the results of all three datasets that we applied the linkage method to. This report was presented to the stakeholders of the department along with the poster at the final presentation day.
3. Additionally, we also have the results of a first cut of joining all three **previously unlinkable** datasets. (The results are under intermediate results report as well.) 

#### Result highlights

Out of three datasets, for the first objective we reduced the number of duplications over their existing method by

1. 0.3% for the first dataset
2. 32% for the second dataset
3. 25.43% for the third dataset

Systemwide, we have a starting total of *147,611* clients. With our method we are able to join all three datasets and remove *4765* clients that exist across all three systems. In other words, there are approximately *~5,000* clients who use three different services from three different divisions of the department of Human Services in Arlington.

#### Datasets

As a proof of concept, we deployed probabilistic linkage on the following three datasets.

1. Behavioral Health for Children and Aging Population dataset (Web Vision)
2. Economic Independence dataset (ETO)
3. Community Service dataset (Anasazi)

#### My contributions to the project

Sayali and I paircoded the initial deduplication for the ETO dataset. We based it off on our P.I's preliminary code. Furthermore, this code scheme is replicated across the other two datasets by each of us and finally, we paircoded again on linking all three datasets. 
Below, I have outlined a few of the **key** steps to achieve a deduplicated dataset. A code snippet of the first ETO file is included in this repository.

*Please refer to the poster for a quick overview of Fellegi-Sunter probabilistic linkage method*

1. Use compare.dedup from the RecordLinkage library to create pairs of rows for probabilistic comparison.
2. Set m-probabilities. u-probabilities are set automatically using frequency.
3. Apply the weights to the pairs.
4. Check the weight distribution via plots to determine cut off point for definite match, review and mismatch.
5. For the pairs under review, deduplicate those that share the same system ID and those that do not share the same system ID.
6. From 5, merge any overlap between the two outputs and combine them to get a single **deduplicated** data set.
7. The original dataset is antijoined with those rows that go through deduplication to the get rows that are **not** involved at all in deduplication.
8. Combine output from **6** and **7** to get the complete dedudplicated dataset.

#### Code snippet
1. **dedup_eto.R** : This code file goes through the 8 key steps above and more.









