pipeline{
  agent "vm1"
    stages{
      stage ("install") {
        steps{
         sh 'sudo apt-get install apache2 -y'
        }
      }
      stage ("start") {
        steps{
         sh 'sudo systemctl enable --now apache2'
        }
      }
      stage ("check") {
        steps{
         sh 'systemctl is-active apache2'
          sh "http://localhost:8080"
        }
      }
    }
}
