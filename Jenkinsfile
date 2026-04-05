pipeline {
    agent any

    environment {
        VENV = "/home/vikrant/venv-ansible/bin"
    }

    stages {

        stage('Debug') {
            steps {
                sh '''
                echo "User:"
                whoami

                echo "Workspace:"
                pwd

                ls -l
                '''
            }
        }

        stage('Run Ansible') {
            steps {
                sh '''
                $VENV/ansible --version

                $VENV/ansible-playbook \
                -i hosts \
                playbooks/site21-s.yml
                '''
            }
        }
    }
}

