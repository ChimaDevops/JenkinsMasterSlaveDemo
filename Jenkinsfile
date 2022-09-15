pipeline{
  agent {
    label {
      label 'slave1'
    }
  }
  stages{
    stage('version-control'){
      steps{
        checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'github-id', url: 'https://github.com/ChimaDevops/JenkinsMasterSlaveDemo.git']]])
      }
    }
    stage('parallel-job-A'){
      parallel{
        stage('sub-job1'){
          steps{
            echo 'action'
          }
        }
        stage('sub-job2'){
          steps{
            echo 'action'
          }
        }
      }
    }
    stage('parallel-job-B'){
      parallel{
        agent {
        label {
          label 'slave2'
        }
      }
        stage('sub-job3'){
          steps{
            echo 'action1'
          }
        }
        stage('sub-job4'){
          steps{
            echo 'action2'
          }
        }
      }
    }
    stage('parallel-job-C'){
      parallel{
        agent {
        label {
          label 'slave3'
        }
      }
        stage('sub-job5'){
          steps{
            echo 'action'
          }
        }
        stage('sub-job6'){
          steps{
            echo 'action'
          }
        }
      }
    }
  }
}
