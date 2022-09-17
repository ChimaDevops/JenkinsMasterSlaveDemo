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
            sh "lscpu"
            sh "lsblk"
          }
        }
        stage('Tunde'){
          steps{
            echo 'Tunde action'
            sh "lscpu"
            sh "free -g"
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
        sh "lscpu"
        sh "whoami"
      }
    }
    stage('parallel-job2'){
      parallel{
        stage('Chima'){
          steps{
            echo 'Chima action'
            sh "lscpu"
            sh "netstat"
          }
        }
        stage('Gregory'){
          steps{
            echo 'Gregory action'
            sh "lscpu"
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
        sh "lscpu"
        sh "pwd"
      }
    }
    stage('parallel-job3'){
      parallel{
        stage('Lawal'){
          steps{
            echo 'Lawal action'
            sh "lscpu"
            sh "free -m"
          }
        }
        stage('Valentine'){
          steps{
            echo 'Valentine action'
            sh "lscpu"
            sh "free"
          }
        }
      }
    }
  }
}
