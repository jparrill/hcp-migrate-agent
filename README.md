# BM HCP Migration Script (Alpha)

## Filling the variables:

This is an explanation of what is every env var used in the script:

- `WORKSPACE_DIR`: Directory to work with backups and files for each HostedCluster.
- `HC_CLUSTER_NS`: Namespace where the HostedCluster object is present.
- `HC_CLUSTER_NAME`: HostedCluster name.
- `AGENT_NAMESPACE`: Namespace where the agent should be registered against.
- `MGMT_KUBECONFIG`: Place where the Management cluster Kubeconfig (source) file is present. (For Backup and Restoration)
- `MGMT2_KUBECONFIG`: Place where the Management cluster 2 Kubeconfig (destination) file is present. (Only for restoration)
- `BUCKET_NAME`: This is the AWS bucket name. (Sample: cs-hcp-dr)
- `AWS_ACCESS_KEY_ID`: AWS Access Key ID (Usually located under ~/.aws/credentials)
- `AWS_SECRET_ACCESS_KEY`: AWS Secret Access Key (Usually located under ~/.aws/credentials)
- `MGMT2_REGION`: AWS Region where the s3 bucket with etcd backup resisdes eg ap-southeast-1

## Required CLI
- base64
- curl
- jq
- oc
- openssl
- yq
- sed
- kubectl
- aws

## Usage

- Fulfill the env file first and then source it.
- Create Backup

```bash
migrate-hcp-agent.sh -b
```

- Restore Backup

```bash
migrate-hcp-agent.sh -r
```
