.. This work is licensed under a Creative Commons Attribution 4.0 International License.
.. http://creativecommons.org/licenses/by/4.0

Doctor capabilities and usage
=============================
Immediate Notification
----------------------

Immediate notification can be used by creating 'event' type alarm via
OpenStack Alarming (Aodh) API with relevant internal components support.

See, upstream spec document:
http://specs.openstack.org/openstack/ceilometer-specs/specs/liberty/event-alarm-evaluator.html

An example of a consumer of this notification can be found in the Doctor
repository. It can be executed as follows:

.. code-block:: bash

    git clone https://gerrit.opnfv.org/gerrit/doctor -b stable/danube
    cd doctor/tests
    CONSUMER_PORT=12346
    python consumer.py "$CONSUMER_PORT" > consumer.log 2>&1 &

Consistent resource state awareness
-----------------------------------

Resource state of compute host can be changed/updated according to a trigger
from a monitor running outside of OpenStack Compute (Nova) by using
force-down API.

See
http://artifacts.opnfv.org/doctor/danube/manuals/mark-host-down_manual.html
for more detail.

Valid compute host status given to VM owner
-------------------------------------------

The resource state of a compute host can be retrieved by a user with the
OpenStack Compute (Nova) servers API.

See
http://artifacts.opnfv.org/doctor/danube/manuals/get-valid-server-state.html
for more detail.