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
          }
        }
        stage('Tunde'){
          steps{
            echo 'Tunde action'
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
      }
    }
    stage('parallel-job2'){
      parallel{
        stage('Chima'){
          steps{
            echo 'Chima action'
          }
        }
        stage('Gregory'){
          steps{
            echo 'Gregory action'
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
      }
    }
    stage('parallel-job3'){
      parallel{
        stage('Lawal'){
          steps{
            echo 'Lawal action'
          }
        }
        stage('Valentine'){
          steps{
            echo 'Valentine action'
          }
        }
      }
    }
  }
}
