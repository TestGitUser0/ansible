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
        stages {
        stage("Clone Repo") {
            steps {
                sh 'git clone https://github.com/TestGitUser0/ansible.git'
            }
        }

        stage("Install Nginx with Ansible") {
            steps {
                dir('ansible') {
                    sh 'ansible-playbook -i inventory/hosts playbook/nginx.yml'
                }
            }
        }
    }
    }
}
