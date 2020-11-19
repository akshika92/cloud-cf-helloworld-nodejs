@Library('piper-lib-os') _
import static com.sap.piper.Prerequisites.checkScript
import groovy.transform.Field

node() {
   
    stage('prepare') {
        echo "starting stage prepare"
        checkout scm
        echo "checkout scm successful"
        fioriOnCloudPlatformPipeline script:this
        // fioriOnCloudPlatformPipeline(script: this, customDefaults: '.pipeline/config.yml')
        echo "end of stage prepare"
    }
    
    
    stage('build') {
        echo "starting stage build"
        mtaBuild script: this
        echo "end of stage build"
    }
    
    stage('deploy') {
        echo "starting stage deploy"
        cloudFoundryDeploy script: this              
        echo "end of stage deploy"
}
    
}

