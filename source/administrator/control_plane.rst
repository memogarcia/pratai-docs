Control Plane
=============

OpenStack and for that matter every vendor has its own opinions on how to deploy OpenStack for production.
One of the most common approach is to deploy "controllers" with a single instance or in a HA (high avalibility)
environment.

For Pratai, this part is transparent but we try to leverage the configuration that you already have.
For the control plane we need to deploy the following components:

.. toctree::
   :maxdepth: 2

   initialize_db
   install_api
   install_agent
   install_scheduler
