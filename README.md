Found a EBS volume-

Volume id –
vol-0ae7904b966048f71
	IAM > created role

<img width="624" height="260" alt="image" src="https://github.com/user-attachments/assets/bc3c1ecd-0ac1-4cb4-b341-d745bdf42a26" />


Created lambda function- sud-ebs-snapshot-cleanup-30days


<img width="624" height="281" alt="image" src="https://github.com/user-attachments/assets/1a84057a-d5f6-44e4-b07a-71b2df0f2c1d" />


<img width="624" height="302" alt="image" src="https://github.com/user-attachments/assets/b0458ffb-c7a9-41c5-abaf-7ebdfc2a1423" />


Pasted code and created testing event

<img width="624" height="260" alt="image" src="https://github.com/user-attachments/assets/fc747b58-ef8c-4548-b907-5bc610ade05b" />


Changed the configuration-
Time to 1 min
Memory to 256 mb


Output logs-

Status: Succeeded
Test Event Name: testing

Response:
{
  "statusCode": 200,
  "body": {
    "message": "EBS Snapshot created successfully",
    "SnapshotId": "snap-017ac42a19dd029da",
    "VolumeId": "vol-0ae7904b966048f71",
    "State": "completed"
  }
}


<img width="624" height="291" alt="image" src="https://github.com/user-attachments/assets/54a5757e-2ac6-4bfc-9a95-0d6aff009097" />


Created and added triggers of everyday at 2am (cron job)


 Lambda Triggers page (EventBridge added)[15]
 Cron expression: 0 2 * * ? *[14]
EC2 Snapshots → Tagged snapshot created


<img width="624" height="294" alt="image" src="https://github.com/user-attachments/assets/4cc99944-4940-4947-bdcd-b9cd55b27bd5" />

The area below shows the last 4 KB of the execution log.

Function Logs:
START RequestId: bc96e1d4-d793-4677-8257-6ada3cd14eb3 Version: $LATEST
END RequestId: bc96e1d4-d793-4677-8257-6ada3cd14eb3
REPORT RequestId: bc96e1d4-d793-4677-8257-6ada3cd14eb3  Duration: 45803.11 ms   Billed Duration: 47065 ms   Memory Size: 256 MB Max Memory Used: 104 MB Init Duration: 1260.97 ms

Request ID: bc96e1d4-d793-4677-8257-6ada3cd14eb3
