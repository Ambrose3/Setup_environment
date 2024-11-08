pipeline {
    agent any

    environment {
        ANSIBLE_PLAYBOOK = 'setup_webserver.yml'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Run setup node_exporter, prometheus and grafana') {
            steps {
                script {
                    // Run the Ansible playbook
                    sh "ansible-playbook ${ANSIBLE_PLAYBOOK}"
                }
            }
        }
    }
}
