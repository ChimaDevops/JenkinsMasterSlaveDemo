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
    stage('parallel-job1'){
      parallel{
        stage('Max'){
          steps{
            echo 'max action'
            sh "pwd"
            sh "date"
          }
        }
        stage('Tunde'){
          steps{
            echo 'Tunde action'
            sh "pwd"
            sh "date"
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
        echo 'Christiana action'
        sh "pwd"
        sh "date"
      }
    }
    stage('parallel-job2'){
      parallel{
        stage('Chima'){
          steps{
            echo 'Chima action'
            sh "pwd"
            sh "date"
          }
        }
        stage('Gregory'){
          steps{
            echo 'Gregory action'
            sh "pwd"
            sh "date"
          }
        }
      }
    }
    stage('Chizoba'){
      agent {
        label {
          label 'slave3'
        }
      }
      steps{
        echo 'Chizoba action'
        sh "pwd"
        sh "date"
      }
    }
    stage('parallel-job3'){
      parallel{
        stage('Lawal'){
          steps{
            echo 'Lawal action'
            sh "pwd"
            sh "date"
          }
        }
        stage('Valentine'){
          steps{
            echo 'Valentine action'
            sh "pwd"
            sh "date"
          }
        }
      }
    }
  }
}
