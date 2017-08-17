Pratai Nodes
============

Here is where the action happen, the nodes are in charge to execute the functions.

After every node gets deployed it automatically gets registered in the cluster so it can start
receiving jobs to execute.

For OpenStack you don't need a dedicated compute host for Pratai, although you can, but you can easily
deploy the nodes within a dedicated tenant so you can even scale without issues and/or provide the functionality
just to a subset of your users.

Another recommendation is to use the internal keystone endpoints between the control plane and the nodes.
Unless you want to make this service public, in that case, the API should listen on a public endpoint as well.  

The following components should be deployed in the nodes.

.. toctree::
   :maxdepth: 2

   install_drivers
   install_runtimes