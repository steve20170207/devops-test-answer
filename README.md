# devops-test-answer
Please follw below steps
1. gitclone to downoad repository to your workstation 
2. unzip the repository and  go to the folder where fle extractd 
3. run build command:
docker build --tag dev-ops-test-centos .

4. docker run  -it -d -p hostIP:hostPort:containerPort  dev-ops-test-centos /bin/sh
For example
docker run  -it -d -p 192.168.99.100:8088:8080  dev-ops-test-centos /bin/sh
5. open broswer lauch http://hostIP:hostPort
   For example http://192.168.99.100:8088
   you are expected to see a line of text:

            Hello World!
