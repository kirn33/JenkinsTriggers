pipeline{
        agent any
        stages{
                stage("Build")
                {
                        steps{
                        sh 'echo "Build completed"'
                        }
                }

        post{
        always{
            script{
                def subject = "${currentBuild.fullDisplayName} - ${currentBuild.result}"
                def body = """
                Build Name: ${env.JOB_NAME}
                Build Number: ${env.BUILD_NUMBER}
                Build Status: ${currentBuild.result}
                Build URL: ${env.BUILD_URL}
                """
                  emailext(
                    subject: Report,
                    body: body,
                    recipientProviders: [[$class: 'DevelopersRecipientProvider']],
                    to: 'kirankumarhm33@gmail.com'
                )
            }
        }
        success{
            echo 'Build succeeded!'
        }
        failure{
            echo 'Build failed!'
        }       
        }
     }
}


