pipeline {
    agent {label 'test-server'}
    triggers {
        githubPush()
    }
    stages {
        stage ('Job-Build') {
            when {
                branch 'develop'
            }
            steps {
            sh "mkdir -p /home/ubuntu/jenkins-agent/Job-Build"
            dir('/home/ubuntu/jenkins-agent/Job-Build') {
                    git branch: 'develop', url: 'https://github.com/Shudhoo/capstone-project-1.git'
                    dir('capstone-project-1'){
                    sh "sudo docker build -t job1:${env.BUILD_NUMBER} ."
                    sh "sudo docker run -itd -p 82:80 --name testdevelop${env.BUILD_NUMBER} job1:${env.BUILD_NUMBER}"
                }
            }

        }
    }
        stage ('Job-Test') {
            when {
                branch 'master'
            }
            steps {
                sh "mkdir -p /home/ubuntu/jenkins-agent/Job-Test"             
                dir('/home/ubuntu/jenkins-agent/Job-Test') {
                    git branch: 'master', url: 'https://github.com/Shudhoo/capstone-project-1.git'
                    dir('capstone-project-1'){
                    sh "sudo docker build -t job2:${env.BUILD_NUMBER} ."
                    sh "sudo docker run -itd -p 81:80 --name testmaster${env.BUILD_NUMBER} job2:${env.BUILD_NUMBER}"
                    }
            }
            }
        }
}
}

