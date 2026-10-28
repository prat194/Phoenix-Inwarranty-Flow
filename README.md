# Postman collection Automation integrating with GitHub actions #
This repository is a demonstration for POC for integrating Postman tests with GitHub actions. The tests are written in postman and executed on VM's with the help on newman and newman-reporter-htmlextra. Github actions will trigger the project execution on every push to main branch. You can also execute the project manually using workflow_dispatch.The project runs on scheduled time with the help of CRON job.

The Html report is archived and kept in artifacts section for the team to download it. Along with that they can view the report directly from the Github page : https://manasa994.github.io/Phoenix_Inwarranty_Flow.The latest report is mailed to the team members using Gmail SMTP.

## Testing Coverage ##
1.Happy flow testing
2.Negative Testing and edge case testing 
3.Token testing 
4.Schema validation
5.Data driven testing with CSV
6.Secrets management with GitHub Secrets

## Tech Stack ##
1.Postman 
2.Node JS 
3.newman 
4.newman-reporter-htmlextra 
5.github actions 
6.github pages 
7.Gmail SMTP 
8.CSV for data driven testing 
9.AWS EC2 instance for selfhosted github runs

## Github Pages ##
You can directly view the latest postman tests report at the GitHub page link - https://prat194.github.io/Phoenix-Inwarranty-Flow/

## Project Structure ##
Postman Inwarranty Flow
├─ Inwarranty-flow Collection.postman_collection # Collection
├─ QA.postman_environment.json # Environment file
└─ testdata.csv # Testdata file

## HTML Report ##
The Report will be created in newman folder

Postman Report

How can you run the project
You can run the project on our local system for that :

Clone the project on Local system : https://github.com/prat194/Phoenix-Inwarranty-Flow.git
Install Node js and npm : https://nodejs.org/en
Install newman using npm install -g newman
Install newman-reporter-htmlextra using npm install -g newman-reporter-htmlextra
Run the newman command :
newman run 'Inwarranty-flow Collection.postman_collection' \
         -e QA.postman_environment.json \
         -d testdata.csv \
         -r cli,htmlextra \
         --reporter-htmlextra-export ./newman/index.html
