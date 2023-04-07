pipeline {
    agent { label 'ws' }
    environment { 
        SSH_CREDENTIALS = credentials('SSH_CRED') 
    }    
    stages {
        
        stage('Performing Lint Check') {
        when { branch pattern: "feature-.*", comparator: "REGEXP"}
            steps {
                sh "env"
                sh "echo This step should run against non-main branches only"
                sh "echo PERFORMING LINT CHECKSS"
            }
        }

        stage('Performing Ansible Dry Run') {     // This stage I want to run it against a PR Only
        when { branch pattern: "PR-.*", comparator: "REGEXP"}
            steps {
                sh "env"
                sh "ansible-playbook robot-dryrun.yaml -e COMPONENT=mongodb -e ansible_user=${SSH_CREDENTIALS_USR} -e ansible_password=${SSH_CREDENTIALS_PSW} -e ENV=qa"
            }
        }

        stage('Promotion To Prod Branch') {       // This stage will run only against the main branch
            when { branch 'main' }
            steps {
                sh "env"
                sh "echo main - PROMOTING To PROD"
            }
        }
    }
}