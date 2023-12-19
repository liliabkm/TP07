pipeline {
    agent any

    stages {
        stage("Test") {
            steps {


                    sh "./gradlew test"


                    archiveArtifacts: 'build/test-results/*.xml'


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
