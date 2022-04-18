pipeline{
  agent none
  stages{
    stage('Setup parameters') {
            steps {
                script {
                  properties([parameters([choice(choices: ['compile ', 'codequality', 'clean ', 'test', 'package'], name: 'stage')])])
                }  
            }
    }
    stage('Compile'){
      agent any
      steps{
        bat 'mvn compile'
      }       
    }
    stage('Code Quality'){
      agent any
      steps{
        bat 'echo Sonarqube Code Quality Check Done'
      }
    }
    stage('Clean'){
      agent any
      steps{
        echo "Clean"
        bat 'mvn clean install'
      }
    } 
    stage('Test'){
      agent any
      steps{
        echo "test"
        bat 'mvn test'
      }
    } 
    stage('Package'){
      agent any
      steps{
        echo "PACKAGE"
        bat 'mvn package'
      }
    }
  }
}
