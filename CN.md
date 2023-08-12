# <p align="center"> Unit 1 </p>

## Basics

**Computer Network:**

A computer network is like a digital community where computers and devices are connected, allowing them to communicate and share resources. Think of it as a virtual neighborhood where devices like computers, smartphones, and printers can talk to each other. Networks have some key features:

- **Communication Speed:** Networks allow devices to exchange information quickly, ranging from local networks in your home to global networks like the internet. Faster communication speed means quicker data transfer.

- **File Sharing:** Networks enable devices to share files and data. This is useful for collaborative work, sharing documents, or sending pictures between devices.

- **Security:** Networks need security measures to protect data from unauthorized access. Just like locking your front door, networks use firewalls and encryption to keep your data safe.

- **Scalability:** Networks can grow to include more devices as needed. Whether you're connecting a few computers at home or building a large corporate network, scalability allows for expansion.

- **Reliability:** Networks strive to stay operational without disruptions. Reliable networks ensure that devices can consistently communicate and access resources.

**Components of a Computer Network:**

- **Network Interface Cards (NICs):** These are like the passports of devices to enter the network. NICs are hardware components that allow devices to physically connect to the network, enabling communication.

- **Hubs:** Imagine a hub as a central meeting place where devices connect. However, hubs are quite basic and tend to send data to all devices connected to them, which can lead to inefficiencies.

- **Switches:** Switches are like smart hubs. They only send data to the device it's intended for, making communication more efficient. It's like sending a private message to a specific person in a room full of people.

- **Router:** Routers are like postal workers of the network. They direct data between different networks. They decide the best path for data to travel so it reaches its intended destination, even if it's across the globe.

- **Modem:** If the router is like a postal worker, the modem is like the translator between the digital world and the analog world. It converts data from your devices into a form that can be transmitted over the internet (and vice versa).


**Internet:**

The internet is a vast global network of interconnected computers and servers. It enables people to access and share information, communicate, and use various online services through websites and applications.


**World Wide Web:**

The World Wide Web (WWW) is a collection of web pages and resources that are accessible over the internet. It's like a library of information that you can access from anywhere in the world. The WWW is just one of many services that the internet provides.

**CRC:**

CRC stands for Cyclic Redundancy Check. It is a method of error detection in data transmission. It is used to detect accidental changes to raw data. It's a hash function that detects accidental changes to raw computer data commonly used in digital telecommunications networks and storage devices such as hard disk drives.



## TCP/IP Model

The TCP/IP model, where TCP stands for Transmission Control Protocol and IP stands for Internet Protocol, is a network model designed to facilitate communication across diverse computer systems. It's a practical framework tailored to meet the original design of the Internet. TCP/IP comprises two primary protocols and encompasses numerous sub-protocols across four layers.

<img src="2023-08-12-12-08-04.png" alt="TCP/IP Model" width=50%/>

**Application Layer:**

The Application layer protocols serve applications on computers, acting as an interface between software and the network. It's the layer where users interact with the network. It's responsible for identifying and establishing the availability of intended communication partners and determining resource availability. Furthermore, it also synchronizes communication and establishes privacy and security boundaries. Some protocols used in this layer are:

- **HTTP:** Hypertext Transfer Protocol is used for transmitting data between clients (like web browsers) and servers, forming the basis for web communication.
- **FTP:** File Transfer Protocol ensures secure data exchange between devices, often used in large organizations and institutions.
- **SMTP:** Simple Mail Transfer Protocol standardizes email transmission on the Internet, facilitating communication between servers for sending messages.
- **DNS:** Domain Name Server maps host names to numerical addresses, crucial for Internet functionality.

**Transport Layer:**

This layer maintains communication between sender and receiver. At the Transport layer, data is divided into smaller units called segments.  It employs either TCP or UDP. TCP supporting segmentation for large data and UDP being more straightforward for smaller data. 

- **TCP:** Transmission Control Protocol breaks down large messages into smaller segments with headers for efficient delivery.
- **UDP:** User Datagram Protocol is used for simpler, smaller data transfers.

There's also a third protocol called SCTP, which is less common.

- **SCTP:** Stream Control Transmission Protocol offers reliable, message-oriented communication. It divides messages into chunks, providing error-checking, reordering, and multiplexing for enhanced data transfer in a more versatile manner than TCP.

**Network Layer:**

This layer establishes connections between source and destination computers, with routers helping determine the best path for each packet. It's responsible for logical addressing and routing.

- **Logical Addressing:** IP addresses are assigned to segments to ensure proper routing across networks.
- **Routing:** Determines the path for packets to reach their destination, not necessary within the same network.

**Data Link Layer:**

This layer is responsible for the physical transmission of data. It's responsible for the node-to-node delivery of messages. It's also responsible for error detection and correction. It's divided into two sublayers:

- **Logical Link Control (LLC):** This sublayer is responsible for error checking and flow control.
- **Media Access Control (MAC):** This sublayer is responsible for controlling how devices in a network gain access to a medium and permission to transmit data.

**Physical Layer:**

This layer physically carries bits within frames across links. It's the lowest layer in TCP/IP, with communication occurring via transmission media like cables or airwaves. It's responsible for the physical connection between devices. Likewise, it also defines the electrical and physical specifications for devices. It's the layer where data is converted into binary bits and transmitted over the network.


The Data Link and Physical layers are often combined into a single layer in the TCP/IP model as the Link layer or Network Interface layer/ Network Access layer.

Hence, the TCP/IP model has four layers:

![](2023-08-12-12-12-58.png)



## OSI Model

The OSI Reference Model, developed by the International Standards Organization (ISO), is a structured framework for understanding how different systems communicate. It comprises seven layers, each with specific responsibilities, enabling seamless communication across networks.

<img src="2023-08-12-12-19-20.png" alt="OSI Model" width=50%>

**1. Physical Layer:**

The bottom layer focuses on transmitting raw data bits across the network. It encompasses transmission media like cables and wireless signals, ensuring reliable propagation of binary data (0s and 1s). It's the layer where data is converted into binary bits and transmitted over the network. Furthermore, it's also responsible for defining the electrical and physical specifications for devices.

**2. Data-Link Layer:**

The second layer ensures error-free communication over physical links. It forms frames from raw data, handles error detection and correction, manages flow control, and decides which device controls the shared communication channel. 

**3. Network Layer:**

Layer three facilitates routing across interconnected networks. Routers and software work here to determine the optimal path for data, addressing, and delivering packets between devices, even when multiple networks are involved. It also handles congestion control to prevent network overload i.e. in situations where there's too much data to handle.

**4. Transport Layer:**

The fourth layer ensures end-to-end data integrity. It segments and reassembles messages, ensures reliable data transfer, establishes flow control, and handles error recovery by retransmitting damaged segments. It also manages data congestion to prevent network overload.

**5. Session Layer:**

This layer establishes and maintains communication channels between devices. It handles session initiation, maintenance, and termination, along with data checkpointing for resuming interrupted transfers. It also manages security and authentication. This layer is responsible for establishing, managing, and terminating connections between applications.

**6. Presentation Layer:**

Layer six prepares data for transmission. It encodes, encrypts, compresses, and translates data formats, ensuring proper representation for transmission between devices. It also handles data decryption and decompression at the receiving end.

**7. Application Layer:**

The topmost layer provides access to network services. It manages communication between applications and users, using protocols like HTTP, FTP, POP, SMTP, and DNS to deliver meaningful data and control the sequence of activities within applications. It's the layer where users interact with the network.

In summary, the OSI Reference Model is a structured representation of how communication occurs in a network. It encompasses seven layers, each with its unique role, working together to enable efficient, error-free, and meaningful communication between devices and applications.