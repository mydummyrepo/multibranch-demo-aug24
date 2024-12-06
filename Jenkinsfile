pipeline {
    agent any 
    tools {
        maven 'MAVEN_3.9.8' 
    }
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('VCS') {
            steps {
                git url: 'https://github.com/spring-projects/spring-petclinic.git', 
                    branch: 'perftest'
            }
        }
        stage('build') {
            steps {
                echo 'sh building code ....'
                echo 'sh static code analysis'
                echo 'sh archive the package into jfrog'
                echo 'sh quality gate'
            }
        }
        stage('deploy')
        {
            steps {
                echo 'sh using terraform create env'
                echo 'sh use kubectl to deploy'
            }
        }
        stage('test') {
            steps {
                echo 'sh run end to end performance tests'
                echo 'sh display test results'
            }
        }
        
    }
}