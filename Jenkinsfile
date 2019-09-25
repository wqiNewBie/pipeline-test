node('master') {
  //拉取git代码仓库
  stage 'Checkout'
  checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], 
         submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'c6d98bbd-5cfb-4e26-aa56-f70b054b350d', 
              url: 'git@192.168.0.16:lubo/lubo-lib/lubo-market.git']]])

 
  
//构建
    stage 'Build'
        bat '''cd "D:\\Program Files (x86)\\Jenkins\\workspace\\LoginServiceCore\\LoginApi.Hosting.Web"
            dotnet restore
            dotnet build
            dotnet publish --configuration Release --output D:\\publish\\LoginServiceCore'''
}
