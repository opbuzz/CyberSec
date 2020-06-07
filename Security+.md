
## Domains

Network Security 
* Compliance and operations security
* Threats and vulnerabilities
* Application data and host security
* Access control and identity management 
* Cryptography


1)
TCP/IP

* Route information across networks
* provides an addressing scheme
* Delivers packets from source to destination
* Serves as a network layer protocol
 

TCP

Connection oriented protocol
guarantees delivery through acknowledgement
Is widely used

TCP Flags

Three way handshake

* SYN: Opens a connection
* FIN : Closes a connection
* ACK : Acknowledges a SYN or a FIN.

UDP 

* lightweight connectionless protocol
* does not send ack.

OSI Model 

* Physical - Wires, radios and optics
* Data link -  Data transfers between two nodes
* Network - IP
* Transport - TCP/ UDP
* Session  Exchanges between systems
* Presentation
* Application

!  A Must in the exam OSI model

###IP Addresses
* Dotted quad notation 192.168.1.100
* Range of 0-255: 8 binary 

Must not be reused on internet connected systems
may be reused if on private network


#### IPv6
* IPv6 uses 128 bits compared to 32 for IPv4
* Consists of eight groups of four hexadecimal numbers

#### Domain Name Service (DNS)
* DNS functions over UDP port 53.
* Computer sends IP query to DNS server.
* if no response contacts a different DNS.

use _dig_ command in order to use DNS lookup manually 

* Some content filters alter DNS query results.

#### Network ports

* 16 bit binary number (0 - 65k)
* 0 - 1,023 : well known ports
* 1,024-49,151 : registered ports
* 49,152 - 65535 - dynamic ports

!!!! memorize ports
| Port num | Name | 
|-|
| 21          | File transfer port (FTP)                |
| 22          | Secure Shell (SSH)                      |
| 3389        | Remote Desktop Protocol (RDP)           |
| 137,138,139 | NetBIOS                                 |
| 53          | Domain name System (DNS)                |
| 25          | Simple Mail transfer Protocol (SMTP)    |
| 110         | Post Office Protocol (POP)              |
| 143         | Internet Message Access Protocol (IMAP) |
| 80          | Hypertext Transfer Protocol (HTTP)     |
| 443         | Secure HTTP (HTTPS)                     |


####ICMP

* Ping command - are you there -  ICMP ECHO REQUEST
* Ping reply - Yes I am -  ICMP ECHO REPLY
* Traceroute - checks the entire route between two networks.
* Other ICMP functions :
	* Destination unreachable
	* Redirects
	* Time exceeded
	* Addresses mask requests and replies

### Switches and Routers

* Ethernet jacks are at the other end of network cables connected to switches

### Firewall
* Switch -> router -> firewall
* Stateful Inspection - Tracks open connections
* Rules contents:
	* Source system address
	* Destination system addresses
	* Destination port and protocol
	* Action ( allow _or_ deny)
####DMZ

* Contains systems that must accept direct external connections.
* Isolates those systems due to risk compromise.
* Protects internal network from compromised DMZ systems.

####  Implicit Deny principle
* If the firewall receives traffic not explicitly allowed by a firewall rule, then that traffic must be blocked.
!!! FOR QUIZZ

### WAP - Web application wall

#### Web server

* Load balancing - Several server share the load 
* Functions:
	* SSL certificate management
	* URL filtering
	* Other web application security tasks

###Proxy Server
* Surf the web instead of the user
* Benefits:
	* Anonymization
	* Performance boosting (stores popular websites cash)
	* Content Filtering 
	* 
### Web Security Gateways
* Sits between web users and the internet
* Scan requests coming from users
* Scan responses coming from the internet
* Filter out Potential malicious attacks
#### VPN

* Site to site VPNs - connect remote offices to each other and headquarters
* Remote Access VPNs -  Provide remote access to corporate networks for mobile users

###VPN endpoints
* Firewall 
* Routers
* Servers
* VPN concentrators
#### Tunnels
* IPSec - Network layer VPN protocol, commonly used for site-to-site VPNs but difficult to configure.
* SSL/TLS  - Application layer VPN,  easier to configure. commonly used for remote access VPNs
### Intrusion detection systems
* Types of behavior:
	* SQL Injections
	* Malformed packets
	* Unusual logins
	* Botnet traffic
* Alerts admin
* Require someone to monitor and take appropriate action

### Intrusion Prevention systems
* Signature detection systems
	* Contain databases with patterns of malicious activity
	* alet administrators to traffic matching signatures
	* fail to detect brand- ew attacks
	* Reduce false positive false.
#### Anomaly detection systems
	* Build models of "normal" activity
	* Alert admin to activity not matching the model
	* Detect previously unknown attacks
	* Increase false positive rates

! anomaly detector , behavioural detector , huristicol detector are the same.

#### Protocol Analyzers 

* Troubleshoot network issues
* Investigate security incidents
* Eavesdrop on confidential communications


### Unified threat management (UTM)
* Basic functions
	* Protecting network against attacks
	* Blocking unsolicited traffic
	* Routing traffic to and from the internet
*  Additional
	* VPN connectivity
	* Intrusion detection
	* Intrusion prevention
* URL filtering
* Content inspection
* Malware inspection
* Email and spam filtering
* Very useful for SMB.

####IP address

* Public IP Address- Assigned by a central authority and are routable over the internet
* Private IP Address - Available for everyone but not routable over the internet

ICAN -  distributes large blocks of address by region.

IP addresses scarce - no large blocks available  - only 4.3 billion addresses.

####Private IP address ranges
* 10.0.0.1 - 10.255.255.255
* 172.16.0.1 - 172.31.255.255
* 192.168.0.1 - 192.168.255.255
* Organizations mix public and private addresses

###Network address translation
* Translates private IP addresses to public.
* NAT and Security
	* Hides internal addresses from internet systems
	* Limits direct access to systems
	* Makes it difficult to identify the true origin of traffic
* NAT requires a large pool of public IP addresses.

#### Port Address Translation (PAT)
* Allows multiple systems to share the same public address
* Assigns unique ports to each communication

#### Subnetting
* Subdivides large networks
* Regular Private IP  192.168.1.100
* (Network address) 192.168.|1|.100  (Host address)
*  The '1'  is the subnet number.

#### Subnet masks

Placing '1' in all the places the the network address is '1' and '0' for the host.
Subnet mask: 255.255.255.0

#### Virtual LANs
* Separate systems on a network into logical groups based upon function , regardless of physical location.
* Extends broadcast domain - layer 2
* Configure VLANs
	* Enable VLAN trunking
	* Assign switch ports to VLANs

### Network Access Control

* Intercepts networks traffic coming from known devices and verifies that the system and user are authorized before allowing further communication
* NAC uses 802.1x authentication protocol.
	* Uses RADIUS
	* Request :  Supplicant (user) -> Authenticator -> Authentication Server
	* Response Authentication Server ->  -> Authenticator  -> Supplicant (user)  -> (only if positive) internet or other LAN resources 
* NAC Roles:
	* User and device authentication
	* Role-based access 
		* Authentication server provides additional user information
		* Authenticator places user on a role- appropriate network based upon that information
		* Example -  in a university, professor logon to a staff VLAN while students login to a a student VLAN,
	* Posture checking (health chk)
		* Checks if the device complies with the organization policies before granting access.
		* Antivirus activated
		* Validating current signatures
		* Ensuring proper firewall configuration
		* Verifying presence of security patches
		* Devices that fail this check, ho to into a quarantine VLAN with no access to internal resource,  It is done in order for the devices to obtain necessary requirements in order to move to the regular network.


#### Remote Access 
* Remote shell =Provides CMD access to a remote system (LINUX)
* Remote desktop (RDP) - provides GUI access to a remote system encrypted communication (windows)

* Telenet - old remote access for Linux -  not secure. no encryption.
* SSH - works the same as Telnet only it is encrypted.

#### Telephony security
* VoIP
	* Carries voice communications over data networks
	* Converts voice from analog to digital form
	* Transmits using the internet protocol.
* Security 
	* Encryption - Problem that it might scramble the voice too much
	* Network segmentation

###Defense in depth
* Org should use multiple, overlapping security controls to achieve each of their security objectives.
* Layer 
!!!! Quiz


####Virtualization
* The Hypervisor tricks each guest into thinking it is running on dedicated hardware
* Type 1 Hypervisor - runs on the on top of physical hardware (home computer)
* Type 2 Hypervisor - runs on top of an operating system
* security
	* Isolation
	* Access its own memory and storage
	* VM escape attack 

###Cloud computer 

Delivery computing resources over the internet
Flexibility 
Scale
Agile

* Private cloud
* Public cloud
* Hybrid cloud

!! Quiz- NO cloud model is superior to another

### Public cloud tiers
* SaaS
* PaaS
* IaaS


#### Security responsibilities
C = Customer
V = Vendor
| Name         | Iaas | Paas | SaaS | 
|-|
| Data         | C    | C    | C    | 
| Application  | C    | C    | V    |  
| OS           | C    | V    | V    | 
| Hardware     | V    | V    | V    | 
| Data Center  | V    | V    | V    | 
| Vendor       | V    | V    | V    | 
 
####Firewall rules

* Action : source : Destination : port : protocol
* Goes from top to bottom
* Shadow rules - would never be applied  because it is listed below an allow rule.
* Promiscuous rules
* orphaned rules - allow to decommissioned rules.

#### Router
* Not great at filtering complex rules 
* Filter type: 
	* Restrict network traffic based on source IP address.
	* Restrict network traffic based on destination IP address/ source.
	* Restrict network traffic based on protocol used.

* Firewall vs Router -  firewall are better.
* Firewall - are specific 
!!!  Quizz - type of filtering you can do on a router.

#### Switch Physical Security
* An attacker with physical access would be able to take control of entire network.
* VLAN Pruning - limit the Unnecessary exposure of VLANs by limiting the number of switches where they are trunked, especially for sensitive VLANs
* VLAN trunk Negotiation - Deny the use of automatic VLAN trunk negotiation to limit the effectiveness of VLAN hopping attacks.
* Port Security - Limit the devices that may connect to a network switch port by MAC address
* Static Port Security - Administrators manually  configure valid MAC addresses for each port
* Dynamic port Security- Switches memorizes the first MAC address they see on each port and limit access to that address.


Flooding attacks -

* SYN Floods
* MAC Floods

Flood guard.
Routing Loops
* STP - spanning tree protocol - prevents broadcast storms by implementing loop prevention

Firewall log

####Network Flow Data
* Source and destination systems
* Source and destination ports
* Timestamps
* Amount of data transferred each direction
* Dosen't tell _what_,  But does tell, _who_, _when_, _how much_

###SIEM - log analysis 
* App
* FW
* Server
* Net devices

#### SNMP - simple network management protocol
* any device (Agent) that is on the network
* Agent works on the device.
* Request 
	* network activity
	* other
* Can configure devices
* Can receive information from an agent 

!!!! quiz Version 3.0 is the latest


#### Storage network

* NAS- network attached storage - SImple self contained storage devices that commonly use CIFS and NFS.
* SAN - storage area network.
#### SAN 
* Sans present raw storage.
* Uses fiber channel
* FC over ethernet
* iSCSI - rns the SCSI standard over network connection.

The communication is unencrypted.  
Should be used to a dedicated network.

##Compliance and operations

###Security controls
* Procedures and mechanisms that org puts in place to manage security risks
Defense in Depth - Multiple controls for one objective
* Cathorizing controls:
	* Technical  - Tech in order to achieve security ( FW)
	* Management  - Security of the risk management process itself (Reg risk assessment, security planning)
	* Operational - Human driven process ( Background checks, log review) - Individual)

####Failed control
* False Positive errors - control is triggers when it should not. - reduce 
* False negative errors - control fails to detect a situation that it should.

###Security policy Framework

* Policies 
	* Provide the foundation for a security program
	*  Written carefully over a long period of time
	* Require compliance from all employees
	* Are approved at the highest levels
	* Problems
		* Too specific
		* Right Level
* Standards
	* Provide specific details of security controls
	* Derive their authority from policies
	* Follow a less rigorous approval process
	* Require compliance from all employees.
	* Taken by large from large intl org.
* Guidelines
	* Provide advice for the org   (use of wifi when possible)
	* Not mandatory to follow
* Procedures
	* Outline a step-by-step process for an activity
	* Sometime it is mandatory, 

!!Quiz -  remember which one employees must follow

### Security policy
* Culture of the org
* Industry
* Regulatory environment

####Common policies
* Information security policy
	* Designation of individual responsible for security
	* Description of security role and responsibilities
	* Authority for creation of security standards
	* Authority for incident response
	* Process for policy exceptions and violations
* Privacy policy  - (published)
* Acceptable use policy -( Responsible use policy)
	* Describes how individuals may use information systems
	* Prohibits illegal activity
	* Describes what personal use is permitted

* Least privilege
	* Mandatory vacation 
	* Job rotation

####Risk assessment
Identife and protititzins risk

Therats - 
*risk 
* vulnerabilities - weakness

!!! Quiz - Thereat vector - hacker tools 


* Rank the risk by likelihood and impact
* Qualitative risk assessment
* Quantitative risk assessment


* AV = asset value 
	* Original cost
	* Depreciated cost
	* Replacement cost
* EF - exposure value 
	* How much of the product is lost of total
* SLE - single-loss expectancy
```
SLE = AV * EF
```
* ARO - Annualized Rate of occurrence - The number of times a risk is expected to occur each year
* ALE - Annualized Loss expectancy -  Expected monies lost from a risk in any given year
```
ALE = SLE * ARO
```
* MTTF - Mean time to failure - Avg time a  _non-repairable_ component will last. 
* MTBF - Mean Time between failures - avg time gap between failures of a _repairable_ component
* MTTR - Mean time to repair - Avg time required to return a _repairable_ component to service



!!! Quiz - meme for test

###Risk management strategies
* Avoidance  - change biz practice
* Transfer -  shift risk to another (insurance)
* Acceptance -  Accept risk
* mitigation - reduce likelihood of risk
* Deterrence - Takes action to dissuade a threat from exploiting a vulnerability  (security dogs)

!!!quiz - remember all five

Ensure vendor security policies are at as the org
###Vendor agreements
* SLR - service level request
	* System response time
	* Service availability
	* Data preservation 
* SLA - service level agreement
* MOU - memorandum of understanding
* BPA - business partnership agreement
* ISA - Interconnection security agreement
###Vendor Cycle
* Selection - RFP
* Onboarding - technical, Incident report
* Monitoring - Site visits, audits
* Offboarding - destroys data, 


###Vendor information management 
* Data ownership provisions
* Data share
* Data protection

###Change Management
Ensures that an org follows a standard process for requesting, reviewing, approving, and implementing changes to information systems.

#####Request for change - RFC
* Description of the change
* Expected impact
* Risk assessment
* Rollback plan
* Identity of those involved
* Proposed schedule
* Affected configuration items

* Routine changes may be pre approved

* Baselines - Provides a configuration snapshot
* Versioning - assigns numbers to each version


###Audits and assessments
* Evaluate Security controls
* Report on effectiveness
* Recommend improvements

* Assessment - internal
* Audits- external imposed


Audits should have clearly defined scopes.
* User access reviews
!! Quiz - should ask on access 

####DLP - data loss prevention
Tech solution that search systems and monitor networks for sensitive information that is unsecured and provide the ability to remove it, block transmission or encrypt the stored data.

* Host based DLP
* Network-Based DLP (email)

* Pattern matching  - Credit info, "secret"
* Watermarking - Identifies using tags.

####IR program components
1. Policy and plan documentation
2. Procedures for incident handling
3. Guidelines for communicating externally
4. Structure and staffing model for the team
5. Description of reactions with other group.

* IR Policy
* IR Procedures
	* Notification
	* Escalation
	* Reporting
	* System isolation
	* Forensic analysis
	* Evidence handling
	* 
* communication guidelines
	* Senior exec
	* Legal
	* Public relations
	* Regulatory agencies
	* Law enforcement 

###Building an IR Team
* Management
* infoSec
* Subject matter experts
* Legal
* Public
* HR

###Incident identification
* SIEM


!! Quizz -  first responders needs to contain the damage

####trianging impact  (in the IR procedure)
* Low impact
* Moderate impact 
* High impact

###Incident mitigation
1. Damage potential
2. Evidence preservation
3. Service availability
4. Resource req
5. Expected effectiveness
6. Soulution timeframe

MItigation ends with stability

#### Recovery and reconstitution

* rebuild compromised systems
* Remove malware
* Disable breached accounts
* Restore corrupted or deleted data
* recon
	* Applying security patches
	* updating FW
	* etc. 


!!!Quiz - Hot aisle/ cold aisle approach (servers)

###Fire extinguishers
* Class A - Common combustion (Wood, cloth & trash)
* Class B - Flammable liquids (gasoline & oil)
* Class C - Electrical fires (data centers)
* Class D - Heavy metal fires (industrial applications)
* Class K - Kitchen fires (fats & oils)
!!! quizz-  remember the extinguishers.

Wet Pipes - has water all the time
Dry pipes - would have water only in case of fire

###Elctronmaneing inferferance (EMI)
* Interferes with normal operation of other equipment
* Enables eavesdropping attacks
###Physical security
* Deterrent controls
* Preventive controls
* Detective controls


###BCP

* Define Scope
	* biz activities
	* Systems
	* Controls

### BIA - biz impact assessment
* Identifies and prioritizing risk
* redundancy
* Single point of failure (SPOF)  - a service/ system with no redundancy.

###IT contingency scenario

* Sudden bankruptcy of a key vendor
* Insufficient storage or compute capacity
* Failure of utility service


* Succession planning for staff

* High availability (HA)
* Fault tolerance (FT)   -
	* power supply
	* storage  - 
		* RAID
		* Mirroring - two disks
		* parody - three or more disks
* Load balancing
!!!quizz - RAID is not backup

###Disaster recovery
* Initial response
	* Employees should work only on disaster recovery
	* Disaster communication
* Assessment mode
	* RTO 0 recovery time objectives
	* RPO - recovery point objective

!!! quiz - disaster recovery end when everything's back to the way it was


###Backup media
* Tape Backup
* Disk-to-disk backup
* Cloud backup

* Types
	* Full backup - copy of all data
	* Differential backups - all data modified since full backup
	* Incremental backups -  all data modified since last incremental backup

!!! Quiz-  remember


####Backup strategy
* Grandfather-father-son rotation
	* 4 X son - Daily
	* 4 X dad - weekly
	* 4 X GF - Monthly

### Disaster recovery sites
* Hot sites  - Ready to go sites. (expensive)
* Cold sites - Empty data centers
* Warm sites - Compromise between both , used for short term use.

###DR test types
* Read- through - checklist review.
* Walk-through - table review
* Simulation
* Parallel test
* Full interruption test



##Application data and host security

####App security

* Application hardening
*	Use proper authentication
*	Encrypt sensitive data
*	Validate user input
*	Avoid and remediate known wcpolites

* Configuration
	* Type and scope of encryption
	* Scope of access
	* Security of underlying infrastructure

* SQL injection
* Cross site scripting - Third party website that run under different website
* Cross site request forgery -  CSRF, XSRF and Sea surf-  when surfing multiple site, makes illegitimate request.
	* log off auto


* Unpredictable state - unknown input handling


####Fuzz testing

* Fuzzing - feeds a software many different input in order to activate: 
	* Unpredictable state
	* Unauthorized access
* Source of fuzzing:
	* Developer input
	* Developer script
	* Generation 
	* Mutation  ( real values then changing it)
* Use OWASP Zap prog for fuzzing

####NoSQL

* Uses key and value

####Mobile security
* Strong password
* Remote wiping
* Lock screen
* Mobile device  management  (MDM)

!!! quiz - Granting network access requires configuring both network and host FW

####IDS and IPS
* Intrusion detection systems - Alert admin to suspicious network activity
* Intrusion Prevention systems - Take proactive measures to block suspicious network activity  
* Both can be host based and network based

####Secure data
* Data in rest  - HD, USB stick , cloud
* Data in motion - Data that is sent through the network

####ICS Types
* SCADA - Supervisory control and data acquisition
* DCS - Distributed control systems  (water plants)
* PLC - Programmable logic controllers (( handle I/O in difficult environment)

!!Quiz - Embedded = smart home  , needs network segmentation  works also for mainframes

#### Access control and identity management 
 * Identification  - claim of ID
 * Authentication - prof of ID
* Authorization - Is ID ok for process
!! Quizz -remember

##### ID types
* User names
* Access cards


* something you know
* something you are
* something you have
* somewhere you are
* something you do


###Protocol  PAP
*  Has no encryption  authentication
* CHAP -  has encryption - sends challenge( hash) and gets a response.


* Federation - Share info across org  ( Google account , Facebook account)
* Single Sign on - 

* One way trust
* Two way trust
* Transitive trust
* Non-transitive Trust

RADIUS - Remote access dial in user service
* uses UDP - not reliable
* not encrypted

TACACS - alternative to RADIUS
* TACACS+  -  
	* uses TCP
	* Encrypts transmission

###Kerberos
Ticket-based authentication system that allows users to authenticate to a centralized service and then use tickets to gain access to distributed services

!!! Need to understand

* NTLM authentication - 
	* Old and not in use. 
	* Weak encryption
	* 
* LDAP 

Ports: 

* Port 88 - kerberos
* port 389 - LDAP
* port 636 - Secure LDAP

SAML -  single sign on with web browser 



> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbNTY4NTYyNjkzXX0=
-->