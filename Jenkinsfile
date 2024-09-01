pipeline {
    agent any

   stages {
        stage('Test') {
            steps {
                sh 'cd SampleWebApp && mvn test'
            }
        }
        stage('Build') {
            steps {
                sh 'cd SampleWebApp && mvn clean package'
            }
        }
        
        stage('Deploy to Tomcat') {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'tomcat2', path: '', url: 'http://18.209.171.58:8080/')], contextPath: 'myapp', war: '**/*.war'            }
        }
    }
}
