<!-- .slide: data-background-gradient="linear-gradient(to bottom, #283b95, #17b2c3)" -->

# Helium Network

> People-Powered Networks

Note: This will only appear in the speaker notes window.

---

## Content

- Blockchain
- Mining and Token Rewards
- Proof of Coverage
- Tokenomics
- Mine HNT
- LoRaWan On Helium
- Use the Network

---

## Blockchain

The Helium Blockchain is a new blockchain built from the ground up to incentivize the creation of decentralized, public wireless networks.

- Native token: $HNT
- Consensus algorithm: Proof of Coverage (PoC)
- Officially launched on July 29, 2019.
- Supports public LoRaWAN network.

--

## Mining and Token Rewards

| Reward Type           | Description                                                                                  |
|-----------------------|----------------------------------------------------------------------------------------------|
| PoC Challenger        | Awarded to any Hotspot that transmits a PoC packet after being targeted by the challenger.   |
| PoC Challengees       | Rewarded to any Validator* that creates a valid PoC challenge and submits to the blockchain. |
| Witnesses             | Distributed to selected Hotspots that witness a beacon packet as part of a PoC Challenge.    |
| Consensus Group       | Divided equally among the Validators that are part of the Consensus Group.                   |
| Security Tokens       | Awarded to Helium, Inc and other Network investors who hold Security Tokens.                 |
| Network Data Transfer | Distributed each epoch to Hotspots that route LongFi sensor data for sensors on the Network. |
| Total                 |                                                                                              |

--

### Target HNT Production Per Epoch

The target production rate for new HNT minted per month is 2,500,000

- Target block time is 60 seconds. (block is mined)
- Target epoch size is 30 blocks.

HNT minted per epoch:

- (43200 minutes per month / 30 minutes per epoch) = 1440 epochs per month
- (2.5m tokens minted per month / 1440 epochs per month) = 1736.1111 HNT per epoch

--

### HNT Distributions per epoch

| Reward Type           | Percentage    | HNT Earned  |
|-----------------------|---------------|-------------|
| PoC Challenger        | 0.85%         | 14.7236     |
| PoC Challengees       | 4.73%-12.23%  | 82.1-212.3  |
| Witnesses             | 18.92%-48.92% | 328.5-849.3 |
| Consensus Group       | 6%            | 104.17      |
| Security Tokens       | 32%           | 555.55      |
| Network Data Transfer | Up to 37.50%  | Up to 651   |
| Total                 | 100%          | 1736.1111   |

if the DC burned doesn't equal the value of 651 HNT, the remaining HNT is redistributed to the Proof of Coverage (PoC) rewards groups pro-rata.

--

### Consensus Group (CG)

- consists of 16 members is elected per epoch
- all active Helium Hotspots in the Helium network are eligible to be elected.
- in each election, 4 new CG members are elected. Other 12 are from previous election.
- once elected, a Hotspot can participate in up to 4 consecutive CG.
- poorly performing CG members are removed before 4 epoch limit is reached

---

## Proof of Coverage

The Helium Network is a physical wireless network based on the amount of reliable coverage it can create for users deploying connected devices on it.

PoC relies on the following characteristics of radio frequency(RF):

- RF has limited physical propagation and, therefore, distance;
- The strength of a received RF signal is inversely proportional to the square of the distance from the transmitter
- RF travels at the speed of light with (effectively) no latency;

---

## Tokenomics

> HNT - Data Credits - Net Emission

![Icons](https://www.helium.com/static/images/new/hntheader.svg)

--

### HNT

- 5m HNT is minted per month -> It's currently 2.5m HNT after halving in August 1, 2021.
- HNT halving happens every 2 years from the genesis block.
- no cap on maximum supply -> changed to maximum 223M HNT
- current supply: 128M HNT

--

### Helium security token (HST)

Helium security token (HST) - $55M funding:

- 32% of all earnings are rewarded to Helium, Inc and other Network investors who hold Security Tokens.
- Reward percentage decreases every year. 15% by 21st year (2040).

--

### Net emission /not implemented yet/

What if the protocol run out of HNT?

- Net Emissions recycle a pool of 'burned' HNT available for use in rewarding CG members and reward data transmitters in perpetuity.
- It doesn't add to the amount of HNT outstanding and therefore do not violate the max supply
- Net Emissions are capped at 1% of current issuance (3,424 HNT minted per epoch) at 34.24 HNT

![Net emission](https://www.helium.com/static/images/new/netemissioncontribution2.svg)

--

### Data Credits

Data Credits are the only payment accepted to send data over Helium Network.

- One Data Credit pegged to $0.00001
- Data credit produced by burning HNT (Burn and mint equilibrium BME)
- Data credits are non-transferrable and can only be used by the wallet owner.
- Minimum data credit buy amount is $10.

--

### Burn and Mint (BME)

![HNT to DC](https://www.helium.com/static/images/new/CreateDC.svg)

Burn `HNT` to mint `Data Credits`

- Price should increase if # of tokens burned > # of tokens of minted
- Price should decrease if # of tokens burned < # of tokens of minted

--

### HNT Price oracles

    Oracles provide a way for the decentralized Web3 ecosystem to access existing data sources.

Blockchain uses HNT/USD price to convert HNT to DC at a rate pegged at $.00001.

- Every 10 blocks (every 10 minutes) the blockchain establish a new HNT/$USD price
- Prices are submitted by 11 oracles.
  - Helium Foundation
  - Nova Labs
  - Nine (9) Anonymous Individual Community Members
- Data credits can be bought by credit cards. Helium inc handles buying and burning HNT by using oracle prices.

---

## Mine HNT

- Helium Hotspots mine $HNT and were originally built by Helium, Inc.
- But are now built by our growing ecosystem of approved manufacturers.

<!-- [<img src="https://docs.helium.com/img/mine-hnt/minehnticon.png" width="25%"/>](https://docs.helium.com/img/mine-hnt/minehnticon.png) -->

--

### Full Hotspots

- maintain full copy of HNT blockchain
- can participate in all potential reward activities.
- only manufactured by approved Makers.

--

### Light Hotspots

- participate as a Full Hotspot, without maintaining a local copy of the blockchain
- in progress. updated in HIP 70.
- A Hotspot on the Helium network will Beacon automatically on a pre-determined time interval (up to several times a day)
- submit PoC receipts directly to an Off-Chain PoC Oracle
- does not store a copy of the Blockchain, eliminating synchronization
- transmit packets on behalf of IoT devices on the network to an Off-Chain Data Oracle
- does not participate in Consensus Groups
- earn $HNT

--

### Data only Hotspots

- Eligible for Network Data Transfer Rewards but not Proof of Coverage Rewards.

### Validators

- New entity that perform the work of the consensus group including verifying transactions and adding new blocks to the blockchain
- Cloud based

### Maker Apps

- All manufacturer are required to support their customers with a bespoke Mobile App to onboard their Hotspots, maintain their Hotspots with diagnostic tools, and various basic troubleshooting tools

---

## LoRaWAN on Helium

Typically single entity owns LoRaWAN Network Server (LNS).

Helium supports decentralized independent operation of LNS. Therefore, it enables the multi-tenancy of LNS’s on the same Public LoRaWAN Network.

- compatible with LoRaWAN class A devices
  - Class B: [A]
  - Class C: [A, B]
- enabled the multi-tenancy of LNS’s on the same Public LoRaWAN Network. Public wireless infrastructure is now compatible with privately-run network servers.

--

### Class A devices

- Device spends most of its time in an idle state(sleep mode). When there is a change in the environment, it wakes up and initiates an uplink, transmitting the data about the changed state back to the network (Tx).

- There is no way the application of the end device can wake up a Class A device. Given this limitation, Class A devices are not suitable for actuators.

[![LoRaWAN class A devices](<https://lora-developers.semtech.com/uploads/documents/images/Class_A.png>)](https://lora-developers.semtech.com/documentation/tech-papers-and-guides/lora-and-lorawan/)

--

### Class B devices

An enhancement of Class A, Class B mode offers regularly-scheduled, fixed-time opportunities for an end device to receive downlinks from the network, making Class B end devices suitable for both monitoring sensors as well as actuators.

[![LoRaWAN class B devices](<https://lora-developers.semtech.com/uploads/documents/images/Class_B.png>)](https://lora-developers.semtech.com/documentation/tech-papers-and-guides/lora-and-lorawan/)

--

### Class C devices

- Class C are always `on`. They do not depend on battery power. Class C devices include such things as street lights, electrical meters etc. These devices are always listening for downlink messages, unless they are transmitting an uplink.
- They offer the lowest latency for communication from the server to an end device.

[![LoRaWAN class B devices](<https://lora-developers.semtech.com/uploads/documents/images/Class_C.png>)](https://lora-developers.semtech.com/documentation/tech-papers-and-guides/lora-and-lorawan/)

---

## Use the Network

---

## Thank You
