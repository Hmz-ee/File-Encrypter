pipeline {
    agent {label 'agent'}

    stages {

        stage('Build') {
            steps {
                sh '''
                    echo "Building Java project..."
                    cd "Password Protection"
                    mkdir -p build
                    javac -d build src/*.java
                    echo "Build successful"
                '''
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                    echo "Packaging..."
                    cd "Password Protection"
                    jar cf FileEncrypter.jar -C build .
                    echo "Deployment successful"
                '''
            }
        }

    }
}
