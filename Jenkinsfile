pipeline {
    agent any 
    def changeLogSets
    def entries
    def entry
    def files
    def file
    stages {
        stage('Build') { 
            steps {
               changeLogSets = currentBuild.changeSets
                    for (int i = 0; i < changeLogSets.size(); i++) {
                        entries = changeLogSets[i].items
                        for (int j = 0; j < entries.length; j++) {
                        entry = entries[j]
                        echo "${entry.commitId} by ${entry.author} on ${new Date(entry.timestamp)}: ${entry.msg}"
                        files = new ArrayList(entry.affectedFiles)
                        for (int k = 0; k < files.size(); k++) {
                        file = files[k]
                        echo "  ${file.editType.name} ${file.path}"
        }
    }
}
            }
        }
      stage('Success') { 
            steps {
                echo 'Success'
            }
      }
        
       
    }
}
