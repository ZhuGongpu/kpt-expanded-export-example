pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // This requires that docker is installed on the agent.                
                sh 'docker run -v $PWD:/app -v /var/run/docker.sock:/var/run/docker.sock gongpu/kpt:latest fn run /app/resources --fn-path functions.yaml'
            }
        }
    }
}