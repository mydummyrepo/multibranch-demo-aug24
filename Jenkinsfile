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
                    branch: 'dev'
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
        
    }
}