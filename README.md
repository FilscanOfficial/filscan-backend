# Filscan Allocator Readme
# FilscanOfficial

Contact: filscanteam@outlook.com.


Below is an summary of the key client requirements and processes that the Filscan team will follow to oversee proper due diligence while insuring compliance to Fil+ guidelines for DataCap allocations.

## Background

### What is Filecoin Plus?
[Filecoin Plus](https://github.com/filecoin-project/FIPs/blob/master/FIPS/fip-0003.md) aims to maximize the amount of useful storage on Filecoin by adding a layer of social trust to the Network. [Clients](https://github.com/filecoin-project/filecoin-plus-client-onboarding#client) can apply to Notaries to receive [DataCap](https://github.com/filecoin-project/filecoin-plus-client-onboarding#datacap), which can be used to incentivize Storage Providers (SPs) to take storage deals. SPs who take deals that are compensated with DataCap receive a 10x to their quality adjusted power - increasing their probability of winning block rewards. Filecoin Plus puts power in the hands of Clients and incentivizes SPs to support real use case on the Network.
For more detailed descriptions, please refer to [here](https://github.com/filecoin-project/FIPs/blob/master/FIPS/fip-0003.md).

### What is an Allocator?
As of March 2024, there are a total of 4 Pathways for Client to obtain Datacap, which are:
1. [Datacap faucet](https://verify.glif.io/) *(32 GiB/time/day)*
2. [Ordinary dataset application](https://github.com/filecoin-project/filecoin-plus-client-onboarding/issues)  *(0-500 TiB/time)*
3. [Large dataset application](https://github.com/filecoin-project/filecoin-plus-large-datasets/issues)  *(>500 TiB/time)*
4. [Fil-E dataset application](https://github.com/filecoin-project/filecoin-plus-large-datasets/issues)  *(private data)*

Now the community has stopped further maintenance of 2), 3), and 4), and has been replaced by a new channel called Allocator. The Allocator channel has several Pathways, each defined by an organization or individual for rules and maintenance, and all allocator information can be viewed [here](https://github.com/filecoin-project/notary-governance/issues?q=allocator).

### What is Filscan Allocator?
Filscan Allocator is a pathway maintained by Filscan team as an Allocator, and clients can apply for Datacaps.
https://github.com/FilscanOfficial/filscan-backend/issues


## Using DataCap
### How to Get DataCap
Client can get the DataCaps of VDFA on the https://github.com/FilscanOfficial/filscan-backend/issues, and they need to initialize their on chain address by sending a small amount of FIL to their address.

#### Current Scope:
Any client looking to onboard a Public Dataset to Filecoin can apply to this allocator pathway.

#### Minimum client requirements:
- At least 4 sealed copies of a dataset, stored with 4 separate Storage Provider entities, at least in 2 different regional locations(city).
- The dataset is made readily retrievable on the network. And the retrieval rate should not be less than 75%.
- Clients disclose their storage provider partners upfront. VPN for storage provider is not allowed.
- Clients are required to apply for DataCap using the following GitHub repo (https://github.com/FilscanOfficial/filscan-backend/issues).

#### Once an application is submitted, diligence to be completed on clients includes:
We implement a stringent, multi-layered client verification process to ensure that only qualified entities are onboarded. Clients are required to provide relevant formation documents (such as registration certificates), participate in interviews, and undergo independent verification to confirm their authenticity. We then enter into a formal agreement with each client, clearly stating our requirements.
Clients must agree to maintain high data retrieval success rates, ensure balanced deal distribution, work exclusively with us, avoid VPNs. Additionally, clients are required to stake a proportional amount of FIL based on their DataCap needs to reinforce compliance. We closely monitor performance, and slashing measures will be applied if the agreement is breached. Most documents, interview notes, signed agreements, and compliance records are published on GitHub for full community transparency.

### The allocation schedule for trusted users is:
First allocation max 5%, but no more than 256TiB; 
Second max 10%; 
Third max 15%; 
Fourth max 20%; 
Fifth and there after max 25%;
AND No allocation can be bigger than 2x of the previous one. 



#### Subsequent allocation schedule:
- When clients use up > 75% of the prior DataCap allocation, a request for additional DataCap in the form of the next tranche is automatically kicked off (via the subsequent allocation bot). The allocator team will set an SLA (Service Level Agreement) to keep up with allocation review and comment on bot messages within 3 days.

#### Compliance check mechanisms for the client applications:
We maintain strict oversight to ensure both data and clients adhere to program guidelines and comply with applicable local and regional regulations. As part of our due diligence, clients are required to thoroughly outline their data preparation workflows, specifying the type and size of their datasets. We conduct random checks on data ownership by reviewing sampled content, and we regularly audit deal records using mapping files and by cross-referencing payload CIDs with Filecoin utilities. For governance and compliance reviews, we make all key documents available—including client submissions, compliance agreements, mapping file samples, monitoring logs, and supporting validation materials from our ongoing checks.

----------------------------
# Filscan Backend Readme
# Overview

Filscan is a blockchain browser for Filecoin, which can be used to view Filecoin blockchain data, including querying addresses, messages information, block heights, miner information, token information, etc.

# Table of Contents
- [Overview](#overview)
- [Table of Contents](#table-of-contents)
- [Front-End](#front-end)
- [Back-End](#back-end)
  - [Build and Install](#build-and-install)
    - [Environment](#environment)
    - [System Require](#system-require)
    - [Build](#build)
    - [Configuration](#configuration)
    - [Run](#run)
  - [API Document](#api-document)
  - [License](#license)

# [Front-End](https://github.com/ipfs-force-community/filscan-frontend)


# Back-End

## Build and Install

### Environment

- golang >= v1.13
- mongo >= v4.2
- lotus >= v0.2.7

### System Require

- Linux or Mac OS

### Build
```
git clone (githuburl)

cd Backend

make build-lotus

go build
```
### Configuration

Edit app.conf in path /conf and set the correct parameter
```
mongoHost = "127.0.0.1:27017"

mongoUser = "root"

mongoPass = "admin"

mongoDB   = "filscan"

lotusGetWay="192.168.1.1:1234"
```
### Run

Make sure mongo and lotus is active, and run the filscan_lotus
```
./filscan_lotus
```
The application will check lotus and mongo’s status. The application will stop if got any error from them. If application start success, it will work until sync all data down from lotus. 

## API Document

Check document [here](Filscan_Interface_v1.0.md)


## License
Dual-licensed under 

[MIT](https://github.com/filecoin-project/lotus/blob/master/LICENSE-MIT) 

[Apache 2.0](https://github.com/filecoin-project/lotus/blob/master/LICENSE-APACHE)
