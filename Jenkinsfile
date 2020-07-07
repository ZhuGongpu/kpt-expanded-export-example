pipeline {
    agent {
        docker { image 'gongpu/kpt' }
    }

    stages {
        stage('Build') {
            steps {
                sh 'kpt fn run .'
            }
        }        
    }
}