pipeline{
    agent { label 'ws' }
    environment { 
        SSH_CREDENTIALS = credentials('SSH_CRED') 
    }
    stages{
        stage('Performing Ansible Dry RUn'){
            steps{
                sh "ansible-playbook robot-dryrun.yaml -e COMPONENT=mongodb -e ansible_user=${SSH_CREDENTIALS_USR} -e ansible_password=${SSH_CREDENTIALS_PSW} -e ENV=qa"
            }
        }
    }
}
