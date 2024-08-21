pipeline{
        agent any
        stages{
                stage("Build")
                {
                        steps{
                        sh 'echo "Build completed"'
                        }

                 }

                post {
                    success {
                        emailext(
                            subject: "SUCCESS: ${env.JOB_NAME} [${env.BUILD_NUMBER}]",
                            body: "Good news! The build ${env.JOB_NAME} [${env.BUILD_NUMBER}] succeeded.",
                            to: 'kirankumarhm33@gmail.com'
                                )
                            }
                    failure {
                        emailext(
                            subject: "FAILURE: ${env.JOB_NAME} [${env.BUILD_NUMBER}]",
                            body: "Unfortunately, the build ${env.JOB_NAME} [${env.BUILD_NUMBER}] failed. Please check the Jenkins console for details.",
                            to: 'kirankumarhm33@gmail.com'
                                )
                            }
                }

        }
}


