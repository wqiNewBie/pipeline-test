node('master') {
  stage 'Checkout'
checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], 
　　　　　　　submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'c6d98bbd-5cfb-4e26-aa56-f70b054b350d', 
            url: 'git@192.168.0.16:lubo/lubo-lib/lubo-market.git']]])
  
}
