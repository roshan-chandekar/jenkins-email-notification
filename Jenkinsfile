node (label: 'slave_adtech') {
    try {
        stage('Test') {
            sh 'echo "Fail!"; exit 1'
        }
        echo 'This will run only if successful'
    } catch (e) {
        echo 'This will run only if failed'
        emailext attachLog: true, subject: "Jenkins Build Status is ${currentBuild.currentResult} | ${currentBuild.durationString} | #${BUILD_ID}", body: "Hello there, \n\nStatus of this job is ${currentBuild.currentResult}\n Job Name is ${env.JOB_NAME}\n\n More info at: ${env.BUILD_URL}\n\n\n Regards,\n DevOps" , to: 'roshan.chandekar@nykaa.com'


        // Since we're catching the exception in order to report on it,
        // we need to re-throw it, to ensure that the build is marked as failed
        throw e
    } finally {
        def currentResult = currentBuild.currentResult ?: 'SUCCESS'
        if (currentResult == 'SUCCESS') {
            echo 'This will run only if the run was marked as unstable'
            emailext attachLog: true, subject: "Jenkins Build Status is ${currentBuild.currentResult} | ${currentBuild.durationString} | #${BUILD_ID}", body: "Hello there, \n\nStatus of this job is ${currentBuild.currentResult}\n Job Name is ${env.JOB_NAME}\n\n More info at: ${env.BUILD_URL}\n\n\n Regards,\n DevOps" , to: 'roshan.chandekar@nykaa.com'

        }

        //echo 'This will always run'
    }
}



node (label: 'slave_adtech') {
    try {
        stage('Test') {
            sh 'echo "Fail!"'
        }
        echo 'This will run only if successful'
        emailext attachLog: true, subject: "Jenkins Build Status is ${currentBuild.currentResult} | ${currentBuild.durationString} | #${BUILD_ID}", body: "Hello there, \n\nStatus of this job is ${currentBuild.currentResult}\n Job Name is ${env.JOB_NAME}\n\n More info at: ${env.BUILD_URL}\n\n\n Regards,\n DevOps" , to: 'roshan.chandekar@nykaa.com'


    } catch (e) {
        echo 'This will run only if failed'
        emailext attachLog: true, subject: "Jenkins Build Status is ${currentBuild.currentResult} | ${currentBuild.durationString} | #${BUILD_ID}", body: "Hello there, \n\nStatus of this job is ${currentBuild.currentResult}\n Job Name is ${env.JOB_NAME}\n\n More info at: ${env.BUILD_URL}\n\n\n Regards,\n DevOps" , to: 'roshan.chandekar@nykaa.com'


        // Since we're catching the exception in order to report on it,
        // we need to re-throw it, to ensure that the build is marked as failed
        throw e
    } finally {
        def currentResult = currentBuild.result ?: 'SUCCESS'
        if (currentResult == 'UNSTABLE') {
            echo 'This will run only if the run was marked as unstable'
            emailext attachLog: true, subject: "Jenkins Build Status is ${currentBuild.currentResult} | ${currentBuild.durationString} | #${BUILD_ID}", body: "Hello there, \n\nStatus of this job is ${currentBuild.currentResult}\n Job Name is ${env.JOB_NAME}\n\n More info at: ${env.BUILD_URL}\n\n\n Regards,\n DevOps" , to: 'roshan.chandekar@nykaa.com'

        }

        def previousResult = currentBuild.getPreviousBuild()?.result
        if (previousResult != null && previousResult != currentResult) {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
            emailext attachLog: true, subject: "Jenkins Build Status is ${currentBuild.currentResult} | ${currentBuild.durationString} | #${BUILD_ID}", body: "Hello there, \n\nStatus of this job is ${currentBuild.currentResult}\n Job Name is ${env.JOB_NAME}\n\n More info at: ${env.BUILD_URL}\n\n\n Regards,\n DevOps" , to: 'roshan.chandekar@nykaa.com'

        }

        echo 'This will always run'
    }
}


pipeline {  
     agent any  
     stages {  
         stage('Email Notification') {  
             steps {  
                 sh 'echo "Email Sending!!"'  
             }  
         }  
     }
      post {  
         always {  
             echo 'This will always run'  
         }  
         success {  
             echo 'This will run only if successful' 
             emailext attachLog: true, subject: "Jenkins Build Status is ${currentBuild.currentResult} #${BUILD_ID}", body: "Hello there, \n\nStatus of this job is ${currentBuild.currentResult}\n Job Name is ${env.JOB_NAME}\n\n More info at: ${env.BUILD_URL}\n\n\n Regards,\n DevOps" , to: 'roshan.chandekar@nykaa.com'

         }  
         failure {  
            echo 'This will run only if failure'
            emailext attachLog: true, subject: "Jenkins Build Status is ${currentBuild.currentResult} #${BUILD_ID}", body: "Hello there, \n\nStatus of this job is ${currentBuild.currentResult}\n Job Name is ${env.JOB_NAME}\n\n More info at: ${env.BUILD_URL}\n\n\n Regards,\n DevOps" , to: 'roshan.chandekar@nykaa.com'

         }  
         unstable {  
             echo 'This will run only if the run was marked as unstable'
             emailext attachLog: true, subject: "Jenkins Build Status is ${currentBuild.currentResult} #${BUILD_ID}", body: "Hello there, \n\nStatus of this job is ${currentBuild.currentResult}\n Job Name is ${env.JOB_NAME}\n\n More info at: ${env.BUILD_URL}\n\n\n Regards,\n DevOps" , to: 'roshan.chandekar@nykaa.com'


         }  
         changed {  
             echo 'This will run only if the state of the Pipeline has changed'  
             echo 'For example, if the Pipeline was previously failing but is now successful'
             emailext attachLog: true, subject: "Jenkins Build Status is ${currentBuild.currentResult} #${BUILD_ID}", body: "Hello there, \n\nStatus of this job is ${currentBuild.currentResult}\n Job Name is ${env.JOB_NAME}\n\n More info at: ${env.BUILD_URL}\n\n\n Regards,\n DevOps" , to: 'roshan.chandekar@nykaa.com'

         }  
     }  

 }


node (label: 'slave_adtech') {
    try {
        stage('Test') {
            sh 'echo "Fail!"; exit 1'
        }
        echo 'This will run only if successful'
        emailext attachLog: true, subject: "Jenkins Build Status is ${currentBuild.currentResult} | ${currentBuild.durationString} | #${BUILD_ID}", body: "Hello there, \n\nStatus of this job is ${currentBuild.currentResult}\n Job Name is ${env.JOB_NAME}\n\n More info at: ${env.BUILD_URL}\n\n\n Regards,\n DevOps" , to: 'roshan.chandekar@nykaa.com'


    } catch (e) {
        echo 'This will run only if failed'
        emailext attachLog: true, subject: "Jenkins Build Status is ${currentBuild.currentResult} | ${currentBuild.durationString} | #${BUILD_ID}", body: "Hello there, \n\nStatus of this job is ${currentBuild.currentResult}\n Job Name is ${env.JOB_NAME}\n\n More info at: ${env.BUILD_URL}\n\n\n Regards,\n DevOps" , to: 'roshan.chandekar@nykaa.com'


        // Since we're catching the exception in order to report on it,
        // we need to re-throw it, to ensure that the build is marked as failed
        throw e
        emailext attachLog: true, subject: "Jenkins Build Status is ${currentBuild.currentResult} | ${currentBuild.durationString} | #${BUILD_ID}", body: "Hello there, \n\nStatus of this job is ${currentBuild.currentResult}\n Job Name is ${env.JOB_NAME}\n\n More info at: ${env.BUILD_URL}\n\n\n Regards,\n DevOps" , to: 'roshan.chandekar@nykaa.com'
    } finally {
        def currentResult = currentBuild.currentResult ?: 'SUCCESS'
        if (currentResult == 'UNSTABLE') {
            echo 'This will run only if the run was marked as unstable'
            emailext attachLog: true, subject: "Jenkins Build Status is ${currentBuild.currentResult} | ${currentBuild.durationString} | #${BUILD_ID}", body: "Hello there, \n\nStatus of this job is ${currentBuild.currentResult}\n Job Name is ${env.JOB_NAME}\n\n More info at: ${env.BUILD_URL}\n\n\n Regards,\n DevOps" , to: 'roshan.chandekar@nykaa.com'

        }

        def previousResult = currentBuild.getPreviousBuild()?.result
        if (previousResult != null && previousResult != currentResult) {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
            emailext attachLog: true, subject: "Jenkins Build Status is ${currentBuild.currentResult} | ${currentBuild.durationString} | #${BUILD_ID}", body: "Hello there, \n\nStatus of this job is ${currentBuild.currentResult}\n Job Name is ${env.JOB_NAME}\n\n More info at: ${env.BUILD_URL}\n\n\n Regards,\n DevOps" , to: 'roshan.chandekar@nykaa.com'

        }

        echo 'This will always run'
    }
}


@Library('standardECSLib@slave_adtech')_

pythonBuildECS(git_url: 'git@github.com:Nykaa/adtech-adserver-backend-service.git', repo_name: 'nka-preprod-mumbai-adserver-backend-repo', jenkins_ssh_key: 'true', task_name: 'preprod-cd-adserver-backend-service-uwsgi-task', ecs_service_name: 'preprod-cd-adserver-backend-service-uwsgi-svc', cluster_name: 'nka-preprod-python-mumbai', build: 'python', recipients: 'kirti.nehara@nykaa.com')

pipeline {  
     agent any  
     stages {  
         stage('Email notification') {  
             steps {  
                 sh 'echo "Fail!"'  
             }  
         }  
     }
      post {  
         always {  
             echo 'This will always run'  
         }  
         success {  
             echo 'This will run only if successful' 
             emailext attachLog: true, subject: "Jenkins Build Status is ${currentBuild.currentResult} #${BUILD_ID}", body: "Hello there, \n\nStatus of this job is ${currentBuild.currentResult}\n Job Name is ${env.JOB_NAME}\n\n More info at: ${env.BUILD_URL}\n\n\n Regards,\n DevOps" , to: 'roshan.chandekar@nykaa.com'

         }  
         failure {  
            echo 'This will run only if failure'
            emailext attachLog: true, subject: "Jenkins Build Status is ${currentBuild.currentResult} #${BUILD_ID}", body: "Hello there, \n\nStatus of this job is ${currentBuild.currentResult}\n Job Name is ${env.JOB_NAME}\n\n More info at: ${env.BUILD_URL}\n\n\n Regards,\n DevOps" , to: 'roshan.chandekar@nykaa.com'

         }  
         unstable {  
             echo 'This will run only if the run was marked as unstable'
             emailext attachLog: true, subject: "Jenkins Build Status is ${currentBuild.currentResult} #${BUILD_ID}", body: "Hello there, \n\nStatus of this job is ${currentBuild.currentResult}\n Job Name is ${env.JOB_NAME}\n\n More info at: ${env.BUILD_URL}\n\n\n Regards,\n DevOps" , to: 'roshan.chandekar@nykaa.com'


         }  
         changed {  
             echo 'This will run only if the state of the Pipeline has changed'  
             echo 'For example, if the Pipeline was previously failing but is now successful'
             emailext attachLog: true, subject: "Jenkins Build Status is ${currentBuild.currentResult} #${BUILD_ID}", body: "Hello there, \n\nStatus of this job is ${currentBuild.currentResult}\n Job Name is ${env.JOB_NAME}\n\n More info at: ${env.BUILD_URL}\n\n\n Regards,\n DevOps" , to: 'roshan.chandekar@nykaa.com'

         }  
     }  

 }


node (label: 'slave_adtech') {
        stage('Email Notification'){
        try {
        echo 'This will run only if successful'
        emailext attachLog: true, subject: "Jenkins Build Status is Success | ${currentBuild.durationString} | #${BUILD_ID}", body: "Hello there, \n\nStatus of this job is Success\n Job Name is ${env.JOB_NAME}\n\n More info at: ${env.BUILD_URL}\n\n\n Regards,\n DevOps" , to: 'nykaa-display-network@nykaa.com'

    } catch (e) {
        echo 'This will run only if failed'
        emailext attachLog: true, subject: "Jenkins Build Status is Failed | ${currentBuild.durationString} | #${BUILD_ID}", body: "Hello there, \n\nStatus of this job is Failed\n Job Name is ${env.JOB_NAME}\n\n More info at: ${env.BUILD_URL}\n\n\n Regards,\n DevOps" , to: 'nykaa-display-network@nykaa.com'
        throw e
       } finally {
        //echo 'This will always run'
      }
    }
}
