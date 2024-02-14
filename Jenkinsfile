pipeline {
    agent {
        label 'master'
    }
    stages {
        stage('Build') {
            steps {
                bat 'mvn -B -DskipTests clean package'
            }
        }

        stage('Test') { 
            steps {
                bat 'mvn test' 
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml' 
                }
            }
        }
        stage('Sonar-Report') {
            steps {
                bat "mvn clean verify sonar:sonar -Dsonar.projectKey=project-test -Dsonar.projectName='project-test' -Dsonar.host.url=http://localhost:9000 -Dsonar.token=sqp_06d2dc5d5b0764ac0ec8473c72ad81ec111efd93"
            }
        }
        stage('Deploy'){
            steps{
                bat 'C:\\Users\\priya\\Jenkins_\\workspace\\Webapp-2\\target\\'
            }
        }
        
        // stage('SonarQube Analysis') {
        //     steps{
        //         bat "mvn clean verify sonar:sonar -Dsonar.projectKey=project-test -Dsonar.projectName='project-test' -Dsonar.host.url=http://localhost:9000 -Dsonar.token=sqp_06d2dc5d5b0764ac0ec8473c72ad81ec111efd93"
        //     }
        // }
    }
}
