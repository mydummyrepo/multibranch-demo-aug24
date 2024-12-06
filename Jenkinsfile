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