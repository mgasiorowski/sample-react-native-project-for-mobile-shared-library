#!groovy
 
@Library('jenkins-mobile-pipeline-shared-libraries') _
 
pipelineOptions{
    maxNumberBuildsToKeep = 10
}
 
checkoutScm {
    nodeLabel = 'centos_7'
}
 
reactNativeInstallDependencies {
    nodeLabel = 'centos_7'
    dependencyInstallationCommand = 'wget https://github.com/yarnpkg/yarn/releases/download/v1.1.0/yarn-1.1.0.js && export yarn="node ./yarn-1.1.0.js" && $yarn install'
}
 
reactNativeStaticAnalysis {
    nodeLabel = 'centos_7'
    staticAnalysisCommand = 'npm run lint'
}
 
reactNativeUnitTests {
    nodeLabel = 'centos_7'
    unitTestsCommand = 'npm test'
}
 
reactNativeBundleAndroidResources {
    nodeLabel = 'centos_7'
    bundleAndroidResourcesCommand = 'npm run bundle_android'
}
 
androidBetaUpload {
    nodeLabel = 'centos_7'
    stageSuffix = 'Android'
    isReactNative = 'true'
    gradleTasksDebug = 'clean assembleDebug'
}
 
iosBuild {
    nodeLabel = 'mac_mini'
    stageSuffix = 'iOS'
    isReactNative = 'true'
    fastlaneLane = 'build'
}
