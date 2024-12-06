pipeline {
    agent{
        label 'maven'
    } 
    tools {
        maven 'apache-maven-3.9.9' 
    }
    stages {
        stage('VCS') {
            steps {
                git url: 'https://github.com/spring-projects/spring-petclinic.git', 
                    branch: 'main'
            }
        }
        stage('build') {
            steps {
                echo 'sh building code ....'
                echo 'sh static code analysis'
                echo 'sh archive the package into jfrog'
            }
        }
        stage('deploy-prod') {
            steps {
                echo 'sh deploy into production'
            }
        }
    }
}