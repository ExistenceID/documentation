# Existence ID Technology Overview

## What does Existence ID Deliver?

Existence ID delivers two distinct product lines.


### For end users.

*   A free and unencumbered application (versioned for both mobile and desktop environments) that provides structured private storage for government-issued and other document types that can be used to establish a proof of identity when dealing with third parties.
*   A premium product line that augments fundamental document storage to provide a 'Drop-Box' style environment as a highly secure repository for a lifetime of personal records and memorabilia.  


### For businesses and third-party developers.

A set of documentation and example code to facilitate the integration, giving Existence ID users seamless, authenticated access to all participating services. 


## Fundamental requirements

*   The interface prioritises simplicity and ease of use. 
*   Internally, the application is optimised for the storage and organisation of identity-related information.
*   Data cannot be intercepted or in any way copied or disrupted, either in transit, or while in storage on the network. 
*   The identity owner has exclusive access to their stored data through the application interface. Data can never be requested from any other path.
*   No data or identifying information is to be recoverable from network storage by any party other than the identity owner. This includes the provider, Existence ID. 
*   Data sharing by the identity owner is exclusively at the owner's discretion. This sharing is selective and very granular, down to individual fields of information. The intention is to prevent the sharing of any data not strictly required for the specific scenario. For example, access to a licensed venue only requires verification of age, while a job application will require much more information.
*   Third party integration ensures instant authenticated access for Existence ID Identity Capsule owners. Once an Existence ID user has established their credentials with a provider, all subsequent visits will be frictionless, removing the need for usernames and passwords.


# Technology selection and discussion


### Where we <span style="text-decoration:underline;">are not</span> using blockchain.

_Existence ID is not using blockchain technologies for data storage. The following discussion explains why._

Data storage is central to the Existence ID project. Blockchain technology is often proposed as a way of decentralising data storage and forms the basis of a number of identity projects in proposal stage or currently under development. Our position is that blockchain systems, such as the Bitcoin network, have some serious limitations that make them problematic for general data storage applications. Blockchains have limitations on the amount of data that they can actually store and so when we talk about 'putting data on the blockchain', we really mean something quite different; the data will not be stored 'on' the blockchain, it will be stored elsewhere, most commonly in conventional, network-connected database systems, and hence vulnerable to attack. 

The most common contribution that a blockchain can make here is by notarising the state of the associated data. A suitable hash function is run against the content and the resulting hash is recorded in the OP_RETURN field (currently 80 Bytes in the case of bitcoin). As the transaction is recorded with a date-time stamp, we have a point in time with which to compare future hashes of the corresponding data. Any change to the data whatsoever will result in a different hash value, indicating that the stored data has been tampered. This tamper proofing method clearly does nothing to actually protect the data, it just tells us that the data is no longer trustable. 

Conventionally stored data can of course be protected through encryption involving the creation and management of cryptographic keys, (often using public key infrastructure). Although such approaches are considered best practice, experience demonstrates how even the most hardened of systems can be penetrated. Blockchain transactions can be used to provide the binding between a public key and an owner, thus removing the certificate authority from the picture. For more information. See the section, [Blockchain-based PKI](https://en.wikipedia.org/wiki/Public_key_infrastructure) at Wikipedia.

While we can see that blockchain technology can contribute in some ways to the integrity of conventionally stored data sets, other properties of blockchain networks need to be considered. If the hybrid model described above is adopted, then the most problematic factor beyond data integrity becomes write speed, ie, having created a record in the database, the notarisation of the data state and creation of a key pair set will be dependent upon the block speed of the chosen network, which in the case of bitcoin is approximately ten minutes. Not only is this slow, it is indeterminate. Further, if the data is critical, then the number of confirmations becomes a factor which could lead to effective write times of hours in some cases. While this may be acceptable for some specific types of applications, it certainly doesn't provide a generalised data storage solution. This will explain why, despite the hype, there are still no blockchain-database hybrid solutions in practical, widespread use today.


### Where we <span style="text-decoration:underline;">are</span> using blockchain.

Having established that the storage requirement is not well served by blockchain, this technology is still important to the project. Unique identities must be actually unique, unforgeable, and assertable by the identity holder. These are characteristics that are well supported by blockchains. When users are interacting with other parties over the broader internet, they will be able to represent their identity consistently through sharing public keys and asserting control of addresses. When sharing limited and specific information, evidence of the actual event will be notarised providing permanent proof of what was provided and when. These and other blockchain operations will be extremely important in a wide range of use cases around identity that are not time-critical.


### Peer-to-peer networks and data storage

All user data will be stored on an encrypted, autonomous peer-to-peer network. At present, the two most promising projects capable of fulfilling this requirement are The [SAFE Network](https://maidsafe.net/#safePrimer) and [IPFS](https://ipfs.io/). While IPFS is currently operational in working beta, the scope of SAFE Network, (still in alpha), is far more ambitious and involves a number of features consistent with the goals of this project. In fact SAFE Network directly supports many of the requirements listed above that relate to network functionality. The remainder of this overview assumes the SAFE Network when referring to any functions across the the network.


#### The SAFE Network

The SAFE Network was conceived at the outset as a data store to ensure that individuals and companies could keep their own information private, safe and secure and could, if they chose, share portions of that information with other individuals, groups or the general public. Detailed information about the SAFE Network can be found [here](https://safenetwork.org/), [here](https://maidsafe.net/#safePrimer) and [here](https://safenetforum.org). Briefly, all data being stored by a SAFE Network user is fragmented and encrypted before being spread in replicated form across the hard drives of a randomly selected subset of the other participating users on the network. This reduces the attack surface for data from the numerous locations it is currently stored at on vulnerable, centralised systems to just one point; the user's device. While the user remains potentially vulnerable, as all users can be, a successful exploit will only yield one single user's data at a time, vastly reducing the incentives and rewards for attackers. Further to this secure mode of data management, SAFE Network promises to be extremely fast, endlessly scaleable and incorporates a native, embedded currency known as SafeCoin, which, beyond its primary function of underpinning the economy of the network, can be used to both reward and incentivise users of Existence ID's Identity Capsule.


#### The coding environment

The SAFE Network is being developed in a system-level language known as [Rust](https://www.rust-lang.org). Rust is a modern, compiled language with some very important properties that make it impossible to access unsafe memory at run-time. Rust was chosen for this project because experienced coders can produce very robust, efficient code. We also look forward to making code contributions to the open-source [SAFE Network](https://github.com/maidsafe) project, and this will be more likely if we are coding in the same language as the project.


<!-- GD2md-html version 1.0β11 -->

