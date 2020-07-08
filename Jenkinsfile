pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // This requires that docker is installed on the agent. 
                // And your user, which is usually `jenkins`, should be added to the `docker` group to access `docker.sock`.
                sh '''
                    docker run \
                    -v $PWD:/app \
                    -v /var/run/docker.sock:/var/run/docker.sock \
                    gongpu/kpt:latest \
                    fn run \
                    /app/resources \
                    --fn-path /app/functions.yaml
                '''
            }
        }
    }
}
