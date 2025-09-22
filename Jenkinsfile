pipeline {
    agent any
    stages {
        stage('Clone Git Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/gyanpunj/jenkins-ansible.git'
            }
        }

        stage('Run Ansible Playbook') {
            steps {
                ansiblePlaybook credentialsId: 'ansible-ssh', disableHostKeyChecking: true, installation: 'ansible2', inventory: 'inventory.ini', playbook: 'install_apache.yml', vaultTmpPath: ''
            }
        }
    }
}

