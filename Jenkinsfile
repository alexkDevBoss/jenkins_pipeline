pipeline {
    agent any
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
		checkout([$class: 'GitSCM', branches: [[name: '*/main']], userRemoteConfigs: [[url: 'https://github.com/alexkDevBoss/git_container.git']]])
            }
        }
        stage('Goodbye'){
            steps {
                echo 'Goodbye'
		echo 'Another commit'
                mail bcc: '', body: 'Im inside my step again', cc: '', from: '', replyTo: '', subject: 'Step message', to: 'devboss7878@gmail.com'
            }
        }

    }
    post{
            success{
                mail bcc: '', body: 'This time everything is good.', cc: '', from: '', replyTo: '', subject: 'Successful build', to: 'devboss7878@gmail.com'
            }
            failure{
                mail bcc: '', body: 'This time everything is bad.', cc: '', from: '', replyTo: '', subject: 'Failed build', to: 'devboss7878@gmail.com'
            }
    }
}
