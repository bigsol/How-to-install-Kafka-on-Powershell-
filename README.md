# How-to-install-Kafka-on-Powershell-
<hr>
<p>Pre-Requisites for installation</p>
<ul>
<li>Module ThreadJob needs to be available</li>
<li>Powershell Version needs to be 5 or ahead of it.</li>
<li>Admin access to run commands on powershell cmd</li>
<li>kafka broker list , this goes with default port of 9092</li>
</ul>
<hr>
<p>Installation Process</p>
<ul>
<li>Download file pskafka-master.rar</li>
<li>UnRAR file to C:\Folder (PS C:\pskafka-master> )</li>
<li>Install-Module -Name 'ThreadJob'</li>
<li>Import-Module .\pskafka.psd1</li>
<li>Import-Module .\pskafka.psd1</li>
</ul>

<hr>
<p>Validating the instillation</p>
<ul>
<li>Get-KafkaTopics -BrokerList xx.xxx.xx.xxx:9092 -Verbose VERBOSE: C:\pskafka-master\pskafka-master\bin\win\kafkacat.exe -b xx.xxx.xx.xxx:9092 -L__consumer_offsets</li>
</ul>

<hr>
<p>Post a message to Kafka Topic</p>
<ul>
<li>PS C:\pskafka-master> Out-KafkaTopic -Messages "1" -TopicName "test5" -BrokerList "xx.xxx.xx.xxx:9092"</li>
 
<li>PS C:\pskafka-master> Out-KafkaTopic -Messages "1" -TopicName "test5" -BrokerList "xx.xxx.xx.xxx:9092"</li>
</ul>

<hr>
<p>You can validate if your message is inserted and available in kafka cluster like below.</p>
<ul>
<li>PS C:\pskafka-master> Read-KafkaTopic -TopicName 'test5' -BrokerList 'xx.xxx.xx.xxx:9092' -MessageCount 1000 -FromBeginning -Verbose VERBOSE: D:\Navin\pskafka-master\bin\win\kafkacat.exe -b xx.xxx.xx.xxx:9092 -q -u -o beginning -c 1000 -e -C -t test5</li>
</ul>

hr>
<p># List all commands in the `pskafka` module.</p>
<ul>
 <li>PS C:\pskafka-master> Get-Command -Module pskafka.</li>
 </ul>
 
 
 
Get-Command -Module pskafka
