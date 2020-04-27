
pipeline {
	agent any
		stages {
			stage('Build') {
				steps {
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
					configuration: 'development', 
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
xcodebuild -exportArchive -archivePath **/PipelineiOSTest.xcarchive \
-exportOptionsPlist **/*xportOptions.plist \
-exportPath /Users/nithinkumar/Desktop/NK/
}
}
                   }  
}

