def appName = helloWorld
def imageBuildConfig = appName
def deploymentConfig = appName

pipeline {
  agent {
    label 'maven'
  }
  stages {
    stage('Run unit tests') {
      steps {
        echo "Run unit tests"
        sh 'mvn test'
      }
//      post {
//        always {
//          junit 'target/surefire-reports/*.xml'
//        }
//      }
    }

    stage('Build') {
      steps {
        echo "Build artifact"
        sh   'mvn package'

        echo "Trigger image build"
 //       script {
//          openshift.withCluster() {
//            openshift.selector("bc", imageBuildConfig).startBuild("--from-file=target/ROOT.war", "--wait")
//          }
//         }
        }
//      post {
//        success {
//          archiveArtifacts artifacts: 'target/**.war', fingerprint: true
//        }
//      }
    }

//    stage('Deploy') {
//      steps {
//        script {
//          openshift.withCluster() {
//            openshift.selector("dc", deploymentConfig).rollout()
//          }
//        }
//     }
//    }
//  }
}