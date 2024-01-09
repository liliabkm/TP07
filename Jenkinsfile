pipeline {
    agent any

    stages {
        stage("Test") {
            steps {


                    sh "./gradlew test"


                    junit 'build/test-results/test/*.xml'


                    cucumber(
                        buildStatus: 'UNSTABLE',
                        reportTitle: 'Rapport Cucumber',
                        fileIncludePattern: '**/*.json'
                    )
                }




                 stage("Notiy") {
                            steps {

                notifyEvents message: 'Hello <b>world</b>', token: 'fmn--poqmgyccjg3mftvnnntl9xgxpur'

                                }


        }
    }


}
