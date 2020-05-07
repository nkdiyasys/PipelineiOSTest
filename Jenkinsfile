
pipeline {
    agent any
        stages {
            stage('Build') {
                steps {
                  echo 'Build'
                  xcodeBuild appURL: '',
                                 assetPackManifestURL: '',
                                 buildDir: '',
                                 buildIpa: true,
                                  bundleID: '',
                                 bundleIDInfoPlistPath: '',
                                 cfBundleShortVersionStringValue: '',
                                 cfBundleVersionValue: '',
                                 cleanBeforeBuild: false,
                                 cleanResultBundlePath: false,
                                 compileBitcode: false,
                                 configuration: 'Release',
                                 developmentTeamID: '',
                                 developmentTeamName: 'Tregaron India Holdings, LLC',
                                 displayImageURL: '',
                                 fullSizeImageURL: '',
                                 ipaExportMethod: 'development',
                                  ipaName:  '${BUILD_DATE}_${VERSION}',
                                 ipaOutputDirectory: '',
                                 keychainId: '',
                                 keychainPath: '${HOME}/Library/Keychains/login.keychain',
                                 keychainPwd: hudson.util.Secret.fromString(''),
                                 logfileOutputDirectory: '',
                                 provisioningProfiles: [[provisioningProfileAppId: 'com.lockdown.app',         provisioningProfileUUID: '4e3f3e97-d9d0-465e-9340-de6a3e0acc30']],
                                 resultBundlePath: '',
                                 sdk: '',
                                 signingMethod: 'manual',
                                 symRoot: '',
                                 target: '',
                                 thinning: '',
                                 xcodeProjectFile: '',
                                 xcodeProjectPath: 'PipelineiOSTest',
                                 xcodeSchema: 'PipelineiOSTest',
                                 xcodeWorkspaceFile: '',
                                 xcodebuildArguments: 'build -destination \'platform=iOS Simulator,OS=13.3,name=iPhone 11 Pro Max\''
                    }
                }
            stage('Test') {
                steps {
                 echo 'Test'
                }
        }
        stage('Export') {
            steps {
                echo 'Export'
              
            }
        }
        stage('Upload') {
            steps {
                echo 'upload'
          
            }
        }
                   }
post {
          always {
        echo 'Hi'
      
                     }
         success {
          mail bcc: '', body: "<b>Details</b><br>Project: ${env.JOB_NAME} <br>Build Number: ${env.BUILD_NUMBER} <br> URL de build: ${env.BUILD_URL}", cc: '', charset: 'UTF-8', from: '', mimeType: 'text/html', replyTo: '', subject: "SUCCESS CI: Project name -> ${env.JOB_NAME}", to: "nkdiyasys@gmail.com";
             }
         failure {
               mail bcc: '', body: "<b>Details</b><br>Project: ${env.JOB_NAME} <br>Build Number: ${env.BUILD_NUMBER} <br> URL de build: ${env.BUILD_URL}", cc: '', charset: 'UTF-8', from: '', mimeType: 'text/html', replyTo: '', subject: "ERROR CI: Project name -> ${env.JOB_NAME}", to: "nkdiyasys@gmail.com";
               }
         unstable {
        mail bcc: '', body: "<b>Details</b><br>Project: ${env.JOB_NAME} <br>Build Number: ${env.BUILD_NUMBER} <br> URL de build: ${env.BUILD_URL}", cc: '', charset: 'UTF-8', from: '', mimeType: 'text/html', replyTo: '', subject: "UNSTABLE CI: Project name -> ${env.JOB_NAME}", to: "nkdiyasys@gmail.com";
             }
         changed {
        mail bcc: '', body: "<b>Details</b><br>Project: ${env.JOB_NAME} <br>Build Number: ${env.BUILD_NUMBER} <br> URL de build: ${env.BUILD_URL}", cc: '', charset: 'UTF-8', from: '', mimeType: 'text/html', replyTo: '', subject: "PREVIOUSLY FAILING BUT IS NOW SUCCESSFUL CI: Project name -> ${env.JOB_NAME}", to: "nkdiyasys@gmail.com";
            }
               }
}

