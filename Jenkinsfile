pipeline {
    agent any

    stages {
        stage('SCM checkout') {
            steps {
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/rodamilans/ansible-devopscourse.git'    
            }
        }
        
        stage('Run Ansible') {
            steps {
                ansiblePlaybook credentialsId: 'ssh-key', disableHostKeyChecking: true, installation: 'Ansible', inventory: 'webserver.inv', playbook: 'installapache.yml'
            }
        }
    }
}
