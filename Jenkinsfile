pipeline {
    agent any

    stages {
        stage("Find change sets") {
            steps {
                script {
                    // Put stuff in here
                    def build = currentBuild

                    echo "There are ${build.changeSets.size()} changeSets"
                    build.changeSets.each { cs ->
                        echo "Inspecting changeSet ${cs}"
                        echo "cs affectedFiles = ${cs.getAffectedFiles()}"

                        cs.getAffectedFiles().each {
                            echo "Affected file ${it}"
                            echo "Affected file at ${it.getPath()}"
                        }
                    }
                }
            }
        }
    }
}
