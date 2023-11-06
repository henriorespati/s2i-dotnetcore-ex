#!groovy
// def DEV_PROJECTNAME = "demo-dev"
// def UAT_PROJECTNAME = "demo-uat"
// def BUILDCONFIGNAME="sampledotnet"
// def IMAGE_NAME="sampledotnet:latest"
// def UATIMAGENAME = "sampledotnet:UATReady-1.0.0"

podTemplate {
    node(POD_LABEL) {
        container('dotnet') {
            stages {
                stage('Clone') {
                    steps {
                        checkout scm
                    }
                }
                stage('Restore') {
                    steps {
                        sh "dotnet restore app/app.csproj --force --verbosity d" // --configfile nuget.config 
                    }
                }
            }
        }
    }
}
