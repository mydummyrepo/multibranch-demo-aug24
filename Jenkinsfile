pipeline {
    agent{
        label 'maven'
    } 
    tools {
        maven 'apache-maven-3.9.9' 
    }
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('VCS') {
            steps {
                git url: 'https://github.com/spring-projects/spring-petclinic.git', 
                    branch: 'systemtest'
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
                echo 'sh run end to end system tests'
                echo 'sh display test results'
            }
        }
        
    }
}