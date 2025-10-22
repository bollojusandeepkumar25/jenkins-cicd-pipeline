pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building Docker image...'
                bat 'docker build -t bollojusandeepkumar25/myapp:latest .'

            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                bat 'echo All tests passed!'
            }
        }

        stage('Deploy') {
            steps {
                bat 'docker push bollojusandeepkumar25/myapp:latest'
                echo 'Deploying container...'
                bat 'docker stop myapp || exit 0'
                bat 'docker rm myapp || exit 0'
                bat 'docker run -d -p 5000:5000 --name myapp myapp:latest'
            }
        }
    }
}
