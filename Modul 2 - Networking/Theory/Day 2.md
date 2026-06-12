# Day 2 — Network Topologies

Bus  |  Ring  |  Star  |  Mesh  |  Hybrid  |  Tree

# Introduction

# What is Network Topology?

## Definition

A Network Topology is the structure or layout of how devices are connected inside a network.

It shows:

* Devices kaise connected hain
* Data kis path se travel karta hai
* Network ka shape kya hai

Simple samajh:

“Topology network ka map hota hai.”

---

# Real Life Example

Road system imagine karo:

* Roads = Network connections
* Cars = Data
* Buildings = Devices
* Traffic routes = Data paths

Jaise city ka road structure hota hai,
waise network ka topology structure hota hai.

---

# 💡 Simple Definition

“Network Topology batati hai devices kaise connected hain aur data kaise move karta hai.”

---

# Why Topology Important hai?

Topology decide karti hai:

* Network speed
* Security
* Reliability
* Cost
* Troubleshooting
* Scalability

Cyber Security me topology bahut important hoti hai kyuki:

* Different topologies ke security risks different hote hain
* Attack paths topology par depend karte hain

---

# Types of Topology View

## 1. Physical Topology

Actual physical layout.

Example:

* Cables kaha hain
* Router kaha hai
* Devices kaha placed hain

---

## 2. Logical Topology

Data actual me kaise flow karta hai.

Kabhi physical aur logical topology same nahi hoti.

---

# Example

Physical:
Sab devices switch me connected.

Logical:
Data specific route se flow ho raha hai.

---

# The Six Main Topologies

1. Bus Topology
2. Ring Topology
3. Star Topology
4. Mesh Topology
5. Hybrid Topology
6. Tree Topology

---

# 01. Bus Topology

# What is Bus Topology?

Bus topology me:
sab devices ek single cable se connected hote hain.

Is main cable ko:

* Bus
* Backbone

kehte hain.

Data same cable par travel karta hai.

---

# Real Life Analogy

School hallway imagine karo.

* Hallway = Main cable
* Students = Devices

Teacher shout karta hai:
sab sunte hain,
but sirf jis student ka naam hai wahi respond karta hai.

---

# How Bus Topology Works

1. Device data send karta hai
2. Data backbone cable me travel karta hai
3. Sab devices data receive karte hain
4. Intended device data accept karta hai

---

# Main Components

| Component      | Work                    |
| -------------- | ----------------------- |
| Backbone Cable | Main communication line |
| Terminator     | Signal stop karta hai   |
| Nodes          | Connected devices       |

---

# Terminator kya hota hai?

Cable ke ends par lagta hai.

Purpose:
Signal reflection rokna.

Agar terminator nahi ho:
signals bounce back karenge.

---

# Features of Bus Topology

* Single cable use hoti hai
* Shared communication medium
* Cheap setup
* Simple structure

---

# Advantages

| Advantages                  |
| --------------------------- |
| Cheap                       |
| Easy installation           |
| Less cable required         |
| Small networks ke liye good |

---

# Disadvantages

| Disadvantages                         |
| ------------------------------------- |
| Main cable fail = entire network down |
| Low security                          |
| Slow under heavy traffic              |
| Collision problem                     |
| Troubleshooting difficult             |

---

# Collision kya hota hai?

Jab 2 devices same time data bhejte hain:
data collide ho jata hai.

Result:

* Slow network
* Data corruption

---

# Cyber Security Risk 🔐

Sab devices same cable use karte hain.

Attacker:

* Traffic sniff kar sakta hai
* Sensitive data capture kar sakta hai

Bus topology least secure topologies me se ek hai.

---

# Real Use Cases

Old:

* Computer labs
* Small offices

Modern networks me rarely use hoti hai.

---

# 02. Ring Topology

# What is Ring Topology?

Ring topology me:
har device 2 devices se connected hota hai.

Network circular loop form karta hai.

---

# Data Flow

Data:

* One direction me move karta hai
* Device to device pass hota hai

---

# Real Life Analogy

Relay race imagine karo.

Baton:
runner se runner tak pass hota hai.

Waise hi:
data device se device tak travel karta hai.

---

# How Ring Works

1. Sender data send karta hai
2. Data next device ko jata hai
3. Data ring me circulate karta hai
4. Destination device receive karta hai

---

# Token Passing

Many ring networks token system use karte hain.

Token:
special permission packet hota hai.

Jiske paas token hota hai:
sirf wahi data send kar sakta hai.

---

# Advantage of Token

Collision avoid hota hai.

---

# Features

* Circular structure
* Sequential communication
* Organized data flow

---

# Advantages

| Advantages                     |
| ------------------------------ |
| No collisions                  |
| Equal access                   |
| Good heavy traffic performance |
| Predictable communication      |

---

# Disadvantages

| Disadvantages                      |
| ---------------------------------- |
| One device failure affects network |
| Difficult troubleshooting          |
| Adding devices disrupts network    |
| Slower than star                   |

---

# Cyber Security Note 🔐

Agar attacker ek device compromise kare:
wo traffic intercept kar sakta hai.

Token manipulation attacks bhi possible hote hain.

---

# Real Use Cases

Old IBM token ring networks.

Modern networks me limited use.

---

# 03. Star Topology

# What is Star Topology?

Sab devices individually:
ek central device se connect hote hain.

Central device:

* Switch
* Hub
* Router

ho sakta hai.

---

# Data Flow

Device directly dusre device ko data nahi bhejta.

Sab data:
central switch ke through jata hai.

---

# Real Life Analogy

Airport hub system.

Flights:
pehle hub airport jati hain,
phir destination par.

---

# Features

* Centralized structure
* Most common topology
* Easy management

---

# Why Most Popular?

Modern:

* Home Wi-Fi
* Offices
* Schools

mostly star topology use karte hain.

---

# Advantages

| Advantages                             |
| -------------------------------------- |
| Easy troubleshooting                   |
| Device failure affects only one device |
| High performance                       |
| Easy expansion                         |
| Better security control                |

---

# Disadvantages

| Disadvantages                         |
| ------------------------------------- |
| Central switch failure = network down |
| More cable needed                     |
| Cost increases                        |

---

# Switch vs Hub

| Switch                       | Hub          |
| ---------------------------- | ------------ |
| Smart                        | Dumb         |
| Sends data to correct device | Sends to all |
| More secure                  | Less secure  |
| Faster                       | Slower       |

---

# Cyber Security Note 🔐

Switch par:

* Firewall
* VLAN
* Monitoring

easily apply kiya ja sakta hai.

But:
central switch single point of failure hota hai.

---

# Real Use Cases

* Offices
* Schools
* Homes
* Data centers

---

# 04. Mesh Topology

# What is Mesh Topology?

Mesh topology me:
har device directly har device se connected hota hai.

Multiple paths available hote hain.

---

# Real Life Analogy

Spider web.

Ek thread break ho jaye:
to bhi web connected rehta hai.

---

# Features

* Multiple connections
* High redundancy
* No single failure point

---

# Types of Mesh

## Full Mesh

Har device sabse connected.

---

## Partial Mesh

Some devices directly connected.

---

# Advantages

| Advantages              |
| ----------------------- |
| Extremely reliable      |
| Very secure             |
| No single point failure |
| High fault tolerance    |
| Excellent performance   |

---

# Disadvantages

| Disadvantages          |
| ---------------------- |
| Very expensive         |
| Huge cable requirement |
| Complex setup          |
| Difficult maintenance  |

---

# Cyber Security Note 🔐

Most secure topology.

Reasons:

* Dedicated paths
* Multiple routes
* No central dependency

Military aur banking systems often mesh use karte hain.

---

# Real Use Cases

* Military
* Banking
* Critical infrastructure
* Internet backbone

---

# 05. Hybrid Topology

# What is Hybrid Topology?

2 ya more topologies ka combination.

Example:

* Star + Bus
* Star + Mesh

---

# Why Hybrid?

Different departments different needs rakhte hain.

Hybrid flexibility provide karta hai.

---

# Real Life Analogy

City transport system:

* Bus
* Metro
* Auto
* Train

sab combine hote hain.

---

# Features

* Flexible
* Scalable
* Enterprise-level

---

# Advantages

| Advantages            |
| --------------------- |
| Highly flexible       |
| Easy expansion        |
| Reliable              |
| Optimized performance |

---

# Disadvantages

| Disadvantages             |
| ------------------------- |
| Expensive                 |
| Complex                   |
| Difficult troubleshooting |
| Skilled admins needed     |

---

# Cyber Security Note 🔐

Hybrid networks me:
security policies complex hoti hain.

Different topology sections:
different protections demand karte hain.

---

# Real Use Cases

* Universities
* Enterprises
* Corporate offices

---

# 06. Tree Topology

# What is Tree Topology?

Tree topology:
tree structure jaisa hota hai.

Combination of:

* Bus
* Star

---

# Structure

* Root device
* Branches
* Leaf nodes

---

# Real Life Analogy

Actual tree:

* Trunk
* Branches
* Leaves

---

# Features

* Hierarchical structure
* Organized network
* Large deployments

---

# Advantages

| Advantages              |
| ----------------------- |
| Easy expansion          |
| Structured management   |
| Fault isolation easier  |
| Good for large networks |

---

# Disadvantages

| Disadvantages               |
| --------------------------- |
| Root failure dangerous      |
| Backbone dependency         |
| Complex setup               |
| Expensive large deployments |

---

# Cyber Security Note 🔐

Agar root switch compromise ho:
multiple branches affected ho sakti hain.

Access control important hota hai.

---

# Real Use Cases

* Schools
* Universities
* Enterprises

---

# Topology Comparison Table

| Feature      | Bus  | Ring   | Star   | Mesh      | Hybrid  | Tree   |
| ------------ | ---- | ------ | ------ | --------- | ------- | ------ |
| Cost         | Low  | Medium | Medium | Very High | High    | Medium |
| Installation | Easy | Medium | Easy   | Complex   | Complex | Medium |
| Speed        | Slow | Fast   | Fast   | Very Fast | High    | Medium |
| Reliability  | Low  | Medium | Medium | Very High | High    | Medium |
| Security     | Low  | Medium | Medium | High      | High    | Medium |
| Scalability  | Hard | Hard   | Easy   | Hard      | Easy    | Easy   |

---

# Best Use Cases

| Topology | Best For           |
| -------- | ------------------ |
| Bus      | Small old networks |
| Ring     | Token systems      |
| Star     | Homes & offices    |
| Mesh     | Military           |
| Hybrid   | Enterprises        |
| Tree     | Schools            |

---

# Important Cyber Security Concepts

# Single Point of Failure (SPOF)

Aisa component:
jiske fail hone par pura network fail ho jaye.

Examples:

* Bus cable
* Central switch
* Root node

---

# Redundancy

Backup paths ya systems.

Purpose:
network failure avoid karna.

Mesh topology best redundancy provide karta hai.

---

# Fault Tolerance

Network failure ke baad bhi kaam continue kare.

---

# Scalability

Future me network easily grow ho sake.

Star aur Hybrid scalable hote hain.

---

# Traffic Sniffing

Attacker network traffic monitor karta hai.

Bus topology me easy hota hai.

---

# Segmentation

Network ko sections me divide karna.

Security improve hoti hai.

---

# Real Life Cyber Attack Example

Suppose:
company bus topology use karti hai.

Attacker:

* Network cable tap karta hai
* Passwords capture karta hai
* Sensitive data steal karta hai

Isliye topology security directly affect karti hai.

---

# Which Topology Most Secure hai?

## Most Secure:

✅ Mesh Topology

Reasons:

* Multiple paths
* Dedicated links
* No single failure point

---

## Least Secure:

❌ Bus Topology

Reasons:

* Shared cable
* Traffic visible
* Easy sniffing

---

# Exam Important Points

| Question                     | Answer               |
| ---------------------------- | -------------------- |
| Most common topology?        | Star                 |
| Most secure topology?        | Mesh                 |
| Cheapest topology?           | Bus                  |
| Topology with token passing? | Ring                 |
| Hybrid means?                | Combination topology |
| Tree topology based on?      | Bus + Star           |

---

# Quick Revision

| Topic    | Meaning                |
| -------- | ---------------------- |
| Topology | Network structure      |
| Bus      | Single backbone cable  |
| Ring     | Circular connection    |
| Star     | Central switch         |
| Mesh     | All-to-all connection  |
| Hybrid   | Mixed topology         |
| Tree     | Hierarchical structure |

---

# Final Thought

Cyber Security me:
topology samajhna extremely important hai.

Kyuki:

* Attack paths topology par depend karte hain
* Security controls topology par depend karte hain
* Network failures topology par depend karte hain

## 🔐 Golden Rule

“Strong network design = Strong cyber security.”
