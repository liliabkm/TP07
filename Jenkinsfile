pipeline {
    agent any

    stages {
        stage("Test") {
            steps {
                script {

                    sh "./gradlew test"


                    archiveArtifacts artifacts: 'build/reports/tests/*'


                    cucumber(
                        buildStatus: 'UNSTABLE',
                        reportTitle: 'Rapport Cucumber',
                        fileIncludePattern: '**/*.json',
                        trendsLimit: 10,
                        classifications: [
                            [
                                'key': 'Browser',
                                'value': 'Firefox'
                            ]
                        ]
                    )
                }
            }
        }
    }


}
