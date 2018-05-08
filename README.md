# tf_module_glcoud_bucket

Terraform module for building out storage bucket on Google Cloud Services

It builds a storage bucket to hold Terraform state

## Use

Call it as a module from another Terraform repository.

```sh
module "bucket" {
  source = "tf_module_gcloud_buket"_

  bucket_name = "Your bucket name"
}
```

## Testing

To build, validate and then destroy run these commands below:

```sh
bundle exec kitchen converge
bundle exec kitchen verify
bundle exec kitchen destroy
```

### Prerequisites

- Ruby 2.2 or greater
- Terraform 0.10 or greater
- gcloud command line utility (https://cloud.google.com/sdk/)
- Google Cloud Project with a service account
- Download service account credentials to: `credentials.json`
- Create an environment file: `.env`, add this content:

```sh
export GOOGLE_APPLICATION_CREDENTIALS="credentials.json"
export GCLOUD_PROJECT="<project-id>
export GCLOUD_REGION="us-west1"
```
