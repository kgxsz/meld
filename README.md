1) `aws cloudformation create-stack --stack-name infrastructure --template-body "file://./provisioning/infrastructure-template.json" --profile personal`
2) `ssh ec2-user@YOUR_ELASTIC_IP_ADDRESS -i ~/.ssh/main.pem`
3) install torch from: http://torch.ch/docs/getting-started.html
4) install loadcaffe from: https://github.com/szagoruyko/loadcaffe (installing LuaRocks looks difficult) 
5) `scp /path/to/source-file user@host:/path/to/destination-folder/`
6) `aws cloudformation delete-stack --stack-name infrastructure`
