Every iam profile can only have 2 access keys maximum.

Every access key is made from:
- access key
- secret access key

----------
This can be used to access profile by aws cli. For accessing this, we should run:\
`aws configure --profile nameofaprofile`\
After that we will be typing:
First - access key\
Second - Secret access key\
Third - Default region\
Fourth - Output format

-----
For checking anything (example with s3):\
`aws s3 ls --profile (nameofaprofile)`

This will show us a s3 storages on specific iam account, after configuration of access keys.