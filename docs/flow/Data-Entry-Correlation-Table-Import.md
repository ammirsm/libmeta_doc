---
tags: [flow, Paper]
---

# Data Entry

We will discuss flows in the dataentry page here.

In the data-entry page we have a drop down which a user select between [import from file, import from library]. 

## Import from file
We will have two choice here.

### Library
Search the title without punc, author without punc and year. It will return an object of the paper which you will have an option to select from samples and their meta_data.
After selecting from them you will have a view for changing the data and save that into Hubmeta database.

Use ```GET /paper``` to get the data of the paper and other endpoints will be use from hubmeta api.

### File
Import from file is one of the most ciritial functions in the Hubmeta.
1. User will upload file to the platform with the paper details. ```POST /paper```
2. If file extenstion is ```PDF```:
- wait for the process and task ```202 response```
- check for the task status ```GET /task/{id}```
- get the data after success process ```GET /paper/{id}```
2. Elseif the file exention is ```CSV or XLS```:
- get data immediately ```200 response```
3. Show that to the user with sample 
4. After edits beside of saving to the hubmeta request to save into libmeta. ```POST /paper/{id}```

