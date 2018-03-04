# Prerequiste
1- Install Logstash by using the container 


# Create a simple logstash scnario by copying input from a file to another output file 
1- change directory $cd /opt/logstash/bin.<br>
2- create a configuration file and rename it to logstash.conf.<br>
3- Add the following content to the file <br>
  ```
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
```
 - To pass the command directly from the cLI 
 ```
 ./logstash -e 'input { stdin { } } output { file { path => "/opt/logstash/logs/outlog.log"} }' --path.data /opt/logstash/logs/
 ```
4- create this 2 files inlog.log and outlog.log <br>
5- execute the chmod command for the 2 files, inlog.log and outlog.log <br>
6- cd /opt/logstash/bin <br>
7- Execute this command $./logstash --path.config logstash.conf --path.data /opt/logstash/logs/ <br>
8- Check the outlog.log file, you will find the content of the inlog.log inside the outlog.log file.


# Adding Filter on Logging DATA
1- ADD this configuration in the logstash.conf
```
input {
   stdin { }
}
filter {
   grok {
      match => {"message" => "%{WORD:verb} %{URIPATHPARAM:uri}"}
   }
}
output {
   file {
      path => "/opt/logstash/logs/outlog.log"
   }
}
```
