---
tags: [flow, Project]
---

# Import Articles

In this flow we will use the import articles.

The user will upload RIS file to here and we will search each paper in the table and if its related to paper add project_id to its project.

1. Upload file of the papers into there. ```POST /project```
(Open Modal)

2. Get the task id. ```response 200```

3. When the process finished. ```GET /task/{id}```
(Waiting for completed task)

4. Get the related data paper. ```GET /project/{id}```
(Table with sample selection and othr details of the paper and relate that to paper)
