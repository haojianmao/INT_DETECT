# GRAY FAILURES DETECTION AND LOCALIZATION
## Introduction
Network reliability becomes increasingly important in modern data center networks (DCNs). The DCNs are expected to work sustainably under internal failures and assist network operators in troubleshooting them rapidly. However, some network failures will happen silently with packets discarded without producing any explicit notification before causing tremendous damage to the network. To troubleshoot these “gray failures”, in this work, we present a rapid gray failure detection and localization mechanism based on the recently proposed In-band Network Telemetry (INT). Specifically, we leverage simplified INT probe packets to conduct network-wide telemetry to help the servers under ToR switches obtain all the feasible paths between sources and destinations. Once a network failure occurs, the affected thus unavailable paths will immediately be detected and flushed out of the path information table at each server by a timeout mechanism. Hence, servers can proactively perform source routing-based fast traffic reroute to avoid massive packet loss and retain uninterrupted quality of experience. At the meantime, all the aged path entries will be uploaded to a remote controller for centralized failure localization by identifying common path elements. To verify the feasibility of our design, we build a virtual network testbed with software P4 switches and a Redis database. Evaluation shows that our system can successfully detect network gray failures and reroute the affected traffic in no time while complete failure localization within only a few seconds.

## System
The system includes six modules: `bmv2_model`, `controller`, `flow_table`, `p4_source_code`, `packet`, `topology`.

### bmv2_model
The bmv2 target
#### simple_switch
The target used in the network is simple_switch.

### controller
