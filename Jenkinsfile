pipeline{
    agent { label 'ws' }
    environment { 
        SSH_CREDENTIALS = credentials('SSH_CRED') 
    }
    stages{
        stage('Performing Ansible Dry RUn'){
            steps{
                sh "ansible-playbook robot-dryrun.yaml -e COMPONENT=mongodb -e ansible_user=${SSH_CREDENTIAL_USER} -e ansible_password=${SSH_CREDENTIAL_USER} -e ENV=qa"
            }
        }
    }
}
