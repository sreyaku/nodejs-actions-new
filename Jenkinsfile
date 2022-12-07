@Library('jenkins-shared-library-groovy-practice') _
pipeline {
    agent any
stages{
        stage('SonarQube Scan'){
            steps {
                script{
                    scan()
                }
               
            }
        }
            stage('node_build') {
                steps {
                    script{
                       nodedeploy()
                
                }
            }
        }
                stage ("Deploy to Staging"){
                    steps {
                        script{
                            deploy()
                       
                }
            }
        }
    stage ("Upload to S3"){
        steps {
            script{
                upload()
            }
        }
    }
    }
}









// pipeline{
//    agent any
//     stages{
//         stage('gitclone'){
//             agent any
//             steps{
//                 git credentialsId: 'bc010765-2802-482d-8502-5f629f70228a', url: 'https://github.com/sreyaku/NodeApplication.git'
//             }
//         }

//         stage('Dockerizing '){
//             steps{
//                 bat '''
//                 docker container stop yourcontainer
//             docker container rm yourcontainer
//             docker image build -t testimage:1.0 .
//              docker run -d -p 80:3000 --name yourcontainer testimage:1.0
//             '''
//         }
//         }
//          }
//     }
