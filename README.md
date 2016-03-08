1) `aws cloudformation create-stack --stack-name infrastructure --template-body "file://./provisioning/infrastructure-template.json" --profile personal`
2) `aws cloudformation describe-stacks` to see status and outputs
3) `ansible-playbook ./configuration/playbook.yml -u ubuntu -i ./configuration/inventory --private-key="~/.ssh/main.pem"`
7) `scp -i ~/.ssh/main.pem path/to/source/file ubuntu@host:/path/to/destination/directory`
4) `ssh ubuntu@your_elastic_ip_address -i ~/.ssh/main.pem`
8) `th neural_style.lua -style_image /tmp/klimpt.jpg -content_image /tmp/lily-cafe.jpg`
9) `scp -i ~/.ssh/main.pem ubuntu@52.87.18.37:/home/ubuntu/neural-style/out.png .`
9) `aws cloudformation delete-stack --stack-name infrastructure`
