# Meld

##### A repository for provisioning and configuring a GPU heavy instance for doing image neural styling.

## Provisioning 
- Provision the infrastructure with:
  ```
  aws cloudformation create-stack --stack-name infrastructure --template-body "file://./provisioning/infrastructure-template.json" --profile meld
   ```
- Then verify that all is in place:
   ```
   aws cloudformation describe-stacks --profile meld
   ```
   
## Configuration
- Configure the EC2 instance with: 
   ```
   ansible-playbook ./configuration/playbook.yml -i ./configuration/inventory --private-key="~/.ssh/main.pem"
   ```
   
## Image styling
- Copy the image to be styled to the instance:
   ```
   scp -i ~/.ssh/main.pem /path/to/content.jpg ubuntu@melder.keigo.io:/tmp
   ```
- Then connect to the instance:
  ```
  ssh ubuntu@melder.keigo.io -i ~/.ssh/main.pem
  ```
- Once connected, kick off the styling:
   ```
   th neural_style.lua -style_image styles/style.jpg -content_image /tmp/content.jpg
   ```
- When it's complete, copy the output back to your local machine:
  ```
  scp -i ~/.ssh/main.pem ubuntu@melder.keigo.io:/home/ubuntu/neural-style/out.png ~/Desktop
  ```
  
## Cleaning up
- To tear down the infrastructure: 
  ```
  aws cloudformation delete-stack --stack-name infrastructure --profile meld
  ```
