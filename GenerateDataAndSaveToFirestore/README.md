## Instruction:
* Firestore > select native mode
* clone this repo in the gcloud
* gcloud config set project [PROJECT_ID] // replace it with the value that you fond using `gcloud config list project` output looks like [core] project = <project_ID>
* PROJECT_ID=$(gcloud config get-value project)
* node createTestData 1000 // this will create customers_1000.csv file containing 1000 records of test data
* node importTestData customers_1000.csv // this will store the data into firestore
* tpye in /customers to see the customer info in firestore

## IAM
Configure IAM to the second user see https://cloud.google.com/iam/docs/understanding-roles for more info
*   gcloud projects add-iam-policy-binding $PROJECT_ID \
  --member=user:[EMAIL] --role=roles/logging.viewer
* gcloud projects add-iam-policy-binding $PROJECT_ID \
  --member=user:[EMAIL] --role roles/source.writer