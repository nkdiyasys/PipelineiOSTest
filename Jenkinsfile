
pipeline {
	agent any
		stages {
			stage('Build') {
				steps {
					xcodeBuild appURL: '', 
					assetPackManifestURL: '', 
					buildDir: '', 
					buildIpa: false,
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
					ipaExportMethod: 'Release',
 					ipaName:  '${BUILD_DATE}_${VERSION}', 
					ipaOutputDirectory: '', 
					keychainId: '', 
					keychainPath: '${HOME}/Library/Keychains/login.keychain', 
					keychainPwd: hudson.util.Secret.fromString(''), 
					logfileOutputDirectory: '', 
					provisioningProfiles: [[provisioningProfileAppId: 'com.lockdown.app', 		provisioningProfileUUID: '4e3f3e97-d9d0-465e-9340-de6a3e0acc30']], 
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
					sh 'xcodebuild -project PipelineiOSTest/PipelineiOSTest.xcodeproj -scheme "PipelineiOSTest" -configuration "Debug" build test -destination "platform=iOS Simulator,name=iPhone 11 Pro Max,OS=13.3" -enableCodeCoverage YES clean test | /usr/local/bin/ocunit2junit'
				}
        }
        stage('Upload') {
            steps {
                echo 'upload'
                // /path/to/altool --upload-app -f "path/to/file.ipa" -u %USERNAME% -p %PASSWORD%
                  exportIpa appURL: '',
                            archiveDir: '',
                            assetPackManifestURL: '',
                            compileBitcode: false,
                            developmentTeamID: '',
                            developmentTeamName: 'Tregaron India Holdings, LLC',
                            displayImageURL: '',
                            fullSizeImageURL: '',
                            ipaExportMethod: 'Release',
                            ipaName: '${BUILD_DATE}_${VERSION}',
                            ipaOutputDirectory: '',
                            keychainName: '',
                            keychainPath:  '${HOME}/Library/Keychains/login.keychain',
                        keychainPwd: hudson.util.Secret.fromString(''),
                            packResourcesAsset: true,
                            provisioningProfiles: [[provisioningProfileAppId: 'com.lockdown.app',                 provisioningProfileUUID: '4e3f3e97-d9d0-465e-9340-de6a3e0acc30']],
                            resourcesAssetURL: '',
                            signingMethod: 'manual',
                            thinning: '',
                            unlockKeychain: false,
                            uploadBitcode: false,
                            uploadSymbols: false,
                            xcodeProjectPath: 'PipelineiOSTest',
                            xcodeSchema: 'PipelineiOSTest',
                            xcodeWorkspaceFile: ''
            }
        }
                   } 
post {
          always { 
		echo 'Hi'
		archiveArtifacts artifacts: '**/*.ipa', fingerprint: true
           	 junit 'test-reports/*.xml'
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

