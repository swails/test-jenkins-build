pipeline {
    agent any

    stages {
        stage("Find change sets") {
            steps {
                script {
                    // Put stuff in here
                    def build = currentBuild
                    analyzeBuild(build)
                    analyzeBuild(build.previousBuild)
                }
            }
        }
    }
}

def analyzeBuild(def build) {
    echo "There are ${build.changeSets.size()} changeSets in build ${build.number}"
    build.changeSets.each { cs ->
        echo "Inspecting changeSet ${cs}"
        echo "cs affectedFiles = ${cs.getAffectedFiles()}"

        cs.getAffectedFiles().each {
            echo "Affected file ${it}"
            echo "Affected file at ${it.getPath()}"
        }
    }
}
