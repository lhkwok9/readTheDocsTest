.. _xjc_class_overview:

Class Overview: Xjc
===================

The ``Xjc`` class is a specialized hardware task (``Raad::Hardware::Task``) designed to interface with an EtherCAT-connected force/torque sensor.

Responsibilities
----------------

*   **Initialization**: Uses a JSON configuration to locate the exact EtherCAT device and slave index using an ``EcDeviceMapper``.
*   **Execution Loop (``step``)**: Routinely polls the physical Xjc sensor via EtherCAT for spatial data (Force and Torque).
*   **Event Handling**: Forwards the 6-axis data (Fx, Fy, Fz, Tx, Ty, Tz) to a registered callback (``xjcSensorDataCb_``) for downstream processing.
*   **Frequency Control**: Maintains its execution rate by enforcing thread sleep delays based on the configured frequency.
