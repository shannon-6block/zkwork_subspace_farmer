# ZKWork Subspace farmer


## zkwork pool address
```shell
pool_address=ai3.asia.zk.work:10020
```

A git repository for ZKWork Subspace farmer release versions

* Download releases : https://github.com/6block/zkwork_subspace_farmer/releases
* Discord Group :  https://discord.com/invite/pKufwyjGFF
* Twitter : https://x.com/ZKWorkHQ

## We are on taurus testnet with official version `taurus-2024-nov-01`

## Requirements
- OS Version: Ubuntu 22.04 +

- Nvidia Driver Version: 555.42.02 +

## Start Farming

### 1. Choose and download the corresponding version on release page

### 2. Unzip
    tar zxvf <YOUR DIR>/zkwork_taurus-2024-nov-01.release.tar.gz

### 3. Start farming

#### 3.1 Start subspace local node
    1. keep .env file and subspace-node binary in the same directory, then open .env file and set POOL_ADDR_IPV4 with the pool address:
     POOL_ADDR_IPV4="ai3.asia.zk.work:10020"

    2. start subspace-node
     ./subspace-node run --base-path <NODE_DATA_PATH> --farmer --rpc-listen-on <LOCAL_IP>:30003 --rpc-cors "all"

#### 3.2 Start subspace farmer cluster
   Notes: farmer cluster and subspace local node need be started within the same intranet.

   ##### 3.2.1 instatll and start NATS server
      https://docs.autonomys.xyz/farming/advanced-cli/cluster/#core-messaging-technology-natsio

   ##### 3.2.2 start farmer cluster
    1. start Controller
     ./subspace-farmer cluster --nats-server nats://<NATS_IP>:4222 controller --base-path <FARMER_DATA_PATH> --node-rpc-url ws://<NODE_IP>:30003

    2. start Cache
     ./subspace-farmer cluster --nats-server nats://<NATS_IP>:4222 cache path=<FARMER_DATA_PATH>,size=<SIZE>

    3.  start Farmer
     ./subspace-farmer cluster --nats-server nats://<NATS_IP>:4222 farmer --reward-address <YOUR_REWARD_ADDRESS> --custom-name <YOUR_NAME> path=<FARMER_DATA_PATH>,size=<SIZE>

    4. start Plotter
     ./subspace-farmer cluster --nats-server nats://<NATS_IP>:4222 plotter