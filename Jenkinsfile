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
    stage('Parallel-job2'){
      agent {
        label {
          label 'slave2'
        }
      }
      parallel{
        stage('Christiana'){
          steps{
            echo 'Christiana action'
          }
        }
        stage('Chima'){
          steps{
            echo 'Chima action'
          }
        }
      }
    }
    stage('Parallel-job3'){
      agent {
        label {
          label 'slave3'
        }
      }
      parallel{
        stage('Gregory'){
          steps{
            echo 'Gregory action'
          }
        }
        stage('Lawal'){
          steps{
            echo 'Lawal action'
          }
        }
      }
    }
  }
}
