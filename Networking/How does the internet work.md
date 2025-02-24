### 1. Local Area Network (LAN):
- **Definition**: A collection of devices connected in a restricted physical location (building, office, home).
- **Switch**: The primary device used to create a LAN. It enables computers within the same LAN to communicate with each other. The switch learns the destination of packets and forwards them accordingly.
- The switch is the device we use for computers in the same environment to communicate with each other… A local area network is a collection of devices connected together in non physical location, such as a building, office or harm.
### 2. Routers and Connecting to the Internet:
- **Role of the Router**: Enables computers to connect to the internet. Without a router, internet connectivity is impossible. The router acts as a "door" to access the internet.
- **Packet Flow**: To send a packet to the internet, a computer first sends it to the switch, which then forwards it to the router. The router then sends the packet to the internet through a port connected to the Internet Service Provider (ISP).
- The main task of the router is to enable computers to connect to the internet. Without a router it is impossible for us to connect to the internet."

### 3. The Internet as a Network of Networks:
- **Conceptualization:** The internet is a structure that connects millions of LANs worldwide.
- **Routers are Essential**: Numerous routers are distributed globally to connect these LANs, enabling communication between computers in different parts of the world.
- **Simplified Model:** The course uses a simplified model to visualize how packets move across the internet, acknowledging that the actual structure is far more complex.
- You can think of the internet is the structure that connects all the lands all over devout... the internet is the network of networks.

### 4. Packet Movement and Routing:
- **Routing Tables:** Each router maintains a routing table that dictates the optimal path for a packet to reach its destination.
- **Forwarding:** Routers forward packets based on information in their routing tables, selecting the appropriate port to send the packet to.
- **Routing Algorithms**: Special processors within routers use various algorithms to determine the best paths, considering factors like distance, traffic congestion, and available bandwidth.
- **Congestion Control**: Routers can dynamically adjust paths to avoid congested links, even if it means taking a longer route.
- Every router needs to look at its routing table to learn which part it must forwards the packet. In other words, we can easily understand that routing tables need to have information that which part a packet will got.

### 5. Servers and Streaming:
- **Servers:** Powerful computers that handle requests from numerous clients simultaneously. Websites like Udemy use servers to deliver content.
- **Streaming:** Sending video content piece-by-piece, allowing users to watch videos without downloading the entire file first.
- **Load Balancing:** Distributing servers across different locations to prevent a single point of failure and ensure efficient resource utilization.
- Servers do not differ fundamentally from normal computers. However, since the servers will exchange packets with 1000s of normal computers at the same time, servers must be much more powerful computers in terms of hardware compared to normal computers.

### 6. Wide Area Network (WAN) and VPNs:
- **WAN Definition:** A network consisting of a combination of different LANs, often geographically separated.
- **Use Case:** Companies with offices in different locations can use WANs to create a unified network.
- **VPN (Virtual Private Network)**: A cost-effective method for creating a WAN by establishing a secure, private connection over the public internet.
- **Tunneling:** Encapsulating a packet within another packet to protect its contents during transmission over a public network. Analogized to putting a letter in an envelope.
- **Encryption**: Encrypting the original packet before tunneling to further enhance security.
- In a simple manner, you can think of van is a network consisting of a combination of different plants. For example, with the combination of these two lands, we can create a van, or combination of this land, this land, and this lesson, we can create another van.

### 7. Campus Area Network (CAN):
- A network type used generally in university campuses
- A LAN created by connecting switches directly, even if they are not in the same environment

### 8. Internet Service Providers (ISPs):
- **Role**: Responsible for transmitting packets from one location to another, controlling the routers that form the internet's infrastructure.
- **Hierarchy**: ISPs exist at different levels: * Local ISPs: Serve small areas (neighborhoods). * Regional ISPs: Connect cities within a country. Global ISPs: Connect devices in different countries.
- **Point of Presence (POP)**: A local ISP office containing routers and other networking equipment.
- **Google Global Cache (GGC)**: A system used by Google to deliver content faster by storing it on servers closer to users within local ISP networks.
- **Internet Backbone**: Network set up by Global ASB.
- **Internet Exchange Points**: Structures that enable global a space to communicate more efficiently.
- The internet service provider or briefly ISP is responsible for the transmission of packets from one location to another.

### 9. IP address and ISP 
- An **IP address (Internet Protocol address)** is a unique numerical label assigned to each device connected to a network. It helps in identifying devices and enabling communication between them over the internet.
	- to find the IP Address of certain website, server or domain ([Find IP address of a website, domain, or server | Site24x7](https://www.site24x7.com/tools/find-ip-address-of-web-site.html)).
	- to find your own client's IP Address: [What's My IP Address? Networking Tools & More](https://www.whatsmyip.org/)
- **Networking**: The internet is a vast network of devices communicating with each other. Each device needs an IP address so that data can be sent and received correctly. It's like a home address but for computers.
- **ISP (Internet Service Provider)**: The ISP is the company that provides you with internet access (e.g., AT&T, Verizon, Comcast). When you connect to the internet from home:
	- The **ISP assigns an IP address** to your modem/router.
	- This IP address allows your home network to communicate with the internet.
	- Your router then assigns local IP addresses to devices (laptops, phones) within your home.
	- Your ISP connects your home network to the wider internet using fiber optics, cable, DSL, or other technologies.
	- When you request a website (e.g., Google.com), your request is sent through your ISP, which routes it to the correct server.
	- The server responds, and the ISP delivers the webpage back to your device.
	- **home router**:
		- Your ISP gives your **router** a **public IP address** (this is how the internet sees your home network).
		- Inside your home, your router creates a **local network (LAN)**.
		- It assigns each connected device a **private IP address** (e.g., `192.168.1.2`, `192.168.1.3`) using DHCP **(Dynamic Host Configuration Protocol) (server** inside **router** is responsible for assigning **local (private) IP addresses** to devices in home network).
		- These private IPs are only used within your home network.
		- Your router translates all internal requests into a single public IP (the one given by your ISP) using NAT (network address translation) .
		- This way, to the **outside internet**, all your devices seem to share the same public IP.
	- **Example**: You Open Google.com on Your Laptop at Home
		(Your laptop is connected to your home Wi-Fi.)
		1. **Your Laptop Sends a Request**
		    - Your browser wants to load **Google.com**, so it sends a request.
		    - Your laptop has a **private IP address** (e.g., `192.168.1.10`), assigned by your router.
		2. **Router Receives the Request**
		    - Your router is like a **traffic manager** for your home.
		    - It takes your request and **forwards it to the ISP** using its **public IP address** (e.g., `45.67.89.100`).
		    - NAT is responsible for translating between private IP (of each device) and public IP (of the home router) 
		3. **ISP Sends the Request to Google’s Server**
		    - Your ISP has connections to the internet and routes your request to Google's data center.
		    - The request now reaches **Google’s IP address** (e.g., `142.250.190.78`).
		4. **Google’s Server Responds**
		    - Google’s server processes your request and **sends back** the webpage data.
		    - The data travels back through the **same path**:  
		        **Google → ISP → Your Router → Your Laptop.**
		5. **Your Router Directs the Data to Your Laptop**
		    - Your router receives the webpage data and knows it was requested by `192.168.1.10` (your laptop).
		    - It **delivers the webpage** to your browser.
	-  NAT (Network Address Translation) is responsible for translating between private and public IP addresses.
		1. When You Send a Request (Private → Public)
			- Your laptop (IP: 192.168.1.10) wants to access google.com.
			- The request reaches your router, which has a public IP (e.g., 45.67.89.100).
			- The NAT in the router changes the request’s IP:
				1. Before NAT: 192.168.1.10 → google.com
				2. After NAT: 45.67.89.100 → google.com
			- Now, Google sees your public IP (not your private one) and sends the response back.
		2. When Google Responds (Public → Private)
			- Google sends the response to your public IP (45.67.89.100).
			- Your router receives it and checks which device requested it.
			- NAT translates the public IP back to your laptop’s private IP (192.168.1.10).
			- Your laptop gets the response and loads Google!
		NAT keeps track of which device made a request so that responses go to the right place.
- SO we need the IP address for any website to open it but this would be too hard to be memorable so we use **DOMAIN NAME SYSTEM (DNS)**.
## Important Devices
- Switch The primary device to create a LAN.
- Router Enables connection to the Internet.

## Key Takeaways:
- The internet is a complex system built upon a hierarchy of networks, enabled by interconnected networking devices (switches and routers).
- Understanding packet flow and routing is crucial for grasping how the internet works.
- Security is a paramount concern, addressed through technologies like VPNs and encryption.
- ISPs play a vital role in connecting users to the internet and managing the underlying infrastructure

## Questions:
#### 1. What is the primary function of a switch within a local area network (LAN)?
- A switch enables computers within the same LAN to communicate with each other. When a computer sends a packet, the switch learns the destination and forwards the packet only to the intended recipient.
#### 2. Explain the difference between a packet and a frame, and which term is preferred in the course.
- Packets and frames are both terms for the messages generated by computers, but the course prefers the term "packet." A packet is a unit of data transmitted over a network.
#### 3.How does a router facilitate internet connectivity for devices within a LAN?
- A router connects a LAN to the internet, acting as a gateway for devices to access external networks. It enables communication between devices on the LAN and computers on the internet.
#### 4.Describe the role of a routing table in a router's operation.
- A routing table is a special table inside each router, and it helps a router determine the best path for forwarding a packet to its destination. It contains information about which port to use for different destinations.
#### 5. What is congestion control, and how does it affect packet routing decisions?
- Congestion control is a mechanism where routers avoid sending packets over busy network paths, even if they seem the shortest. Routers control the traffic of the links they are connected to; they want to deliver packets as fast as possible.
#### 6. What is the "network of networks," and how does it relate to the internet?
- The "network of networks" is a description of the internet, emphasizing that it's a vast system connecting millions of LANs worldwide. It combines all these networks that allow electronic devices in the world to communicate with each other.
#### 7. Explain the process of streaming a video on Udemy in terms of packet transmission.
- Streaming involves sending a video in small pieces (packets) from the server to the user's computer. This allows the user to start watching the video before the entire file has been downloaded.
#### 8. What are Wide Area Networks (WAN), and how are they different from LANs?
- WANs are networks consisting of a combination of different LANs, often spread across different geographical locations. While LANs connect devices in a restricted area, WANs connect LANs over a wider area.
#### 9. What is a VPN, and how does it enhance the security of data transmitted over the internet?
- A VPN (Virtual Private Network) creates a secure, encrypted connection (tunnel) over the internet, protecting data from interception. It encrypts packets, making it difficult for unauthorized parties to access the information.
#### 10. Explain the role of Internet Service Providers (ISPs) in enabling internet connectivity.
- ISPs (Internet Service Providers) are companies responsible for transmitting packets from one location to another. ISPs control routers and their infrastructure allows you to connect to the internet.

### Essay Questions

1. Compare and contrast the roles of switches and routers in network communication. Provide specific examples of when each device is essential.

2. Discuss the significance of routing tables in the functioning of the internet. Explain how routing tables are created and updated, and how they contribute to efficient data transmission.

3. Describe the process of establishing a Wide Area Network (WAN) for a company with offices in different locations. Include the different approaches to setting up a WAN and the security considerations involved.

4. Explain the concept of tunneling in the context of VPNs. How does tunneling enhance the security of data transmitted over a public network?

5. Discuss the hierarchical structure of Internet Service Providers (ISPs), including the roles of local, regional, and global ISPs. Provide examples of scenarios where each type of ISP is involved in facilitating internet communication.

### Glossary of Key Terms
- **LAN (Local Area Network):** A collection of devices connected together in a restricted physical location, such as a building, office, or home.
- **Switch**: A networking device used to connect computers in the same LAN, enabling communication between them.
- **Packet**: A unit of data transmitted over a network.
- **Router:** A networking device that connects different networks (including LANs) together and enables devices to access the internet.
- **Routing Table**: A table stored in a router that contains information about the best path to forward packets to their destination.
- **Congestion Control**: Mechanisms used by routers to avoid sending packets over busy network paths, ensuring efficient data delivery.
- **WAN (Wide Area Network)**: A network consisting of a combination of different LANs, often spread across different geographical locations.
- **VPN (Virtual Private Network)**: A secure, encrypted connection (tunnel) over the internet, protecting data from interception.
- **Tunneling**: Encapsulating a packet within another packet to create a secure channel for data transmission.
- **ISP (Internet Service Provider)**: A company that provides internet access to homes and businesses.
- **POP (Point of Presence)**: A location containing routers, switches, and other devices that enable an ISP to provide internet services.
- **Internet backbone**: The network that global ASB set up with each other.
- **IXP (Internet Exchange Point)**: Structures in order for the internet backbone to work synchronously for global a space to communicate with each other more efficiently.
- **Streaming:** Sending data (like video or audio) in small pieces (packets) over a network, allowing users to consume the content before the entire file has been downloaded.
- **Private WAN**: A WAN created when you request a line from the ISP and give a special money for this line does. The ISP gives you a private line that only your company can use.
- **Public WAN**: A WAN created when using a VPN and communicating through public internet networks.
- **CAN (Campus Area Network)**: When two switches can be connected to each other to create a LAN when their distance is very short, usually used on university campuses.
- **Internet**: Is the network of networks and is the largest Wide Area Network in the world.


## Web Development Fundamentals: A Study Guide
#### In the client-server model, what is the primary role of the "client"?
- The client is the computer that sits in front of you, running web browser software. Its primary role is to display web pages and make requests to the server for information.
#### What are the two different things that the word "server" can mean in web development?
- The word "server" can refer to both the physical hardware (the computer that runs the website) and the software that executes commands to send files and make the website accessible.
#### What is "forking" in the context of CodePen, and why is it useful for learning web development?
- Forking is the process of copying someone else's code on CodePen to create a new, independent version that you can modify. It's useful for learning as it allows you to experiment with existing code and see the effects of your changes.
#### What were the original intended purposes of the ".com," ".net," and ".org" domain extensions?
Originally, ".com" was intended for commercial websites, ".net" for network providers (ISPs), and ".org" for non-profit organizations.
#### Besides country codes, what are the types of domain extensions that are still strictly regulated and who are they regulated for?
".gov" is strictly for the US federal government, ".edu" is strictly for higher education in the United States, and ".mil" is used by the US military.
#### Why is it important to use consistent file and folder naming conventions in web development?
- Consistent naming conventions, using either hyphens or underscores consistently, reduce confusion and errors while coding.
#### Explain the role of an ISP in connecting a home computer to the Internet and what an IP address is.
- An ISP (Internet Service Provider) provides the physical connection to the Internet and assigns an IP address (Internet Protocol address) to the modem or router in a home, enabling devices to communicate online. An IP address functions as a unique return address for your computer on the internet.
#### What is the main purpose of folders on a computer, and how does this relate to web project file organization?
- Folders hold files and other folders to organize and group related content. This helps to keep web projects structured and manageable.
#### What is the purpose of file extensions, and why are they important in web development? Give three examples of web development file extensions.
File extensions are the three- or four-letter suffixes after a dot in a filename that indicate the file type (e.g., .html, .css, .js). They are important because they tell the computer which program to use to open the file.
#### Explain the role of JavaScript, and how JavaScript got its name.
 - JavaScript is a programming language that makes web pages interactive, controlling things like animations, color changes, and calculations. It was named "JavaScript" because Java was a popular programming language when JavaScript was created, in an attempt to capitalize on Java's popularity.

#### Explain the client-server model in detail, including the roles of clients, servers (both hardware and software), and the communication process between them. Provide examples of how this model functions in web development.
- In the client-server model, a client (typically a web browser on a user's computer) requests resources from a server, and the server responds by providing those resources.
- Client: The client is the computer that sits in front of you and runs web browser software such as Chrome or Firefox. The client initiates communication by requesting web pages or resources from a server.
- Server: The term "server" refers to two different things: hardware and software.
- The hardware server is the actual physical computer that runs programs that make a website function.
- The software server executes commands to send files out so that a website can be seen. Apache is a commonly used software server.
- Communication Process: A web browser opens and an address is typed in. That address goes over the Internet to the server. The server receives that request and sends the requested web page back to the client.
#### Discuss the importance of domain names in web development, including the different types of domain extensions, factors to consider when selecting a domain name, and the process of registering and connecting a domain name to web hosting.
- Domain Name Extensions: The suffix at the end of a domain name (e.g., .com) is called the top-level domain.
- Selecting a Domain Name: When selecting a domain name, make sure that it's easy to spell and remember. It is recommended to start with registering your own name. 
- Registering and Connecting to Web Hosting: A domain name can be purchased at the same time you are signing up for web hosting. If you register a domain name separately from web hosting, you'll have to make the two "talk to each other". This connection is made through the Domain Name System (DNS), which translates the name to an IP address. This process can take 24-48 hours.
#### Describe the process of creating a local area network and discuss how it can connect to the internet using routers. Be sure to explain the role of IP addresses and ISPs in your answer.
- A local area network (LAN) is a collection of devices connected in a restricted physical location like a building or home.
- Creating a LAN: LANs are created using a switch device. Computers connect to the switch via LAN ports using cables15....
- Connecting to the Internet: A router enables computers to connect to the internet. The router connects to an Internet Service Provider (ISP).
- IP Addresses: The Internet Service Provider (ISP) provides a cable that brings internet connectivity for a certain fee.
- ISPs: Internet service providers (ISPs) are responsible for the transmission of packets from one location to another. Without an ISP, you cannot connect to the internet.

#### Detail the typical folder structure used in web development projects, explaining the purpose of each folder (e.g., CSS, img, JS) and the types of files that are placed in them. Explain why file organization is important.
- A typical web project has a standard folder structure.
- One main folder for the website.
- A CSS folder for CSS files.
- An img folder for image files. Image file types have to be JPG, GIF, or PNG.
- A JS folder for JavaScript files.
- HTML files go inside the main folder.
- Importance: Using lowercase letters for consistency and avoiding spaces or funny characters in file names
#### Explain how web browsers interpret HTML, CSS, and JavaScript to render a website. What is the role of each language in creating interactive and visually appealing web pages?
- Web browsers interpret HTML, CSS, and JavaScript to render a website.
- HTML: HTML (HyperText Markup Language) identifies the parts of a webpage such as headers, footers, paragraphs, lists, and headings. HTML conveys the structure of a document through tags.
- CSS: CSS (Cascading Style Sheets) dictates how the page looks. It controls colors, fonts, and layouts.
- JavaScript: JavaScript adds interactivity and dynamic behavior to a web page. JavaScript can change the color or position of an element.

### Glossary of Key Terms
- **Client**: In the client-server model, the computer or device running a web browser that requests resources from a server.
- **Server (Hardware)**: The physical computer that hosts a website and runs the software necessary to make it accessible.
- **Server (Software)**: The software that executes commands to send files and make a website visible to clients.
- **CodePen**: An online code editor and social community for building and sharing HTML, CSS, and JavaScript code snippets.
- **Forking**: The process of creating a copy of someone else's code on CodePen that you can modify independently.
- **Domain Name**: The unique address of a website on the Internet (e.g., example.com).
- **.com:** A top-level domain (TLD) originally intended for commercial websites.
- **.net**: A top-level domain (TLD) originally intended for network providers (ISPs).
- **.org**: A top-level domain (TLD) originally intended for non-profit organizations.
- **.gov**: A top-level domain (TLD) strictly for the US federal government.
- **.edu**: A top-level domain (TLD) strictly for higher education institutions in the United States.
- **.mil**: A top-level domain (TLD) used by the US military.
- **File Extension**: A suffix at the end of a filename (e.g., .html, .css, .js) that indicates the file type.
- **Local Area Network (LAN)**: A network connecting devices in a limited physical area, such as a home or office.
- **Internet Service Provider (ISP)**: A company that provides Internet access to homes and businesses (e.g., Comcast, Verizon).
- **IP Address**: A unique numerical identifier assigned to each device connected to the Internet, allowing them to communicate.
- **Router**: A networking device that forwards data packets between computer networks.
- **Files**: Basic units of storage on a computer, containing data such as documents, images, or code.
- **Folders**: Containers used to organize files and other folders on a computer.
- **HTML**: (HyperText Markup Language) The standard markup language for creating web pages, defining the structure and content.
- **CSS**: (Cascading Style Sheets) A style sheet language used to control the presentation and formatting of HTML elements.
- **JavaScript**: A programming language used to add interactivity and dynamic behavior to web pages.
- **Web Hosting:** The service of providing storage space and access for websites on a server.