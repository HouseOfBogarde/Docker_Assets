Note:  Unifi application runs within a docker container, in its own network with IP.  Therefore when the app runs it sees its internal docker ip and not the actual host IP that can be seen by the host network.

During the device adoption, Unifi will send its controller IP to the device for it to use, gets the incorrect IP and sits in an adoption loop

Many suggestions are to set Inform Host overide in the advanced settings of the app to the true host IP http://hostip:8080/inform

However, by accident, I set a DNS lookup of unify.home to point to the docker host.  The devices appear to loop a few times and seem to check on teh local network for a host for http://unify:8080 and find teh controller.   All devices eventually adopt and get the correct setting without the overide
  
