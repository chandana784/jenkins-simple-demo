pipeline {
    agent any
    
    stages {
        stage('Clone') {
            steps {
                git url: 'https://github.com/chandana784/jenkins-simple-demo.git',
                    branch: 'main'
            }
        }
        
        stage('Run Script in Docker') {
            steps {
                sh '''
                    docker run --rm \
                      -v $(pwd):/workspace \
                      -w /workspace \
                      ubuntu:22.04 \
                      bash -c "chmod +x script.sh && ./script.sh"
                '''
            }
        }
    }
}
