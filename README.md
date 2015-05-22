# docker-devstack
Docker implementation for running a legit openstack setup using devstack.  Devstack was designed for those who would like to give openstack a try without going through the installation hassle of a full fledged stack.

# running devstack tl;dr

docker run -it --privileged -p 80:80 slimjim2234/docker-devstack /bin/bash

TODO: make supervisord script to run openstack on startup 

# details on what's going on here
Devstack is a quick one-click install for Openstack
Devstack requires some kernel stuff.  In order for it to be allowed access to this kernel stuff we need initiate the --privileged flag.  Building an openstack image does now allow access to the kernel since that breaks the concept of the "container" if it's tied down to a machine specific kernel.  So build the container for your machine by running it, create your own image from the container, then you can run devstack without any issues.
