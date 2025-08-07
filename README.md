# Filscan Allocator Readme
# FilscanOfficial

Contact: filscanteam@outlook.com.

## Client Scope
Any client looking to onboard a Public Dataset to Filecoin can apply to this allocator pathway.

## How to Get DataCap
Client can get the DataCaps of VDFA on the https://github.com/FilscanOfficial/filscan-backend/issues, and they need to initialize their on chain address by sending a small amount of FIL to their address.

## Minimum client requirements
- At least 4 sealed copies of a dataset, stored with 4 separate Storage Provider entities, at least in 2 different regional locations(city).
- The dataset is made readily retrievable on the network. And the retrieval rate should not be less than 75%.
- Clients disclose their storage provider partners upfront. VPN for storage provider is not allowed.
- Clients are required to apply for DataCap using the following GitHub repo (https://github.com/FilscanOfficial/filscan-backend/issues).

## Client Diligence
We implement a stringent, multi-layered client verification process to ensure that only qualified entities are onboarded. Clients are required to provide relevant formation documents (such as registration certificates), participate in interviews, and undergo independent verification to confirm their authenticity. We then enter into a formal agreement with each client, clearly stating our requirements.
Clients must agree to maintain high data retrieval success rates, ensure balanced deal distribution, work exclusively with us, avoid VPNs. Additionally, clients are required to stake a proportional amount of FIL based on their DataCap needs to reinforce compliance. We closely monitor performance, and slashing measures will be applied if the agreement is breached. Most documents, interview notes, signed agreements, and compliance records are published on GitHub for full community transparency.

## Data Diligence
We maintain strict oversight to ensure both data and clients adhere to program guidelines and comply with applicable local and regional regulations. As part of our due diligence, clients are required to thoroughly outline their data preparation workflows, specifying the type and size of their datasets. We conduct random checks on data ownership by reviewing sampled content, and we regularly audit deal records using mapping files and by cross-referencing payload CIDs with Filecoin utilities. For governance and compliance reviews, we make all key documents available—including client submissions, compliance agreements, mapping file samples, monitoring logs, and supporting validation materials from our ongoing checks.

### Allocation Schedule
- First allocation max 5%, but no more than 256TiB; 
- Second max 10%; 
- Third max 15%; 
- Fourth max 20%; 
- Fifth and there after max 25%;
AND No allocation can be bigger than 2x of the previous one. 



## Subsequent allocation schedule:
- When clients use up > 75% of the prior DataCap allocation, a request for additional DataCap in the form of the next tranche is automatically kicked off (via the subsequent allocation bot). The allocator team will set an SLA (Service Level Agreement) to keep up with allocation review and comment on bot messages within 3 days.

## Handling disputes

The Fil+ program dispute process should begin with users submitting disputes via a Google document and posting in the relevant issue thread. An initial triage and review will be conducted within 3 days, with a full investigation and resolution communicated within 14 days. Decisions and their reasoning will be clearly documented, and an appeal window will be provided to ensure fairness. Transparent status tracking, public (anonymized) dispute logs, and periodic independent audits are key accountability mechanisms. All steps and outcomes will be recorded in the Google document, ensuring timely responses, transparency, and accountability throughout the dispute resolution process.

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
