pipeline {
      agent { label 'vm1' }
  
    stages {
      stage ('install') {
        steps {
         sh 'whoami'
         sh 'sudo apt-get install apache2 -y'
        }
      }
      stage ('start') {
        steps {
         sh 'sudo systemctl enable --now apache2'
        }
      }
      stage ('check') {
        steps {
         sh 'systemctl is-active apache2'
         sh 'curl -i http://localhost/nonexistent-page'
         sh "curl -i http://localhost"
        }
      }
      stage ('finish') {
        steps {
         echo 'Congrat!'
          sh 'curl -I http://localhost'
          sh 'sudo apt remove apache2 -y'
        }
      }
    }
}
