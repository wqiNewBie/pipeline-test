  echo $spring_profile $jar_path $jar_name
  //    #发送包到目标服务器
  ssh ${host}  
  bash /server/scripts/stop.sh $JOB_NAME $jar_name $jar_path ${spring_profile}
  scp /var/lib/jenkins/workspace/${JOB_NAME}/${project_name}/target/${jar_name} $host:/${jar_path}/${JOB_NAME}

  //   #远程启动命令
  #!/bin/bash
  ssh -tt ${host} << eeooff
  cd /${jar_path}/${JOB_NAME}/ 
  echo "java -jar ${jvm_options} ${jar_name} --spring.profiles.active=${spring_profile} --server.port=${server_port} >${JOB_NAME}.log 2>&1 &"
  nohup java -jar ${jvm_options} ${jar_name} --spring.profiles.active=${spring_profile} --server.port=${server_port} >${JOB_NAME}.log 2>&1 &
  exit
  eeooff
