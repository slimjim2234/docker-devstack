# docker-devstack
Docker implementation for running a legit openstack setup using devstack.  Devstack was designed for those who would like to give openstack a try without going through the installation hassle of a full fledged stack.

# running devstack tl;dr

docker run --privileged --name devstack -it -p 80:80 slimjim2234/docker-devstack <br />
docker commit <container id> devstack <br />
docker run -it --privileged -p 80:80 slimjim2234/devstack <br />

TODO: make supervisord script to run openstack on startup

# details on what's going on here
Devstack is a quick one-click install for Openstack.  Devstack requires some kernel stuff.  In order for it to be allowed access to this kernel stuff we need initiate the --privileged flag.  Building an openstack image does now allow access to the kernel since that breaks the concept of the "container".  So build the devstack container for your machine by running it, exit the container and create your own image from the container, then run your newly built devstack image.
The installation can be very time consuming depending on your hardware (~20 mins).
