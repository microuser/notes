MIT license Paul Richeson 2026 , Notes taken on Friday July 26th as watched from the source of https://www.youtube.com/watch?v=PmLPbrf-x9g titled 2019-JUN-27 :: Ceph Tech Talk - Intro to Ceph


00:00 start

- Ceph is an open sourced distributed storage, providing the linux swarm of storage on strong IP backbone.
- Ceph is a unified filesystem which means filessystem capable of serving objects, blocks, and files. 
- Reliable storage assembled out of unreliable components. 
- Data durability via replication or erasure coding.
- Consistency and correctness prefered over performance.  (reading data is more verified that it was wrote).
- Ceph is free and open sourced.
- Ceph has a unified storage system architecture providing object, block, and file storage using librados (Reliable Elastic Distributed storage layer with replication
- Reliable Autonomic Distributed Object Storage
- Object -> RGW -> S3 and Swift object
- Block -> RBD -> ???
- ???

- The legacy (not RADIS) has a server with a backup. the backup is the fail over. you have one server and it runs various back ends for an application datapath. https://youtu.be/PmLPbrf-x9g?feature=shared&t=622 <img width="695" alt="image" src="https://github.com/user-attachments/assets/3ac2dae5-a0ee-4c7b-aea8-652dd45e3574">

- Ceph is a Client Cluster Architecture. Appliction connects via librados, which clusters.
- <img width="1306" alt="image" src="https://github.com/user-attachments/assets/522e175a-2968-43e9-b0b4-d3bacdcd91b2">



