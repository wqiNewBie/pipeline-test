node('master') {
  //拉取git代码仓库
  stage 'Checkout'
 checkout([$class: 'GitSCM', branches: [[name: '*/master']], 
           doGenerateSubmoduleConfigurations: false, extensions: [], 
           submoduleCfg: [], 
           userRemoteConfigs: [[credentialsId: 'ab523fcf-4991-4087-8adc-41c99812924e', 
                                url: 'git@192.168.0.16:lubo/lubo-lib/lubo-market.git']]])
  
//构建
    stage 'Build'
        withMaven(
        maven: 'maven3.5.2',
        mavenSettingsConfig: '9e88adc5-8b36-4f00-b6f6-fdb15e9286ae') {
        sh 'clean install -pl lubo-market-api -am -amd -Pdev -Dmaven.test.skip=true'
    }
  
}
