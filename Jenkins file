pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                sshPublisher(publishers: [sshPublisherDesc(configName: 'phpserver', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '''cd var/www/html
                sudo mv index.php /var/www/html
                cd /var/www/html
                sudo mv index.php index.html''', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '/var/www/html/', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '**/*.php')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
            }
        }
    }
}
