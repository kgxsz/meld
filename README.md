1) `aws cloudformation create-stack --stack-name infrastructure --template-body "file://./provisioning/infrastructure-template.json" --profile meld`
2) `aws cloudformation describe-stacks --profile meld`
3) `ansible-playbook ./configuration/playbook.yml -i ./configuration/inventory --private-key="~/.ssh/main.pem"`
7) `scp -i ~/.ssh/main.pem path/to/source/file ubuntu@melder.keigo.io:/path/to/destination/directory`
4) `ssh ubuntu@melder.keigo.io -i ~/.ssh/main.pem`
8) `th neural_style.lua -style_image /tmp/klimpt.jpg -content_image /tmp/lily-cafe.jpg`
9) `scp -i ~/.ssh/main.pem ubuntu@melder.keigo.io:/home/ubuntu/neural-style/out.png .`
10) `aws cloudformation delete-stack --stack-name infrastructure --profile meld`
