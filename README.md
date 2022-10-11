# Postman-collection-dropbox-api-jenkins

This repo is a placeholder to maintain Dropbox API Postman Collection and Jenkins build.

## Keys used in APIs:

- Client ID: the client identifier issued to the client during the Application registration process.
- Client Secret: the client secret issued to the client during the Application registration process.
- Auth URL: the end point for authorization server. This is used to get the authorization code.
- Access Token URL: the end point for authorization server. This is used to exchange the authorization code for an access token.

## Postman Collection

#### 1. Fork the collection

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/16978833-22ed760b-0b65-48ef-9a2e-3db0653a6c25?action=collection%2Ffork&collection-url=entityId%3D16978833-22ed760b-0b65-48ef-9a2e-3db0653a6c25%26entityType%3Dcollection%26workspaceId%3Dfbdea7d7-a03d-4269-8090-270c57da2e0a#?env%5BDropbox%20env%5D=W3sia2V5IjoiQXBwX2tleSIsInZhbHVlIjoidWw3dGdqYm5xNnUzcjA2IiwiZW5hYmxlZCI6dHJ1ZSwidHlwZSI6ImFueSIsInNlc3Npb25WYWx1ZSI6InVsN3RnamJucTZ1M3IwNiIsInNlc3Npb25JbmRleCI6MH0seyJrZXkiOiJBcHBfc2VjcmV0IiwidmFsdWUiOiI4dXVkczgybHRjcmlkeTkiLCJlbmFibGVkIjp0cnVlLCJ0eXBlIjoiZGVmYXVsdCIsInNlc3Npb25WYWx1ZSI6Ijh1dWRzODJsdGNyaWR5OSIsInNlc3Npb25JbmRleCI6MX0seyJrZXkiOiJBdXRoX3VybCIsInZhbHVlIjoiaHR0cHM6Ly93d3cuZHJvcGJveC5jb20vb2F1dGgyL2F1dGhvcml6ZSIsImVuYWJsZWQiOnRydWUsInR5cGUiOiJkZWZhdWx0Iiwic2Vzc2lvblZhbHVlIjoiaHR0cHM6Ly93d3cuZHJvcGJveC5jb20vb2F1dGgyL2F1dGhvcml6ZSIsInNlc3Npb25JbmRleCI6Mn0seyJrZXkiOiJBY2Nlc3NfdG9rZW5fdXJsIiwidmFsdWUiOiJodHRwczovL2FwaS5kcm9wYm94YXBpLmNvbS9vYXV0aDIvdG9rZW4iLCJlbmFibGVkIjp0cnVlLCJ0eXBlIjoiZGVmYXVsdCIsInNlc3Npb25WYWx1ZSI6Imh0dHBzOi8vYXBpLmRyb3Bib3hhcGkuY29tL29hdXRoMi90b2tlbiIsInNlc3Npb25JbmRleCI6M30seyJrZXkiOiJhY2Nlc3NfdG9rZW4iLCJ2YWx1ZSI6InNsLkJRNmJFLW1maFhiRVJjTmdTVTVuSHBWakNUelZPYUM1NkJMTUpvR3BOVFNNYTh5MVllR3JVNFBQeFBqNUZyT05vNjMyZHhHREhORUk3ZkZ2bkZhRWdWYzBwSFJJVGw4XzMxNWJRSjRncXpRc0FqTTR3QXdKVlVGZzRmRDUxd0dPWUZxUEdYOTRnX28iLCJlbmFibGVkIjp0cnVlLCJzZXNzaW9uVmFsdWUiOiJzbC5CUTZiRS1tZmhYYkVSY05nU1U1bkhwVmpDVHpWT2FDNTZCTE1Kb0dwTlRTTWE4eTFZZUdyVTRQUHhQajVGck9ObzYzMmR4R0RITkVJN2ZGdm5GYUVnVmMwcEhSSVRsOF8zMTViUUo0Z3F6UXNBak00d0F3SlZVRmc0ZkQ1MXdHT1lGcVBHWC4uLiIsInNlc3Npb25JbmRleCI6NH1d)

#### 2. The collection uses environment variables. So choose the dropdown to select "Dropbox env" variables.

#### 3. Generate Access Token using OAuth 2

- After sharing the collection, the access token will not persist in the new workspace. Therefore, it is necessary to regenerate a new access token. In the Authorization tab of the collection, select Get New Access Token.

- By default, requests inside the collection will inherit auth from the parent, and they will use the same auth specified at the collection level.

#### 4. Modify upload file request

Because the file path would be invalid after sharing requests between different machines, Collection Runner would not support uploading file. Before running collection, it is essential to manually select file to be uploaded in the request body. In this collection, it is supposed that the request will upload a text file (.txt), so it is important to manually select a text file to run successfully the collection later.

## Export Jenkins config file

```console
java -jar jenkins-cli.jar -s http://JENKINS_USER:JENKINS_PASSWORD@JENKINS_IP:JENKINS_PORT get-job "JOB_NAME" > CONFIG_FILE
```

## Reference:

- Postman (https://www.postman.com/)
- Jenkins (https://www.jenkins.io/)
- Newman (https://www.npmjs.com/package/newman)
