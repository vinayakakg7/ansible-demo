pipeline{
    agent any

    tools {
        maven 'maven'
        jdk 'Java'
    }

    environment{
        GIT_REPO = 'https://github.com/vinayakakg7/ansible-demo.git'
        GIT_BRANCH = 'main'
        DOCKER_NAMESPACE = "vinayakakg7"
    }
    stages {
        stage('Clone Git repository') {
            steps {
                git branch: GIT_BRANCH, url: GIT_REPO
            }
        }
    stage('Build and test using Maven') {
            steps {
                sh 'mvn clean install -DskipTests=true'
            }
        }
    stage('Run Ansible Playbook') {
            steps {
                sh 'ansible-playbook playbook.yml --connection=local'
			}
		}
        
     
}
}
