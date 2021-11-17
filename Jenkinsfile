def jenkinsfile

def overrides = [
    disableAllReports: true,
    credentialsId: 'github',
    deployTo: 'maven-central',
    openShiftBuild: false,
    scriptVersion  : 'v7',
    javaVersion: '11',
    pipelineScript: 'https://git.aurora.skead.no/scm/ao/aurora-pipeline-scripts.git',
    iqOrganizationName: "Team AOS",
    versionStrategy: [
        [branch: 'master', versionHint: '2']
    ]
]
fileLoader.withGit(overrides.pipelineScript,, overrides.scriptVersion) {
   jenkinsfile = fileLoader.load('templates/leveransepakke')
}

jenkinsfile.run(overrides.scriptVersion, overrides)
