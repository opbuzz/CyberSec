


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
eyJoaXN0b3J5IjpbMTEzNTIzOTU5NiwxMzgxNjQ5NDA1XX0=
-->