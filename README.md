*This project has been created as part of the 42 curriculum by rida-cos.*

# Description
## Net Practice
This activity is a general practical exercise designed to introduce you to the basics of computer networking. You will learn how to configure IP addresses, connect devices through a router, and understand the role of a gateway within a network.

# Instructions
This project involves solving **networking problems** to make a network function properly.
* First, download the file attached: net_practice.1.7.tgz.
* Then, extract the files in whatever folder you want.
* In this folder, run the index.html file (it is necessary to run using Google Chrome).
* This interface should open in your web browser:

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/48592318-f9ef-4dcb-a11f-d7044671f973" />

As mentioned on the page:
* You can practice if you input your login in the field, using your personal configuration.
* Or you can use the ’evaluation’ tab for a random configuration, suitable for evaluations.

There are 10 levels available for training.

For each level, a non-functioning network diagram appears. At the top of your window, you will see one or multiple goals to achieve: adjust the available configuration so that the network functions properly. There are two buttons you can use:
* [Check again] to verify if your configuration is correct or not.
* [Get my config] to download your configuration whenever you need to. It will be useful to turn in your assignment.

<div align="center">
  <img width="904" height="127" alt="image" src="https://github.com/user-attachments/assets/5e6ad387-32c9-4008-9fe2-e6ca9b69e134" />
</div>

When you have successfully completed a level, a new button will appear. Click on this button to get to the next level.
<div align="center">
  <img width="904" height="127" alt="image" src="https://github.com/user-attachments/assets/2225b7c1-0500-4319-99d1-329d1a8709d3" />
</div>



At the bottom of the page, you will see logs. They can be helpful to understand why
your configuration is wrong, for example, if a gateway is missing or an IP address is
invalid.
<div align="center">
  <img width="276" height="328" alt="image" src="https://github.com/user-attachments/assets/7da395a4-9e24-4794-ba43-5916c051c37c" />
</div>

Here is an example of what kind of exercise you will get:

<div align="center">
  <img width="1916" height="1069" alt="image" src="https://github.com/user-attachments/assets/90b977b4-114c-4c39-8108-992200c226d2" />
</div>

To succeed, modify the unshaded fields until your network configuration is correct.

# What is TCP/IP?

IP and TCP are not the same thing. While IP (internet protocol) is the protocol that drives the internet, the TCP (Transmission Control Protocol) is one of their protocols specialized on transmission of data. TCP/IP specifies how data is exchanged over the internet by providing end-to-end communications that identify how it should be broken into **packets, addressed, transmitted, routed and received at the destination**. TCP/IP requires little central management and is designed to make networks reliable with the ability to recover automatically from the failure of any device on the network.

# What is an IP Address?

IP provides mechanisms that enable different systems to connect to each other to transfer data. Identifying each machine in an IP network is enabled with an IP address. Is like a house in a street that has your own number.

An IP Address is look like this: 192.168.0.1

But don’t worry, you don’t need to memorize all the possibility of IP Address, there is conventions and rules that are commonly used.

<div align="center">
  <img width="1320" height="600" alt="image" src="https://github.com/user-attachments/assets/809a6994-0b61-414c-bf7c-2d3dd060f748" />
</div>

Furthermore there are a few different classes of IP addresses. These classes of IP addresses are a kind of division made according to the amount of bits used to identify the elements of the networks. The address classes are divided into A, B, C, D, and E.

A – The first eight bits (first octet) serve to identify the network and the numbering goes from 1.0.0.0 to 127.0.0.. The other bits serve to identify the host.

B – In class B, the numbering ranges from 128.0.0.0 to 191.255.0.0 In this case, the first two octets identify the network and the other 16 bits determine the host.

C – In class C, the first three octets identify the network. The number ranges from 192.0.0.0 to 223.255.255.0

D – In the case of class D, it is only used for multicast. Class D id addresses have 32 bits.

E – Class E addresses have numbering 1 as the initial four bits. However, class E addresses are not available yet because their use is reserved for testing.

<div align="center">
  <img width="750" height="358" alt="image" src="https://github.com/user-attachments/assets/f4615511-27c3-43c0-806c-8ed85d7b8f40" />
</div>

# What is an Mask?

Now that you know what an IP address is, think about it: how is it possible to know **which** part represents the network and **which** part represents the hosts? That’s exactly where subnet masks come in—they work as a filter for an IP address. By using a subnet mask, devices can analyze an IP address and determine which parts correspond to the network bits and which match the host bits.

The secret here is that the bits of a mask can only consist of contiguous sequences of 1s followed by 0s. For example, a mask like `255.255.255.0` translates to binary as `11111111.11111111.11111111.00000000`. Machines use this layout to quickly calculate the network and host portions using bitwise binary operations.

So, settings the contiguous senquences of 1s, the subnet masks show us the separation of network and host, see the image bellow.

<div align="center">
  <img width="2432" height="1510" alt="image" src="https://github.com/user-attachments/assets/8b6d2fdf-de40-48c2-b198-41454351d229" />
</div>

There is two common types of notation CIDR and Dotted-Decimal

**1. CIDR Notation (Classless Inter-Domain Routing)**

**CIDR notation** is a compact, shorthand method used to represent a subnet mask by appending a forward slash (`/`) and a number to the end of an IP address. This number represents the exact **number of bits** dedicated to the network portion.

- **Example:** `192.168.1.0/24`
- **How it works:** The `/24` prefix indicates that the first 24 bits of the 32-bit IP address are locked for the network ID, leaving the remaining 8 bits for host addresses.

**2. Dotted-Decimal Notation**

This is the traditional way of writing a subnet mask. It mimics the structure of an IP address, consisting of four 8-bit numbers (**octets**) separated by periods. In this notation, the binary values for the network bits are set to `1`, while the host bits are set to `0`.

- **Example:** `255.255.255.0`
- **How it works:** In binary, each `255` represents a full sequence of ones (`11111111`), indicating that those specific octets belong entirely to the network. The `0` translates to `00000000`, marking the host portion.

# How they work together?

**Let’s go to a straightforward example.**

IP:   11000000 . 10101000 . 00000001 . 00001010  (192.168.1.10)
MASK: 11111111 . 11111111 . 11111111 . 10000000  (/24 ou 255.255.255.128)
      |---------- REDE -------------|  |-HOST-|

Look for where the mask ends. In this example, the mask ends at .128, so we can subtract this value from 256, which results in 128. Therefore, there are two subnets in the 192.168.1.0 block, starting at 192.168.1.0 and 192.168.1.128. In this case, the IP 192.168.1.10 belongs to the 192.168.1.0 subnet and is structured as below:

| Função              | IP Decimal       | Binário (Bits de Rede vs Host)            | Regra                      |
|---------------------|------------------|------------------------------------------|----------------------------|
| **Endereço de Rede**| `192.168.1.0`     | `11000000.10101000.00000001.00000000`    | Primeiro IP (Inutilizável) |
| **Primeiro IP Útil**| `192.168.1.1`     | `11000000.10101000.00000001.00000001`    | Padrão para o Gateway      |
| **Último IP Útil**  | `192.168.1.126`   | `11000000.10101000.00000001.01111111`    | Último host disponível     |
| **Broadcast**       | `192.168.1.127`   | `11000000.10101000.00000001.10000000`    | Último IP (Inutilizável)   |

# Resources
