pipeline {
    agent any

    environment {
        VENV = "/home/vikrant/automation/venv-ansible/bin"
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
                playbooks/interface_desc.yml
                '''
            }
        }
    }
}

