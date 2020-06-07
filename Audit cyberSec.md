
#### CIA
Informationisbeuteful.com
atom.smaher.org
digitalattackmap.com
Confidentiality - PID - only atugorized access  using Autentication - access control

integrity - protacting data from unauthorized modification
Availability -days is available when needed
Non-repudiation - added
assets -
* Tangible  - Physical
* Intangible - non physical = IP, trade secrets etc.

#####Risk
Risk  =  threats X vulnerabilities

>If threat is zero _or_ vulnerabilities is zero then there is no risk

####Threat (who)
* Anything that can do one or more of the following to assets :
	* Exploit a vulnerability Intentionally or accidentally  
	* Obtain
	* Damage
	* Destroy

####Vulnerability  (what)
* Security flaw in a system that can be exploited by threats to gain unauthorized access to an asset

Principle of least privilege

* People, network, policies 
#### Social engineering 
* Dumpster driving
* Shoulder surfing 
* Phishing / Spearphising

#####Attack Surface
* Know / unknown / potential vulnerabilities across : 
	* Software (common)
		* Application
		* Services
		* Excusables
		* Webpages
	* Hardware
		* Most cases needed physical access
	* Network
		* Protocols
		* Channels
		* Ports
		* Devices
		* Application
		* Interfaces
	* Users
		* Weakest lin\
The goal is to lower the amount of attack surfaces 

Atatacks:

* Passive -  monitoring 
* Active

buffer overfalw

DEP (windows) - Data execution prevention 


Worms can spread by itself
Trojen - backdoor

Spyware - track activity.


webbrowsing 

Security zone - spesific website settings
ActivX - IE browser only.


Access Point

* baste station
* Cabled to network with Ethernet
* Has SSID (service set identifier) or name
* BSSID is the MAC address of the Access Point
* Infrastructure mode: stations communicate with AP

* WEP- not safe - shared a key
*WPA-PSK - Secure - uses Temporal Key Integrity Protocol (TKIP)
* WPA2 - Best - based on IEEE 802.11i standard (AES)
* 
To make router invisable - turn of SSID (name of device)


Ci[her text - 

Symetric - single shared key : DES,#des, and ARS
Asymmetric - Public and private
* Encrypt - Public key + text = cipher text
* de-crypt - Private key + cipher text

####Public Key infrastructure (PKI)
* Third party Isuees

Process:
1. Unsigned certificate containing user ID and user public key
2. Generate hash of cerificate
3. Encrypt hash with CA's Private Key to form signature
4. Signed certificate that can be verified using CA's Public key


####Encrypting

* Encrypting file system (EFS)  - for small buisness use - single file at a time - only for premium windows version.
	* Can insted use programs such as AEC-crypt
* Bitlocker 
	*  TPM -  trusted platform module (not required) - saves encryption key of hard drive.


#### VPN
* Internet Protocol Security (IPsec)
	* step 1  IKE 
	*  step 2 - AES 3des
	*  Problem with NAT or firewall
* SSH
	* VPN tunnling
	* USer name and password
	* Port 22
	* (Use putty program)
* SSL/TLS
	* Used to transmit sensitive information.
	* port 443
* Browser -VPN
	* HTTPS everywhere
	* ZenMate
	
DSCI


##NIST cyber-security framework

####Core 

* Identify (ID)
	* Asset Management (ID.AM)
	* Business Environment (ID.BE)
	* Governance (ID.GV)
	* Risk Assessment (ID.RA)
	* Risk Management Strategy (ID.RM)
* Protect (PR)
	* Access Control (PR.AC)
	* Awareness and Training (PR.AT)
	* Data Security (PR.DS)
	* Information Protection Processes and Procedures (PR.IP)
	* Maintenance (PR.MA)
	* Protective Technology (PR.PT)
* Detect (DE)
	* Anomalies and Events (DE.AE)
	* Security Continuous Monitoring (DE.CM)
	* Detection Processes (DE.DP)
* Respond (RS)
	* Response Planning (RS.RP)
	* Communications (RS.CO)
	* Analysis (RS.AN)
	* Mitigation (RS.MI)
	* Improvements (RS.IM)
* RECOVER (RC)
	* Recovery Planning (RC.RP)
	* Improvements (RC.IM)
	* Communications (RC.CO)

###Implantation tier
* Partial
* Risk informed
* Repeatable
* Adaptive

Bridge risk & buissnes 

#### Framework control
* COBIT
* ISA
* ISO/IEC 27001
* NIST SP800-53

##### Framework profile 
* Current risk profile (where we are)  
* Security Plan (how to reach goal)
* Target risk profile (the goal)

#####CyberSec risks

* Threats
* Vulnerabilities
* attack countermeasures 

####Standards
* NIST SP800-30
* ISO 27005

TIPS:
* Assess risks in the eyes of the attacker 
* How much does he value the information 

 appendix E - therat 

Support risk analysts - 
vcdb.org
 thaeratstream
bae systems = blog

#####Control Strategy

* Threats - Deterrent  (Jail time)
* Vulnerabilities - Preventative  (Blocking protocols)
* Incidents - Detective (Fire alarm)
* Impacts - Corrective ( Recovery from data backup)

#### Risk Treatments

* Acceptance
* Avoidance
* Transfer
* Mitigation

#### COBIT

* Align  
	* APO13 - Manage security
* Build
* Deliver
* Monitor
	* DSS05 - Manage Security Services
####APO13 - Manage security  
* AP013.01 - Establish and maintain an ISMS
* APO13.02 - Define and manage a security plan
* APO13.03 - Monitor and review the ISMS
####DSS05 - Manage Security Services
Operational security
* DSS05.01 - Protect against malware
* DSS05.02 - Manage network and connectivity security
* DSS05.03 - Manage endpoint security
* DSS05.04 - Manage user identity and logical access ( Very important)
* DSS05.05 - Manage physical access to IT
* DSS05.06 - Manage sensitive documents and output devices
* DSS05.07 - Monitor the infrastructure for security-related events

####SOA - Statement of applicability

* Link between risk and the control set
* Evidence that all controls have been considered
* Rationale for omission

####Control considerations
* Common  control
* Compensating control ( on top of common)
* Control overlays
* Control testing

####Control Testing
* Design (Ease of use)
* Operational (check if t works)


####Payment card Industry  

#####PCI terminology
* Merchant - takes credit or debit cards as payment
* Service provider - provides a service to a merchant
* Data breach - loss of credit or debit card information
* Cardholder data
* Sensitive authentication data 

####DSS - data security standard requirements

* Firewall configuration
* Change default passwords and settings
* Protect stored cardholder data
* Encrypt transmission across public networks
* Protect agaist malware
* develop and maintain secure systems and applications
* Restrict access on a need-to-know basis
* Identify and auhenticate access to system compontents
* Restrict physical access to cardholder data
* Track and monitor access to cardholder data
* Regularly test security
* Maintain an information security policy

Cyber essentials - UK government 


####Cyber kill chain

* Reconnaissance
* Weaponization
* Delivery
* Exploitation
* Installation
* Command ad Control
* Actions 

* Rootkits 
* TDL3- install from a prin

APT -advanced persistent threat , (Govramnet) 
* they are mostly successful 
* Take months to detect 

### Methods of Payload delivery
* Phising
* Malicious websites
* USB sticks
* Access to credentials
* Software flaws


###SABSA

* Understanding business requirements
* Develop security architecture
* Design and implement
* Through life management
#### why, how, where, when
* What are you trying to do at this layer? – The assets to be protected by your security architecture.
* Why are you doing it? – The motivation for wanting to apply security, expressed in the terms of this layer.
* How are you trying to do it? – The functions needed to achieve security at this layer.
* Who is involved? – The people and organisational aspects of security at this layer.
*  Where are you doing it? – The locations where you apply your security, relevant to this layer.
* When are you doing it? – The time-related aspects of security relevant to this layer.


https://en.wikipedia.org/wiki/Sherwood_Applied_Business_Security_Architecture


####Business Security

Architect risk and control
* risk to business outcomes
* Controls mitigate risks
* Business attribute profiling

calculating risk - SP800-30  or ISO 27005


#####CobIT DSS05 Processes

* DSS05.04 - Manage user identity and logical access ( Very important)
	* User access rights
	* Roles
	* Authenticate Access
	* Authorization
	* Privileged Access
	* Access and Privileges Review
	* Unique Identification
	* Audit Trail

####SP800-53 controls 
* Access control
	* AC-2 Account management
	* Ac-3 Access Enforcement
* Identification and Authentication
	* IA-2 Identity and Authentication of Organizational Users

Mehnism
* Active directory- Windows
* Lightweight Directory Access Protocol (LDAP)
* Password hash
* File Access rights
* Federated directories


####DSS05.01

* Malicious software detection
* Filter incoming traffic
* implement network filtering
* zoning
* data loss prevention

* SC-7 Boundary Protection
* SI-3 Malicious Code Protection

#####DSS05.07 - Monitoring and alerting

* Log security-related events
* Review event logs
* Network defense covet test

#####Controls

* AU-6 Audit review
* CA-8 Penetration Testing (Red Team)
* SC-5 Denial of Service
* SI-4 Information Systems Monitoring

####Incident Categories

|Category	| Name|
|-----------|
|CAT 0      | Exercise/Network Defense Testing |
|CAT 1      | Unauthorized Access              |
|CAT 2      | Denial of Service (DoS)          |
|CAT 3      | Malicious Code                   |
|CAT 4      | Improper Usage                   |
|CAT 5      | Scans/Probes/Attempted Access    |
|CAT 6      | Investigation                    |

Response tool - http://crest-approved.org/cyber-security-incident-response-guide/index.html

Situational awareness 
* cyber inteligence 
* Tactical information exchanges
* Operational feeds for indicators of compromise (IOC)

####Peocedure and technologies

* Enterprise process and system
	* isuuse tracking system
	* operational playbooks
* Jump Kit
* Establish relationship


ENISA  - cyber training

######Attack vector

* Precursor
* Indicator
* Understand normal
* Deep packet follow-up
* Prioritize

####Responding to the incident

* Preapproved containment decisions
* Investigation
* Major incident management (MIN) process
Eradication and recovery


#### User risk timeline

| Type | Zero day | User risk |
|-|
| vulnerability discovered    | V | V |
| Exploit appears in the wild | V | V |
| Patch available             | V | V |
| User patches                | - | V |


## Learning IT Security

The CIA are each a seperate goals.
* C - Safe from prying eyes
* I - Safe from unauthorized changes
* A - Reliably accessible 

###Solution matrix

* There is a trade off when you use security
	* Security
	* Usability
	* Cost Effective

#### Information Assurance Model
* A Tool to consider three key elements of asset protection
	* People
	* Process
	* Technology

#####People
* Are they trained?
* Is the entire org comitted to InfoSec?
* Do they follow security processes?

####Process
* Are secure processes documented and implemented?
* Do personnel follow processes?
* Do technologies implement processes?

####Technology
* Does the org point "the security finger" at technology?
* Does technology implement security processes?
* Does technology simplify security for people?

####Defense In depth
* Stewardship (procedure, vendor, documentation 
	* Physical
		* External Network
		* Network Perimeter
		* Internal Network
		* Host  ( OS, Host hardware)
		* Application
		* Data

#### Key documents
1/ Audit charter
	Documentss the auhority, scope, and responsibilities of the audit function
2. Engagement letter
	Focus on a specific engagement  (for an Extternal auditor)
Org cart
* Roles
* *Functions of the team
* Management responsibility
Approvals
Independence - defines how free the auditor is.



#### Planning an Audit

* * short term planning - for the yeaar
* * Long term planing - what will we do 


Audit universe -  Describs all the business processes and assets that will be included in the audit


Categorize business processes by risk



Determine which are in and out of scope

Things to consider
* changes ion controls 
* Changes into the risk enviroment
* Changing technologieschanging business process


Planning results

*- Reviewed by senrior auditor
Approved by the board/committee
Communic

ISACA - Steps to perform IS Audit Planning



Identify and document external requirements

Risk management process

Plan 
Collect information


####CISSP

#####CISCO

* Control objectives in Cobit 5
* ISO 27001
* NIST 800-53 - for federal agencies
control framework

#####Compliance obligations
4CHK
* Criminal law
* Civil law  - Resolve disputes
* Administrative law -  Facilitate effective government
* Private regulations - Flow from contractual relationships
look at FISMSA

####Privacy Compliance
* HIPPA
* FEROA - for educational instantiation
	* Regulates handling of student educational records
	* Provides right of inspection
	* Provides right to request corrections
	* Restricts release of personal information
* GBLA - Financial Institution 
	* Regulates financial institutions
	* Requires a written information security program
	* Requires a designated security officer
	* Limits sharing of financial records
* COPPA - Childrens online privacy protection act
	* Protects privacy of children under 13
	* Requires that websites have a privacy policy
	* Provides for parental inspection and deletion of information
	* Requires parental consent for data collection
* Privacy Act 1974 - regulates only federal bodies
* EU Data protection provisions  (till GDPR in 2018)
	* Process information lawfully, fairly and transparently
	* Collect information for specific and legitimate purposes
	* Limit collection to the minimum information necessary
	* Keep information accurate and up to date
	* Remove personal identifiers as quickly as possible (!)
	* Process information under responsibility and liability of a data controller


For controls go to CIS guideline

####Common Policies
* Information security policy
	* Designation of individual responsible for security
	* Decriprtion of security roles and responsibiliyeis 
	* Autority for creation of security standards
	* Authority for incident reponse
	* Process for policy exceptions and violations
* Privacy policy
* Acceptable use policy (AKA responsible use policy)
	* Describes how individuals may use information systems
	* Prohibits iiligal activites
	* Acceptable use of computer and  resource  
	* Least privalge 
	* Separation of duties
	* Mandatory vacation and Job rotation - in order to detect fraud.

#### BCP
* Use BIA


 Common point of failure
 * Power supplies
 * Storage- RAID
	 * Disk mirroring - Two mirroring
	 * RAID 5 -  Three or more disks, (not a backup startegy)

####Pre-employment Screening 
* Criminal records checks
* Sex offender registry
* Reference checks
* Variably certification
#####Agreements with newaly hires
* NDAs
* Return of physical assets at termination

* Minimize employee information kept in the firm
* Make a safe environment
* Add risk from state dep, in case of traveling to foreign countries.
 
Control Fail
* False positive errors
* False negative errors
####Identifying threats
* Assets Focus
* Threat Focus 
* Service Focus

SRIDE Attack - (Microsoft)

MSSP-  Managed security service partner (firewall, log monitoring etc)

Chk the data by type:
Data at rest 
Data in motion

Data Retention policies
Data disposal policies


#### DAta

* Data Owner - managmnet   - responsible for privacy
* Data Steward -  handle day-to-day
* Data custodian - Store and process information 

send notice to individual
Get consent of role in data.

####  GAPP 

see https://www.cippguide.org/2010/07/01/generally-accepted-privacy-principles-gapp/


1. Management

The organization defines, documents, communicates and assigns accountability for its privacy policies and procedures.
Criteria:
privacy policies define and document all ten GAPP
review and approval of changes to privacy policies conducted by management
risk assessment process in place to establish a risk baseline and regularly identify new or changing risks to personal data
infrastructure and systems management takes into consideration impacts on personal privacy
privacy awareness training
2.  Notice

The organization provides notice of its privacy policies and procedures. The organization identifies the purposes for which personal information is collected, used and retained.
Criteria:
communication to individuals
provision of notice
use of clear and conspicuous language
3. Choice and consent

The organization describes the choices available to the individual. The organization secures implicit or explicit consent regarding the collection, use and disclosure of the personal data.
Criteria:
communicating the consequences of denying/withdrawing consent
consent for new purposes/uses of the personal data
explicit consent for sensitive data
consent for online data transfer
4. Collection

Personal information is only collected for the purposes identified in the notice (see #2).
Criteria:
document and describe types of information collected and methods of collection
collection of information by fair and lawful means, including collection from third parties
inform individuals if information is developed or additional information is acquired
5. Use, retention and disposal

The personal information is limited to the purposes identified in the notice the individual consented to. The organization retains the personal information only for as long as needed to fulfill the purposes, or as required by law. After this period, the information is disposed of appropriately.
Criteria:
systems and procedures in place to ensure personal information is used, retained and disposed appropriately
6. Access

The organization provides individuals with access to their personal information for review or update.
Criteria:
confirmation of individual’s identity before access is given to personal information
personal information presented in understandable format
access provided in reasonable time frame and at a reasonable cost
statement of disagreement; the reason for denial should be explained to individuals in writing
7. Disclosure to third parties

Personal information is disclosed to third parties only for the identified purposes and with implicit or explicit consent of the individual.
Criteria:
communication with third parties should be made known to the individual
information should only be disclosed to third parties that have equivalent agreements to protect personal information
individuals should be aware of any new uses/purposes for the information
the organization should take remedial action in response to misuse of personal information by a third party
8. Security for privacy

Personal information is protected against both physical and logical unauthorized access.
Criteria:
privacy policies must address the security of personal information
information security programs must include administrative, technical and physical safeguards
logical access controls in place
restrictions on physical access
environmental safeguards
personal information protected when being transmitted (e.g. mail, internet, public or other non-secure networks)
security safeguards should be tested for effectiveness at least once annually
9. Quality

The organization maintains accurate, complete and relevant personal information that is necessary for the purposes identified.
Criteria:
personal information should be relevant for the purposes it is being used
10. Monitoring and enforcement

The organization monitors compliance with its privacy policies and procedures. It also has procedures in place to address privacy-related complaints and disputes.
Criteria:
individuals should be informed on how to contact the organization with inquiries, complaints and disputes
formal process in place for inquires, complaints or disputes
each complaint is addressed and the resolution is documented for the individual
compliance with privacy policies, procedures, commitments and legislation is reviewed, documented and reported to management



Baselines generic security requirment 



> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTgyMjMyNjgwNV19
-->