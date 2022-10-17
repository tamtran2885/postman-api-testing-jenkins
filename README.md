# Postman-collection-dropbox-api-jenkins

This repo is a placeholder to maintain Dropbox API Postman Collection and Jenkins build.

## Install and set up Jenkins local server with WAR file

- Download Jenkins WAR file here (https://www.jenkins.io/download/)
- Create a folder named Jenkins in the path C:\Program Files and copy the WAR file to it
- Run the command and save the random password

```console
java -jar jenkins.war
```

- Go to (http://localhost:8080), and paste the random password
- Continue following steps to finish the process, and start Jenkins in the default Jenskin page.

## Integrate Dropbox-API project to Jenkins

### Create project and build configuration

- Create new item (New Item > Enter an item name > Choose type of project > click OK)
- In Configuration page, add build step by executing Windows batch command > Save
- Click Buil Now to build the configuration

### Export test result

- In order to access the log and download it as a txt file to your workspace from the job's URL:

```console
${BUILD_URL}/consoleText
```

Ex:

```console
http://localhost:8080/job/dropbox-api-postman/1/consoleText
```

- Hit CTRL+S to save it as a txt file

### Export Jenkins config file

- Download "jenkins-cli.jar" file (Default Jenskin page > Manage Jenkins > Jenkins CLI)
- Run command line to retrieve the config file

```console
java -jar jenkins-cli.jar -s http://JENKINS_USER:JENKINS_PASSWORD@JENKINS_IP:JENKINS_PORT get-job "JOB_NAME" > CONFIG_FILE
```

### Fix Jenkins character issues

```console
java -Dfile.encoding=UTF-8 -jar jenkins.war --httpPort=8080
```

## Install and Set up repository:

- Clone this repository
- Install the dependencies of this project with "npm install"
- Install Newman

```console
npm install -g newman
```

- Install Newman HTML Reporter to get information about the collection run in HTML format

```console
npm install -g newman-reporter-html
npm install -g newman-reporter-htmlextra
```

## Running test suite:

To run our test suite:

- Open terminal
- Navigate to the folder where the project is located.
- Run "npm run colelction"

## Get Newman HTML Reporter

```console
newman run COLLECTION_JSON_FILE -r html
newman run COLLECTION_JSON_FILE -r htmlextra
```

## Postman Collection

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/16978833-22ed760b-0b65-48ef-9a2e-3db0653a6c25?action=collection%2Ffork&collection-url=entityId%3D16978833-22ed760b-0b65-48ef-9a2e-3db0653a6c25%26entityType%3Dcollection%26workspaceId%3Dfbdea7d7-a03d-4269-8090-270c57da2e0a#?env%5BDropbox%20env%5D=W3sia2V5IjoiQXBwX2tleSIsInZhbHVlIjoidWw3dGdqYm5xNnUzcjA2IiwiZW5hYmxlZCI6dHJ1ZSwidHlwZSI6ImFueSIsInNlc3Npb25WYWx1ZSI6InVsN3RnamJucTZ1M3IwNiIsInNlc3Npb25JbmRleCI6MH0seyJrZXkiOiJBcHBfc2VjcmV0IiwidmFsdWUiOiI4dXVkczgybHRjcmlkeTkiLCJlbmFibGVkIjp0cnVlLCJ0eXBlIjoiZGVmYXVsdCIsInNlc3Npb25WYWx1ZSI6Ijh1dWRzODJsdGNyaWR5OSIsInNlc3Npb25JbmRleCI6MX0seyJrZXkiOiJBdXRoX3VybCIsInZhbHVlIjoiaHR0cHM6Ly93d3cuZHJvcGJveC5jb20vb2F1dGgyL2F1dGhvcml6ZSIsImVuYWJsZWQiOnRydWUsInR5cGUiOiJkZWZhdWx0Iiwic2Vzc2lvblZhbHVlIjoiaHR0cHM6Ly93d3cuZHJvcGJveC5jb20vb2F1dGgyL2F1dGhvcml6ZSIsInNlc3Npb25JbmRleCI6Mn0seyJrZXkiOiJBY2Nlc3NfdG9rZW5fdXJsIiwidmFsdWUiOiJodHRwczovL2FwaS5kcm9wYm94YXBpLmNvbS9vYXV0aDIvdG9rZW4iLCJlbmFibGVkIjp0cnVlLCJ0eXBlIjoiZGVmYXVsdCIsInNlc3Npb25WYWx1ZSI6Imh0dHBzOi8vYXBpLmRyb3Bib3hhcGkuY29tL29hdXRoMi90b2tlbiIsInNlc3Npb25JbmRleCI6M30seyJrZXkiOiJhY2Nlc3NfdG9rZW4iLCJ2YWx1ZSI6InNsLkJRNmJFLW1maFhiRVJjTmdTVTVuSHBWakNUelZPYUM1NkJMTUpvR3BOVFNNYTh5MVllR3JVNFBQeFBqNUZyT05vNjMyZHhHREhORUk3ZkZ2bkZhRWdWYzBwSFJJVGw4XzMxNWJRSjRncXpRc0FqTTR3QXdKVlVGZzRmRDUxd0dPWUZxUEdYOTRnX28iLCJlbmFibGVkIjp0cnVlLCJzZXNzaW9uVmFsdWUiOiJzbC5CUTZiRS1tZmhYYkVSY05nU1U1bkhwVmpDVHpWT2FDNTZCTE1Kb0dwTlRTTWE4eTFZZUdyVTRQUHhQajVGck9ObzYzMmR4R0RITkVJN2ZGdm5GYUVnVmMwcEhSSVRsOF8zMTViUUo0Z3F6UXNBak00d0F3SlZVRmc0ZkQ1MXdHT1lGcVBHWC4uLiIsInNlc3Npb25JbmRleCI6NH1d)

## Reference:

- Postman (https://www.postman.com/)
- Jenkins (https://www.jenkins.io/)
- Newman (https://www.npmjs.com/package/newman)
