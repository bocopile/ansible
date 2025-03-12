# ansible
해당 프로젝트는 Ansible를 사용 목적으로 생성된 프로젝트 입니다.


## Azure 사용시
1. Azure cli 설치
   - brew update && brew install azure-cl
2. Ansible 설치
   - brew install ansible
3. Ansible azure.azcollection module 설치
   - ansible-galaxy collection install azure.azcollection --force  
4. Azure login 진행
   - az login
5. Azure Service Principal 생성
 - az ad sp create-for-rbac --name <your-service-principal-name> --role Contributor --scopes /subscriptions/<your-subscription-id>/resourceGroups/<your-resource-group>
6. Ansible Config 설정
   [defaults]
   inventory = ./hosts
   interpreter_python = auto

    [azure]
    client_id = <your-client-id>
    secret = <your-client-secret>
    tenant = <your-tenant-id>
    subscription_id = <your-subscription-id>
