pipeline{
      agent { label 'slave1' }
      stages{
      stage('check out'){
                  steps{
                  sh "rm -rf hello-world-war"
                  sh "git clone https://github.com/Kartikkar/hello-world-war.git"
                  }
                  }
      stage('build'){
      steps{
      sh "pwd"
      sh "ls"
      sh "cd hello-world-war"
      sh "docker build -t kartdock/docimage:1.0 ."
      }
      }
       stage('publish'){
                  steps{
                        sh "docker login -u kartdock -p Kar@11118"
                        sh "docker push kartdock/docimage:1.0"
                  }
            }
            stage('deploy'){
                  agent { label 'slave2' }
                  steps{
                        sh "docker login -u kartdock -p Kar@11118"
                        sh "docker pull kartdock/docimage:1.0"
                        sh "docker rm -f trail1"
                        sh "docker run -d -p 8090:8080 --name trail1 kartdock/docimage:1.0"
                  }
            }
      }
      }
