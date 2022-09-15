pipeline{
  agent {
    label {
      label 'slave1'
    }
  }
  stages{
    stage('version-control'){
      steps{
        checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'githubid', url: 'https://github.com/ChimaDevops/JenkinsMasterSlaveDemo.git']]])
      }
    }
    stage('parallel-job'){
      parallel{
        stage('Max'){
          steps{
            echo 'action'
          }
        }
        stage('Tunde'){
          steps{
            echo 'action'
          }
        }
      }
    }
    stage('Chrstiana'){
      agent {
        label {
          label 'slave2'
        }
      }
      steps{
        sh 'cat /etc/passwd'
      }
    }
    stage('Chima'){
      steps{
        echo 'action'
      }
    }
    stage('Chizoba'){
      agent {
        label {
          label 'slave3'
        }
      }
      steps{
        sh 'cat /etc/passwd'
      }
    }
    stage('Gregory'){
      steps{
        echo 'action'
      }
    }
  }
}
