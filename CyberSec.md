

#Networks
###OSI Model
* Layer 1: Physical Layer-  . Ethernet, WIFI     (DATA)
* Layer 2: Data Link Layer - ARP, SLIP, ATM.   (DATA)
* Layer 3: Network Layer-  IP, ICMP, IPX..        (DATA)
* Layer 4: Transport Layer - TCP, UDP ,SCTP..   ((SEGMENT))
* Layer 5: Session Layer - NetBIOS, L2TP, PPTP..  (((PACKET)))
* Layer 6: Presentation Layer - MIME, ASN.1 ..  (((((FRAME)))))
* Layer 7: Application Layer - HTTP, FTP, SSH..  ((((((BITS))))))


###Physical Layer (1)

* How a single device interacts with the medium
* Major Roles
	* Establishment and termination of a connection to a medium
	* Resource sharing (such as contention resolution & flow control)
	* Modulation (converting digital data into a physical signal)
* Router a physical but they are considered to be layer 3.

#####Physical Layer Devices

* Network Hub
	* connects multiple networked devices together, sending data received on one port to all other ports.
* Network Adapter
	* connects a device such as a computer to a network
* Modem
	* MOdulates an DEModulates signals to be transmitted through different mediums, such as telephone or cable lines.
 
 Network Typologies - Star, Bus, ring

* Star - They have a single point of failure.
* Ring - If one node breaks, it can disrupt the entire network. (not often used)
* Bus - Only one device can talk a time ,  They have a single point of failure.
* 

###Layer 2: Data Link Layer
* Transfers data between adjacent networks nodes
* Detect errors in the physical Layer.
* Only taverses a single network (I.e. not routed)
* MAC - 6 byte identifier that is hard-coded in most networking cards.
	* First 3 bytes are OUI (Organisational Unique Identifier) , which identifies the manufacturer.
	* can be spoofed

#####Network Switch

* Keep track of which devices are connected to which ports
* Stores it in cam table


####ARP

* Devices on the same network use ARP (Address Resolution Protocol) to determine the MAC address associated with a given IP address.
* One System broadcasts an ARP request to all other systems asking who has a given IP address
* The system with that IP address answers with its MAC address
* The MAC address is stored on each computer.
* ARP probe - checks for duplicates.
* Gratuitous ARP - Sends ARP announcement when they boot or change IP addresses 


###Layer 3: Network Layer

* uses packets of data


####IP Addresses

* IPV4 - address are 32 - bit numbers.
* 192.168.101.42
	* The first three represents the network
	* The rest is the address on that network

####IP Addresses Classes

| Name | Netmask | Network (CIDR) | Host| 
|- |-|-|-|
| Class A (0-127) | 255.0.0.0 (/8)| 8 bits | 24 bits| 
| Class B (128-191) | 255.255.0.0 (/16)| 16 bits | 16 bits|
| Class C (192-223) | 255.255.255.0 (/24)| 24 bits | 8 bits|
| Class D (224-239) | Used for multi cast| - | -|
| Class E (224-239) | Reserved | - | -|

CIDR (Classless Inter-Domain Routing)      

Reserved Addresses
* The first address on any network is reserved as the network identifier
* The last address on any network is reserved as the broadcast address.
* reserved as your local loopback address.
	* 127.0.0.0 - 127.255.255.255 
* reserved for link local addresses (ARIPA)
	* 169.254.0.0 - 169.254.255.255 
* Reserved for use on private (internal) networks.
	* 10.0.0.0 - 10.255.255.255
	* 172.16.0.0 - 172.31.255.255
	* 192.168.0.0 - 192.168.255.255

####Default Gateway

* To communicate with systems on different network that is not on the same Layer 2 network.


DHCP - Dynamic Host configuration protocol  
* D- Discover
* 	O - Offer
* 	R - Request
* 	A - Assign



* Enables a server to automatically assign an IP address to a computer from a defined range of numbers (i.e., a scope) configured for a given network.
* If unavailable , the computer will assign itself a link-local (APIPA) address between 169.254.1.0 - 169.254.254.255.
* 

###Routing protocols
Routers support : static, direct and dynamic routs.
within an organization:
* RIP (Routing Information Protocol)
	* Limited up to 16 hop networks
	* 
* OSRF (open Shortest Path First)
* EIGRP (Enhanced Interior Gateway Routing Protocol)
	* Cicso-proprietary avanced distance-vector protocol
Exterior Gateway:
* BGP -Border Gateway Protocol
 
####Fragmentation

* Not available in IPv6
* Should not occur in properly configured networks

####IDS/IPS Evasion

* Fragmentaition reassmebly timeout attacks
* TTL- based attacks
* Overlapping fragments

####Network Address Translation (NAT)

* Technique for translating an IP address to one or more other IP addresses.
* Commonly used in home networks to allow multiple computers to share same IP address.  (This is called PAT - Port address translation)
* Requires changing IP headers

####ICMP
* Internet control Message protocol
* Used as to diagnostic information
* most familiar uses are for ping.

Traceroute -  tracert on windows.
* Uses TTL of 1, causing the first router in the path to respond with an ICMP Time Exceeded message (which identifies the router)
* Some firewall block this command.

IP setting - ncpa.cpl


####Transport Layer

* TCP - Transport Control Protocol
* UDP - User Datagram Protocol

* ports are used with TCP and UDP to identify unique services on a host

####Port Assignments

| Name| Port  Range| exp|
|-|-|-| -|
| Well-Known | 1-1023 |  Most widely used |
| Registered ports | 1024-49151 | Can be registered |
| Ephemeral (Short time) | 49152-65535 | 


#### Important ports to know

| Name| Port  Range| exp|
|-|-|-| -|
|20-21| FTP | File transfer protocol|
|22 |SSH/SCP| Encrypted Secure Shell|
|23 |Telnet| non-encrypted for remote admin |
|25 |SMTP| Simple Mail Transfer Protocol|
|53 |DNS | Domain Name System |
|80 |HTTP| non-encrypted - web traffic|
|110|POP3 | Post office protocol - download email from mail server| 
|135 |MSRPC|For Windows networking (NEtBios over TCP) and remote procedure| 
|139| NetBios| For Windows networking (NEtBios over TCP) |
|143 |IMAP4 | Internet Message Access Protocol; Access email on mail server|
|443 |HTTPS|  HTTP over SSL|
||445 |SMB/CIFS|  For Windows networking (SMB/CIFS over TCP)
|631 |IPP/CUPS| Internet Printing Protocol - used to send print jobs on all platforms|
|3389| RDP| Remote Desktop Protocol/Terminal Server remote GUI (windows)|
|5800| VNC over HTTP| non-encrypted protocol for remotely control and administer computer over HTTP (typically using Jave based viewer) |
|5900+| VNC Server | non-encrypted protocol for remotely control and administer computer over TCP using a native client|

####TCP control bits

SYN - (Synchronize) Initiates a connection
FIN - (Final) Cleanly terminates a connection
ACK - Acknowledges received data

Establish connection :
* SYN-> SYN-ACK -> ACK

####UDP

* No handshake
* No sequence numbers or acknowledgments
* No congestion avoidance
* No re-transmission
* UDP is "best effort" protocol.

####Layer 5: Session Layer

* Creates and terminates unique connection between application


####Layer 6: Presentation Layer
* Standard way to encode data between layers

####Layer 7: Application
* Responsible for interpreting data to a format meaningful to applications


#### Domain Name system (DNS)
* Operates on UDP port 53.
* Each DNS request has a unique transaction ID so that both ends can keep track of individual requests.

####Domain Name Syntax
* TLD  - .com , .gov , .org etc.  - (up to 63 letters)
* Second-level domain - google, microsoft etc (up to 63 letters)
* Sub-domains -  shop.site , go.site etc (up to 253 together with the rest)
* Only lower case

#####Types of DNS servers

* Authoritative Server 
* Recursive / Caching server
* A single DNS server could serve both purposes (bad practice)


|Type|	|Type id. (decimal)|	|Defining RFC|	|Description|
|-
|A|	|1|	|RFC 1035[1]|	|Address record|
|AAAA|	|28|	|RFC 3596[2]|	|IPv6 address record|
|AFSDB|	|18|	|RFC 1183|	|AFS database record|
|CNAME|	|5|	|RFC 1035[1]|	|Canonical name record|
|MX|	|15|	|RFC 1035[1]and RFC 7505|	|Mail exchange record|
|NS|	|2|	|RFC 1035[1]|	|Name server record|
|PTR|	|12|	|RFC 1035[1]|	|Pointer record|
|SOA|	|6|	|RFC 1035[1]and RFC 2308[9]|	|Start of [a zone of] authority record|
|SRV|	|33|	|RFC 2782|	|Service locator|
|TXT|	|16|	|RFC 1035[1]|	|Text record|

nslookup nameofsite

##### HTTP 
* Safe methods
	* GET
	* HEAD
	* OPTIONS
	* TRACE
* Unsafe methods
	* POST
	* PUT
	* DELETE


###HTTP codes

100 Continue
101 Switching Protocols
102 Processing
####**2×× Success**
**200 OK**
201 Created
202 Accepted
203 Non-authoritative Information
204 No Content
205 Reset Content
**206 Partial Content**
207 Multi-Status
208 Already Reported
226 IM Used
####**3×× Redirection**
**300 Multiple Choices**
**301 Moved Permanently**
**302 Found**
303 See Other
**304 Not Modified**
305 Use Proxy
307 Temporary Redirect
308 Permanent Redirect
#### **4×× Client Error**
**400 Bad Request**
**401 Unauthorized**
**402 Payment Required**
**403 Forbidden**
**404 Not Found**
**405 Method Not Allowed**
406 Not Acceptable
407 Proxy Authentication Required
408 Request Timeout
409 Conflict
410 Gone
411 Length Required
412 Precondition Failed
413 Payload Too Large
414 Request-URI Too Long
415 Unsupported Media Type
416 Requested Range Not Satisfiable
417 Expectation Failed
418 I'm a teapot
421 Misdirected Request
422 Unprocessable Entity
423 Locked
424 Failed Dependency
426 Upgrade Required
428 Precondition Required
429 Too Many Requests
431 Request Header Fields Too Large
444 Connection Closed Without Response
451 Unavailable For Legal Reasons
499 Client Closed Request
####**5×× Server Error**
**500 Internal Server Error**
501 Not Implemented
502 Bad Gateway
503 Service Unavailable
504 Gateway Timeout
505 HTTP Version Not Supported
506 Variant Also Negotiates
507 Insufficient Storage
508 Loop Detected
510 Not Extended
511 Network Authentication Required
599 Network Connect Timeout Error


#Windows

Once a month there are patches

PowerShell
* powershell.exe

Change file attributes
attrib a.txt +h
dir /A:H
|Name|Exp|
|----|---|
|attrib| Change file attributes | 
| dir /A:H| List hidden files|
| tasklist | lists currently running processes|
| tasklist /S/U/P | Access a remote need to provide system /S (system) /U (userName) /P (password)|
|taskkill| terminate a running process

ipconfig - 

netstat [-a] [-b] [-e] [-f] [-n] [-o] [-p protocol] [-r] [-s] [-t] [-x] [-y] [time_interval] [/?]

netstat -run = active network connection
netstat -ano = display all active connections, with the parent process ID and port number

ping = test connectivity between systems, requires that ICMP Echo and Reply packets are permitted across the intermediate networks

tracert  = shows hops between systems

mklink = creates a symbolic link 

Alternative data stream = used to convey the origin of the but could be used to implement malicious code.   use *dir/ r*  to look search for it.

Mandatory Integrity Controls

High - Operating System
Medium - Users
Low - Certain applications, such as IE.

Low cannot change High.


#####File Permissions - DACLs


| Permission | Files | 
|-|-|-|
| Read | read the content | 
| Write | write access | 
| full control | includes ability to modify other's access to files|
| Read & Execute | allows file to run | 
| Modify | allows modification|

Permissions are inheritable 

###User Management
Open the GUI
>**kusrmgr.msr**

using cmd:
> **net user/?  ** (brief help)
> **net help user **(detailed help)
> **net user UserName /add  **(adds a new user)
> **net user UserName  MyPass123 /add  **(adds a new user with a password)
> **net user UserName  * /add  **(adds a new user and prompt for password(hidden))
> **/active:yes   /delete**
> **net localgroups GroupName   ** (list content of groups)
> **net localgroups GroupName  userName  /add** (add user to groups)
> **/del  /add**

net accounts = manage password and login requirements for all accounts.

####Using RUNAS

Does not bypass UAS (User access control)
Example
runas /user:jogn_admin secpol.msc

option (/)
* netonly - credential are for emote access only
* smartcard - credential are supplied from a smart card
* noprofile -  user's profile should not be loaded ; faster but not bug free.
* profile - load the user's profile (defualt)
* 

####Credential Storage
* Stored in Security Accounts Manager (SAM)
* Stores hashes.
* C:\windows\system32\config
* Stores in two formats LANMAN (LM) and NT hashes (knows as NTLM)
* If the system uses LM - need to use more then 14 char password.
* encrypted with a key referred to as the SYSKEY

####Cracking windows passwords

* Tools for extracting hashes :
	* fgdump
	* pwdump
	* Metasploit
* Tools for "brute-force" guessing:
	* John the RIpper
	* HashCat
	* Cain and Abel

###Mimikatz
* Can retrieve clear text credentials from RAM.
* Need to limit the amount of time certain accounts' password are cashed.


####Rights and Security policies

* Audit Policy  - Are not turned on by default
* User Rights
* Security Options  - need to disable Debug program permission

- Edit by typing **secpol.msc**


###Registry

Divided to "Hives" -each containing different classes of data
* HKEY_LOCAL_MACHINE or HKLM 
* HKEY_USERS or HKU - 
	* Specific to each user 
	* Pointer to path inside HKEY_Users, dependent on the logged in user
* HKEY_CURRENT_USER or HKCU 
	* specific to current user
* HKEY_CURRENT_CONFIG or HKCC
	* Configuration data for current hardware profile
	* Pointer to HKLM\System\CurrentControlSet\CurrentContreolSet\Hardware Profiles
* HKEY_CLASSES_ROOT or HKCR
	* Registered applications and file associations

#####Common Registry Value Types
REG_SZ - string
REG_MULTI_SZ- Multiple Strings
REG_DWORD - A number between 0 and 4,294,967,295
REG_BINARY - Binary data

###Networking - SMB
* Server Message Block
* Used for sharing
	* FIles
	* Printers
	* Other Resources


####Net use
* View, connect or disconnect a remote resource  
* Map drive using current credentials
	* net use  driveLetter: \\serverName
* Map drive using different credentials With password  (if no letter selected then typing * would let the system choose)
	* net use  driveLetter:  * \\serverName /user:UserName
* Delete the mapping by drive letter
	* net use drivLetter: /delete
* Delete the mapping by share
	* net use \\serverName\shareName  /delete
* Delete tall mapping
	* net use * /delete

###services.msc



| Type | exp |
|-|-|-|
| Automatic | Starts after boot|
| Manual | starts when required or called |
| Disabled | prevents it from running |
| Automatic (Delayed) | Starts a while after boot (speeds boot time)|


* Can use sc in cmd.
	* sc query start..stop [serviceName] state= inactive..active..all
* show all
	* sc query
* Start a process
	* sc start serviceName
*  query configuration 
	* sc qc serviceName
* Show all process in certain state
	* sc query state= inactive
* Disable/start/auto a service
	* sc config serviceName start= disable


####Command line Interface (CLI)

* tasklist and taskkill (see above)
* Create a new calc process
	* wnuc process call create calc.exe
* To list process via diffrent methods
	* wnuc process where (name = "calc.exe") list brief
	* wnuc process where (name = "calc.exe") list full
	* wnuc process where (name = "calc.exe") get commandline
* Kill Process
	* wnuc process where (name = "calc.exe") delete
* To use on remote 
	* wmic /node:servername process call create calc.exe
* For specific user:
	* wmic /node:someserver /user:UserName /password:"SomePass" process call calc.exe


####Scheduled Applications

* Based on 
	* Specific time - Anti-Virus
	* Event Log event - Someone logs into the system
* GUI - Task Scheduler
* CLI - schtasks
	* schtasks /create
for anti virus
* in cmd - mpcmdrun -scan 


###Firewall



# linux 

* A type of Unix
* Distribution = Readhat/Fedora, Unbutu CentOS, CentOS (similar to Red hat)
* list of avaliable - net \\serverName


#### command

* ls : Copy file
* cd
* pwd : print the cuurtent working
* cp : copy a file
* mv : move or rename  a ifle
* rm : delete file
* mkdir : create
* cat (like type) 
* less - like cat ,one screen
* grep : search for text within a file or STDIN
* file : Identify the file type
* head : display the first 10 lines of the files
* tail  :  the last 10 lines
* tail -F  : display new data as it is appended 
* ps : displays a list of running processes
* lsof: display a list of open files
* ifconfig : display information about your network (IP address)
* ping - pings till stops  (use -c  NUM to limit ping)  
* whoami - Dispaly the current username


###Redirection 
| Action |  Code | 
|-|
| Redirect STDOUT to a file | command > file |
| append STDOUT to a file | command < file |
| Redirect STDERR to a file | command 2> file |
| Redirect STDOUT and STDERR to a file | command > file  2>&1|
| Redirect STDIN from a file | command < file |

* Combined - Command < infile > outfile 2>> errolog

* Backtick ( ` ) - Executes command inside the backticks and use result in the outer command.
*  Double bangs ( !! )  - Use previous executed command.
* Bang & dollar ( !$ )  - Use previous executed command's parameter (last)
* Bang & star ( !* )  - Use previous executed command's parameter (all)
* Caret ( ^ ) - Replace string in previous executed command  
	* mroe filename   <-- mistake
	* ^ro^or 
	* more filename <-- result

### Special Characters
* .  = current directory
* ~ = user's home directory
* ?  - wildcard for only one character
* [n-m - A range form n till m $ ls pic[0-9].jpeg
* ;  =  command separator
* && runs second command if first succeeds
*  ||   logical or for command
* 

####Command Shells

* bash - borune shell the most used

users and groups

/home/[username]/

* highest privileges  root (UID 0)
* SUDO - runs a command as root
* wheel a group that can become Root


#### User Management 

* useradd [username] -  add a new user
* passwd [username] - sets a password  (set on password by typing passwrd)
* groupadd [name[ - to create a new group
* gpasswd -a  [user]  [group] tp add a user to a group
*    
#### /etc/passwd
  
* suser information is stored in /etc/passwd and /etc/shadow
* /etc/passwd   - viable to all users
* /etc/shadow -  only viable to Root

#### Structure 

**Username :  Password : UID : GID : GECOS : gome_dir : shell**

**Username**: It is used when user logs in. It should be between 1 and 32 characters in length.
**Password**: An x character indicates that encrypted password is stored in /etc/shadow file. Please note that you need to use the passwd command to computes the hash of a password typed at the CLI or to store/update the hash of the password in /etc/shadow file.
**User ID (UID)**: Each user must be assigned a user ID (UID). UID 0 (zero) is reserved for root and UIDs 1-99 are reserved for other predefined accounts. Further UID 100-999 are reserved by system for administrative and system accounts/groups.
**Group ID (GID):** The primary group ID (stored in /etc/group file)
**User ID Info:** The comment field. It allow you to add extra information about the users such as user’s full name, phone number etc. This field use by finger command.
**Home directory:** The absolute path to the directory the user will be in when they log in. If this directory does not exists then users directory becomes /
**Command/shell:** The absolute path of a command or shell (/bin/bash). Typically, this is a shell. Please note that it does not have to be a shell.

**/etc/group contains a list of group on the system**

###su and sudo

* sudo - run a single command as root (or any other user)
	* "-i" get a full root shell
	* Need personal password to gain access (not 
* su - fully switch to another user (usally root)
	* "-" option  inherit the user's full environment
	* Specify user name in order to switch to that user,  leave blank to switch to root.
	* Need to provide password for the requited account
	* "-c" option run a command istead of obtaining a shell
	* NOTE on some systems users need to be in wheel.
Type 'exit' to logout .


###Applications and services

* On linux services are called daemons ( DAY mons)
* Application are software started and interacted with the user
	* Typically client software (Firefox etc)
* services are software started by the OS that run in the background 
	* Typically server software (Apache web server etc)

#### Boot Process Run level 
**runlevel**
* A set of services to run on stratup  (They are profiles)
* On a typical system there are six runlevels  (most used 3-5)
* example - runlevel 1 is typically Single User Mode - used for diagnostics

Service management 
* Each daemon contain an init script to manage starting and stopping that service
* Each runlevel directory contains numbered symlinks
	* Number represents the starting order (one service can be depended)
	* S/K  - Start or Kill at this runlevel.
	*

####chkconfig 

view  services
> **- -list [sercicename]     < on | off >**

Enable / Disable services
>  **< sercicename > < on | off >**

Enable / Disable services at particular runlevel
>  **- - level5 < sercicename > < on | off >**


ntsysv  - GUI for services
system configuration tool (Red hat system )
> **sudo yum -y  install system-config-services**


week spot - Init Backdoors
in /etc/rc.d/init.d/

Everything is under the root - including disks, cd-rom etc.

### ownership

* Attributes are : read, write & execute
* Permissions are defined by : user, group , other(referred to as "world" permissions)

| Permission | Files | Directories |
|-|-|-|
| Read | read the content | list contents of directory|
| Write | add, remove, modify content | add, remove, rename files |
| Execute | Execute as program or shell script | access files in the directory (not to list contents)|

Show permission

> **ls -l **
> **drwxr-x---- 1 UserName GroupName   4096 Apr 5 15:02 data**

The first letter :
* (-)  =  Regular file
* (d)  = Directory
* (l)  = symbolic link or other type of special file

The  next each 3 letters are for owner, group and other.
The number indicates the number of links to the files.

chmod - change file permission.
* "u" = user/owner 
* "g" = group
* "o" = other
* "a" = all three together
* "+" / "-"  =  add or remove permission
* "=" - set to a new permission (while deleting current setting)
* "r" = read (octal 4)
* "w" = write (octal 2)
* "x" = execute (octal 1)
> **chomd o-rwx somefile.txt**

If ocatal then first 3 number are owner, group and other
> for -rwxr-x----
> **chomd 750 somefile.txt**



####SUID bit

run a file as its owner

###installing

$./configure
$make
$sudo make istall

Or

$ ./configure && make && make install


rep -Uvh NewApplication-3.2.1.rpm 
**Updating  all software**
yum update
**Specif**
yum update tcpdump
**All excluding**
yum update --exclude tcpdump




remove
rep -e -Uvh NewApplication-3.2.1.rpm 
|Name|Exp|
|----|---|
| /etc | mostly configuration files|
| /etc/passwrd| Password location |
| /etc/shadow | Password location |
| /etc/rc.d/rc.d | contains directory corresponding to each runlevel|
| /etc/rc.d/rcN.d | contains symlinks to init scritps|
| /bin  | contains executable programs (Important system programs)|
| /usr/bin| executable programs (other)|
| sbin | executable programs that non root shouldn't need (often no in $PATH for non-root) |
|/usr/sbin| silmler|
| /lib | library & module files for programs (DLL's in windows)
| /lib/modules | kernel modules|
| /usr | contains files for programs installed on the system|
| /usr/local | Defualt location for software installed from source|
| /var | contains variable data used by programs , such as logs|
| /tmp | temporary files - files stored are wiped automatically |
| /var/tmp | temporary files - files stored are not always wiped automatically |
| /boot | Linux kernel and other information needed for booting|
| /home | user's home directories|
| /root | acoount's home directory|
| /mnt | directories where external drives are mounted|
| /media | directories where external drives are mounted|
| /dev | files that represent hardware devices |
| /proc | files allowing direct access to system & kernel information|


#### Apache



#### Web server

most common:
- Apache
- Microsoft IIS (internet information services)
- Nginx (Engine X)


Thereat 
* LFI & RFI
* SQL Injection (SQLi)
* XSS -


###IT Security foundations : OS

Authentication:
* What you know - Password
* What you have - Smart card / token
* What you are - Biometric, i.e., fingerprint

On client side -
 1. Complexity
 2. List item
 3. Passpharsh


#### Smart card

* contact - must have physical contact to work
* contact less - uses radio to transmit data.

| Smart card | Memory card | 
|--------------------------| 
| Considered as token               | Considered as token|
| Holds and _can_ process information | Holds but _cannot_ process information|

Management of cards needed 

####Biometrics
Uses a unique attribute or behavior of an individual's 
* Behavioral 
	* Gait (Someones walk)
	* Signature
	* Voice
* Physiological 
	* Fingerprint
	* Face
	* Iris
	* Hand

####Fingerprint
* Bifurcation
* Island
* Ridge
* Valley

Problem with common API
Lasts for a life time


####Access control
#####RADIUS -  remote dial-in user service
Centralized authentication service used to authenticate wide range of clients before entering the corporate network

Wireless Remote client -> internet -> network access server -> RADIUS -server > user accounts

wireless client Supplicant -> Access Point Authenticator -> switch -> RADIUS Server -> User Account

uses WPA/WPA2 Enterpirse

####TACACS 
* Terminal Access-Controller Access Control System
* Authentication program used on Unix and Linux systems
* An extension of the RADIUS protocol
* Uses TCP, not UDP

###NTFS

* type of acces granted ,
* Full control modfy and list folder contet


#####NTFS Permissions
* Full control
* Change
* Read and execute
* List folder contents
* Read
* Write
* Special Permissions
#####Share permission
* Full control
* Change
* Read
* No access
The Most restrictive permission will be enforced


Right click on a file properties -> advanced

#####Authentication

* Kerveros - provides security and authentication
* NTLM - authentication for nondomain members


Truth is inherit 

Attributes

Schema - list of attributes for a given object

Containrs - holds objects

Object names- LDAP
* CN - commonName
* OU - organizationalUnitName
* DC - domainComponent


Global catlog - used to locate objects on a network (assign (GUID)
Group type - Security or Distribution

Monitor - RADIUS and TACACS+

Auditing -  in local security policy , needs to be planned at it takes a lot of recourse 
Use time syscrineztion

Weekly log review

#### Isolating the Server

* Resource, Physical, Internet and App isolation
* Separation of rules and privileges  


Remove 

eicar   - downalod virus 


Firewall

* checks packs
* UDP ICMP  - stateless 
####Types of Firewall
* CLass 1 
	* Host based software

* class 2
	* Wirells foruter fiewall
	* ready out of the box
	* for home use
* class
	* Low-end hardware firewall
	* switching and VPN functionaly
* Class 4
	* High-end hardware
* Class 5
	* High end server firewall 

Unifird threeat managemnet 

* UTM provides
* Fireswall
* Intrusion Prevention
* Antivirus
* Data Loss Prevention
* Content filtering
* Protects internal wired network
* Monitors Access points, endpoints and servers
* Usually mangaged through a dashboard

Secure contest management

*  Helps prevent data loss (sending email with sensitve data)
* Analyses potential risks: spyware, spam, and phishing
Can use wireshrk to analyze content of email.

###Network access protection
* Go to server manager


####Layer 2

#####VLNS

* Are part of a separate IP subnetwork.
* A layer 3 switch or router must be used
* When a computer is moved it can stay on same VLAN.
* Security - Restrict access

#### Cryptography Basics


see rfc2828

####Terms

* Trusted third party  - nececcry om a jhubrid crypto system for secure key exchange
* Public key infrastructure
* The story of Bob and Alice

###str of encryption

* Encryption algorithm 
* Len of the key

* 3des - slow 168 bit
* Blowfish
* IDEA -  replaces des (needs licnece)

AES -process entrie block

Main tranformation

* Substitute Bytes
* Shift rows
* Mix columns
* Add round key


BLock cyphr

* chining blcok -
	* ECB 0 same key
	* CBC 0 cypher block chaining  - with add or
	* CfB -
	* OFB

####Public key share- Diffie Hellman

* Alice & Bob agree on a non secret prime number:  P and g where as P > g
* Alice chosses a secret random integer (a)  and calc - Av = g^a
* A  =  MOD (Av,P)
* Bob - A random integer (b) and calc Bv= gb
* Bob - Calc B = MOD(Bv, P)
* Example ( b =4 , Bv = 625 , B = 13)
* Alice - Sa = B^a and SS= MOD(Sa,P)
* Bob calc Sb = A^b and SS = MOD(Sb,P)


####PKI
Uses X.509 certificate from the cerificate authority to provide assurance that a public key belongs to entity within the certificate

* SHA
* 


Socket = IP address and a port address
 
####EMAIL S/MIME

* Certificate form admin
* Dosent work with web-based  platform
	* Hush mail
	* S-Mail
	* Countermail


####Cloud  computing
#####Documents
* ENISA
	* Risk assessment document
	* Assurance framework
* Cloud Security Alliance
	*   Security guidance for critical areas of focus in cloud computing
NIST
* Cloud computing Collaborate site  - NIST Cloud Computing Security Reference Architecture


#####NIST

* Consumer 
* Broker
	* Infra
* Service provider
* Carrier
* Auditor

####Essential Characteristics

* On-demand self service
* Broad network access
* Resource pooling
* Rapid elasticity
* Measured service
* Charged by usage (Not included in NIST)

#####Type of cloud - IaaS
* Utility service and billing model
* Offloading of technology administration
* Dynamic scaling
* Virtualization and multi-tenancy
* Internet-hosted paradigm 
* Structure
	* APIs
	* Core Connectivity & Delivery
	* Abstraction
	* Hardware
	* Facilities

#####Type of cloud - PaaS
* Structure 
	* Integration & Middleware
	* IaaS structure
#####Type of cloud - SASS
* Structure 
	* Presentation mobility,	Presentation Platform
	* APIs
	* Applications
	* Data, Matadata, Content
	* PaaS
####ENISA Guidance -  Risks assessment
 https://www.enisa.europa.eu/publications/cloud-computing-risk-assessment
##### Policy and Organizational Risks
R.1 Lock-in  (High risk)
R.2 Loss of governance (High risk)
R.3 Compliance challenges  (High risk)
R.4 Loss of business reputation due to co-tenant activities 
R.5 Cloud service termination or failure 
R.6 Cloud provider acquisition
R.7 Supply chain failure

##### Technical
R.7   Technical risks 
R.8   Resource exhaustion (under or over provisioning) 
R.9   Isolation failure  (High risk)
R.10 Cloud provider malicious insider - abuse of high privilege roles 
R.11 Management interface compromise (manipulation, availability of infrastructure)  
R.12 Intercepting data in transit  
R.13 Data leakage on up/download, intra-cloud  
R.14 Insecure or ineffective deletion of data  
R.15 Distributed denial of service (DDoS)  
R.16 Economic denial of service (EDOS)  
R.17 Loss of encryption keys  
R.18 Undertaking malicious probes or scans  
R.19 Compromise service engine  
R.20 Conflicts between customer hardening procedures and cloud environment  

##### Legal
R.21 Subpoena and e-discovery   (High risk)
R.22 Risk from changes of jurisdiction   (High risk)
R.23 Data protection risks   (High risk)
R.24 Licensing risks  

##### Other- Risks not specific to the cloud 
R.25 Network breaks 
R.26 Network management (ie, network congestion / mis-connection / non-optimal use)      (High risk)
R.27 Modifying network traffic  (High risk)
R.28 Privilege escalation 
R.29 Social engineering attacks (ie, impersonation) 
R.30 Loss or compromise of operational logs 
R.31 Loss or compromise of security logs (manipulation of forensic investigation) 
R.32 Backups lost, stolen 
R.33 Unauthorized access to premises (including physical access to machines and other facilities)
R.34 Theft of computer equipment 
R.35 Natural disasters 


* Case study -  amazon breaches and failures


###CCM - Cloud Controls Matrix
* Matrix of 133 baseline controls covering all 13 domains of cloud
####Consensus assessments initiative questionnaire - Star system
* Used to check cloud providers compliance with controls.
https://cloudsecurityalliance.org/star/#_registry

####Principles of Governance and risk
* Auditing supply chains
* Board / management structure
* Corporate responsibility
* Transparency and Disclosure
* Exercising control


#####Risk Strategies

* Avoidance
* Reduction
* Transfer
* Acceptance

####Assessment Factors

* Incident Management
* Business Continuity
* Disaster Recovery

####Complying with legal and audit requirements

* Ediscovery - All documents, including electronic files can be preserved and provided as evidence
* Electronic evidence needs to be in a standard format and forensically sound.
* Audit assurance should be extended to the cloud, and auditors need to be cloud aware.
####Check for compliance issues before signing the contract
* What obligations affect this service?
* Who is responsible for compliance?
* Can the service provider demonstrate compliance?
* What controls are required?


####Cloud life cycle

* Create
* Store
* Use
* Share
* Archive
* Destroy


* Information Classification
* Information management policies
* Location and jurisdictional policies
* Authorizations
* Ownership
* Custodianship

####Domain 6
* Interprotabilty - the abilty to move data from cloud platform to antoher/ physical network.
* Have procedure in place to migrate service

####NIST SP800-61 

* What suppory is proveded from service provider
* Cheack fro log data ( what, when, where)
* Foransic - see NIST Cloud Computing Forensic Science Challenges NISTIR 8006

#####Application security
* Secure SDLC
	* Physical security
	* Incomplatability
	* Access to logs
	* Fail-over mechanisms
	* Compliance
* Maturity Models
	* Building security in (BSIMM2)
	* Software Assurance
	* Systems security engineering capability (SSE-CMN)
* Assurance program
	* Executive support, policy
	* Design, text and deploy
	* Security and privacy
	* Configuration and Change
	* Physical security risk
	* Secure coding practices
* Verification 
	* Least privilege
	* Segregation of duties
	* Defense-in-depth
	* Fail-safe
	* Simple design
	* Authorization for all requests
* Construction
	* Automated development
	* Code review
	* Security testing
	* interoperability testing
	* Metrics
* Risks
	* Traditional risks
	* New risks - Governance
	* New risks - technical

####Penetration testing 
* Multi-tenancy
* Inter-VM
* See rest in OWASP


####Verifying identity in the cloud
* Fully integrated
* Integrated identity
* Stand-alone 

#####Access Request in the cloud

* User 
* Policy enforcing point
* Policy decision point (sent through SAML, SWRL, XACML, XRBAC, KaoS)
	* Policy Access Point
	* Policy information point
* Sends info back to the user using the same route
* The user gains access to the resource


#### Implementing virtualization
* Type I Hypervisor - On top of the hardware - VMware, vSphere, Cirtix XenServer, Microsoft Hyper-V
* Type II - On top of the current OS (- VMware Workstation)

#### Hardening Hypervisor -NIST Special Publication 800-125a:
* HY-BF1: Execution Isolation for virutal meachines
* Hy-BF2: Device Emulation & Access Control
* HY-BF3: Execution of Privileged Operations
* HY-BF4: Management of VMs
* HY-BF5: Administration of Hypervisor Host & software

####Secure socket layer

* There is an expectation of trust when using passwords.

#####Security Standards 
* OpenSSL 
	* Heartbleed
	* TIming
	* Denial of service
	* OCSP interception
	* CSS injectionn

####Certificate spec 
* Domain name of the server (common name)
* Public key
* Owner of the certification
* Issuer of the certificate
* Expiration date
* Serial number

All ROOT certificate are self-signed

* A ROOT CA is a top-level certificate authority
* Its authenticity can't ever be revoked by anyone
* If it is destroyed, all its certificates will become invalid
* If it is compromised,  it must be destroyed.

* In SSL, a HASH is used to calculate a small, fixed-length message that can be encrypted using the server's private key to validate the authenticity of a certificate received by a client system.
* The HASH has safegurds build in to prevent duplication or undetected modification of the digest.
* Identical decrypted and original digests prove veracity.

#####Computer Forensics

####Software

* Commercial
	* Encase
	* Forensics Toolkit (FTK)
	* ProDiscover
* Open source and free
	* Autopsy
	* Digital Forensics Framework (DFF)





> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTM4MTY0OTQwNV19
-->