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

        }
    }


}
