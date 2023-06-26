# AzureMessageBus-ACE-JMS

The repo contains the basic building blocks and an example ACE flow to create a JMS connection to Azure service bus.
<BR>
It is built upon the qpid JMS libraries for AMQP.
<BR>
The policy does most of the hard work - it points to the jar file for the JMS connection classes, and also the bindings file.
<BR>
The conection factory name here is descrbed by the bindings file. This file is used as-is to connect to Azure Service Bus.
The credentials are provided by the Azure service bus environment.  
Note that in the JMS node the provider name is a combination of the policy folder and policy name. The documentation is not clear on this.
<BR>
I also created a compute node to set the destination as the JMS node seemed not to be reading the destination from the node properties correctly.

You will aslo have to create credentials based on the Connection factory name and an Azure Service Bus access key name and value - something like as below, shown for a connection factory name of 'SBCF'
<BR>
mqsisetdbparms" -w {workdir} -n jms::SBCF -u {keyName} -p {keyValue}
