pipeline{
    agent { label 'ws' }
    environment { 
        SSH_CREDENTIALS = credentials('SSH_CRED') 
    }
    stages{
        stage('Performing Lint Check'){ 
            steps{
                sh "env"
                sh "echo PERFORMING LINT CHECKS"
            }

        stage('Performing Ansible Dry Run'){    // This stage I want to run it against a PR Only
            steps{
                sh "env"
                sh "ansible-playbook robot-dryrun.yml -e COMPONENT=mongodb -e ansible_user=${SSH_CREDENTIALS_USR} -e ansible_password=${SSH_CREDENTIALS_PSW} -e ENV=qa"
            }
        }
    }
}
