#!groovy
// def DEV_PROJECTNAME = "demo-dev"
// def UAT_PROJECTNAME = "demo-uat"
// def BUILDCONFIGNAME="sampledotnet"
// def IMAGE_NAME="sampledotnet:latest"
// def UATIMAGENAME = "sampledotnet:UATReady-1.0.0"

pipeline {
    agent {
        docker {
            image 'jenkins/dotnet-60:6.0-42'
        }
    }
    // environment {
    //     dotnet = '/var/lib/jenkins'
    // }
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
        //   stage('Publish') {
        //     sh "dotnet publish Test.csproj --no-restore  -c Release /p:MicrosoftNETPlatformLibrary=Microsoft.NETCore.App"
        //   }
        //   stage('Build Image') {
        //     sh "oc -n $DEV_PROJECTNAME start-build $BUILDCONFIGNAME --from-dir=./bin/Release/netcoreapp2.2/rhel.7-x64/publish --follow"
        //     sh "oc -n $DEV_PROJECTNAME tag $DEV_PROJECTNAME/$IMAGE_NAME $UAT_PROJECTNAME/$UATIMAGENAME"
        //   }
    }
}