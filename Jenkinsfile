pipeline{
    agent{
        label "master"
    }
    stages {
        stage("Clean Up"){
            steps {
                deleteDir()
            }
        }
        stage("Clone Repo") {
            steps {
                sh 'git clone https://github.com/TestGitUser0/ansible.git'
            }
        }
        stage("Install Nginx with Ansible") {
            steps {
                dir('ansible') {
                    sh 'ls -la'
                    sh 'ls -la playbook'
                    sh 'ansible-playbook -i inventory/hosts playbook/nginx.yml'
                }
            }
        }
    }
}
