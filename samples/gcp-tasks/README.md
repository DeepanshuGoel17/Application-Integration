## Prerequisite
* GCS bucket - to upload files
* Pub/Sub topic - gets file details whenever we upload any file to GCS bucket
* GCS connector to fetch the file from GCS bucket
* Saleforce Connector(Optional)
* Big Query Connector(Optional)

Note: If you do want to use the GCS bucket. You can directly use the Base64 content of the file with new `DOC AI` task in application integraton. 

## Steps to run the integration sample
1. Create an intergration with the name of your choice. 
2. Download the [file](https://github.com/DeepanshuGoel17/Application-Integration/blob/c79c0e944ee57f3f55cbdd219d2f703a5dc64804/samples/gcp-tasks/documentAI-demo-v1.json) and upload the same in the integration editor page. 
3. Configure the Cloud Pub/Sub Trigger named `Document Trigger` your Pub/Sub topic which gets file details whenever we upload any file to GCS bucket.
4. Configure the next task named `Fetch from GCS`.
    - Click on the task and then click on the `CONFIGURE TASK` button.
    - Select the region where your GCS Connection is running.
    - Select the GCS connection from the list.
    - Select `Actions` for the Type.
    - Select `DownloadObject`.
    - Click Done.
5. Configure the task name `Doc AI - Process (Preview)`.
    - Add `Region`, `ProjectId` & `Processorsid`.
6. Configure the `Send Email` task. 
    - Add email address to the `To Recipient(s)` field (which will receieve email in case it is not a claim).
7. Now we are alomst complete. Please feel free to skip the next steps if you want to process a claim in different way. 
8. (Optional) Configure the `Push to Salesforce` task. 
    - Click on the task and then click on the `CONFIGURE TASK` button.
    - Select the region where your Saleforce Connection is running.
    - Select the Saleforce connection from the list.
    - Select `Entities` for the Type.
    - Select the entity where you want to push record. 
    - Select `Create` from Operation.
    - Click Done. 
9. (Optional) Configure the `Push to BQ` task. 
    - Click on the task and then click on the `CONFIGURE TASK` button.
    - Select the region where your Big Query Connection is running.
    - Select the Big Query connection from the list.
    - Select `Entities` for the Type.
    - Select the entity where you want to push record. 
    - Select `Create` from Operation.
    - Click Done.
10. Test the integration!!

See more information on the GCP tasks in Application Integration [here](). 
