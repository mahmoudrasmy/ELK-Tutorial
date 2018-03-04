# Prerequiste
1- Install Logstash by using the container 


# Create a simple logstash scnario by copying input from a file to another output file 
1- change directory $cd /opt/logstash/bin
2- create a configuration file and rename it to logstash.conf 
3- Add the following content to the file 
    input {
   file {
      path => "/opt/logstash/logs/inlog.log"
   }
}
output {
   file {
      path => "/opt/logstash/logs/outlog.log"
   }
}

4- create this 2 files inlog.log and outlog.log
5- execute the chmod command for the 2 files, inlog.log and outlog.log
6- cd /opt/logstash/bin
7- Execute this command $./logstash --path.config logstash.conf --path.data /opt/logstash/logs/
8- Check the outlog.log file, you will find the content of the inlog.log inside the outlog.log file.
