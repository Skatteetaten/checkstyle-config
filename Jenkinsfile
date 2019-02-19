#!/usr/bin/env groovy
def config = [
        disableAllReports: true,
        credentialsId: 'github',
        deployTo: 'maven-central',
        openShiftBuild: false,
        scriptVersion : 'v6',
        javaVersion : '11',
        pipelineScript : 'https://git.aurora.skead.no/scm/ao/aurora-pipeline-scripts.git',
        versionStrategy : [
                [branch: 'master', versionHint: '2']
        ]
]
fileLoader.withGit(config.pipelineScript, config.scriptVersion) {
   jenkinsfile = fileLoader.load('templates/leveransepakke')
}

jenkinsfile.run(config.scriptVersion, config)
