pipeline {
    agent any
    triggers {
        pollSCM 'H/10 * * * *'
    }
    stages {
        stage('checkout') {
            steps {
                checkout([
                    $class: 'SubversionSCM', 
                    additionalCredentials: [], 
                    excludedCommitMessages: '', 
                    excludedRegions: '', 
                    excludedRevprop: '', 
                    excludedUsers: '', 
                    filterChangelog: false, 
                    ignoreDirPropChanges: false, 
                    includedRegions: '', 
                    locations: [[
                        credentialsId: 'mySvnCredentials', 
                        depthOption: 'infinity',
                        ignoreExternalsOption: true, 
                        local: '.', 
                        remote: 'http://example.com/svn/url/trunk']], 
                    workspaceUpdater: [$class: 'CheckoutUpdater']
                ])
            }
        }
    }
}
