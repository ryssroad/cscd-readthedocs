# Snapshot

**Process**

A snapshot of nodes is taken daily in Cascadia to ensure smooth and efficient validator service operation. Following the completion of each new snapshot, all previous snapshots are removed to maximize available server space.



**Purpose of Node Snapshot**

The node snapshot has been designed with the intention to optimize validator service performance on the Cascadia chain. To ensure the snapshot size is minimized while remaining fully functional for validators, certain settings are employed to economize disk space. It is advised that node operators adopt these adjustments in their nodes as well.



**Limitations and Functionalities**

Please note, with this efficient utilization of disk space, your node's functionalities may be limited beyond signing blocks. For instance, your node may not function as an RPC endpoint, which isn't recommended to be run on a validator node in any case.



**Periodic State-Sync**

The nodes used for snapshot creation undergo state sync periodically. As a result, the snapshot size might occasionally appear unusually small. This process is part of an ongoing effort to optimize performance and efficiency.
