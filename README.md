# devops-test-answer
Please follw below steps:

Option 1

1. Download zip file to your workstation https://github.com/steve20170207/devops-test-answer.git
2. unzip the repository and go to the folder where content extracted. 
3. make sure dockerfile and start.sh in current folder and run build command:

     docker build --tag dev-ops-test-centos .
4. use docker images to list the iamges and make suse image generated.

     REPOSITORY            TAG                 IMAGE ID            CREATED             SIZE
     
     dev-ops-test-centos   latest              a3e4a5dee189        About an hour ago   101MB
     
5.  start the container by issuing below command:

       docker run  -it -d -p hostIP:hostPort:containerPort  dev-ops-test-centos /bin/sh
   
   for example
   
        docker run  -it -d -p 192.168.99.100:8088:8080  dev-ops-test-centos /bin/sh
        
6. open broswer lauch http://hostIP:hostPort

    For example http://192.168.99.100:8088
    
    you are expected to see a line of text:

            Hello World!

option 2 

 use docker pull get the built image

 steveliehealth/dev-ops-test-centos:latest
 
re-tag and launch the container as per step 5 in option 1 
 
