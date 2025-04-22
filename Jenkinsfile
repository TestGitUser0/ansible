pipeline{
    agent{
        label "linux"
    }
    stages {
        stage("Clean Up"){
            steps {
                deleteDir()
            }
        }
        stage("Clone Repo"){
            steps {
                sh 'git clone https://github.com/TestGitUser0/ansible.git'
                sh 'cd ansible'
            }
        }
        stage("Build"){
            steps {
                dir('ansible') {
                    sh 'ansible-playbook -i inventory/hosts playbooks/nginx.yml'
                }
            }
        }
    }
}
