pipeline {
    agent {
        docker {
            image 'gongpu/kpt'
            args '-v $PWD:/app -v /var/run/docker.sock:/var/run/docker.sock'
        }
    }

    stages {
        stage('Build') {
            steps {
                // This requires that docker is installed on the agent. 
                // And your user, which is usually `jenkins`, should be added to the `docker` group to access `docker.sock`.
                sh 'kpt fn run /app/resources --fn-path functions.yaml'
            }
        }
    }
}