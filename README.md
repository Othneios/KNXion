# KNXion
KNXion

A library for communicating with KNX

Implementation is based on C++, with connectors to KNXNet/IP as client and as server via Routing and Tunneling. Other transport may be added later. Each protocol is implemented by a FSM with a read and a write queue, connected to a routing bus. Multiple converters are possible to translate between pdus.

Protocols are router, tunnel, file, udp, tcp, html, log and dump

A simple scenario is: router connected to the pdu-bus where a dumper is listening. This implements a monitor.

Internally shared pointers to pdus are used to avoid copying pdus.

Windows has problems with utf-8. Here are some special handlings neccessary: wherever there are special non-ascii characters they have to converted to iso 8859-1 first which is a serious drawback. Later two-byte characters will be used to avoid this work-around.
