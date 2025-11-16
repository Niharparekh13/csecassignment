Cyber Threat Intelligence Assignment 

Name: Nihar Parekh

Diamond Model Elements 
---
| Vertex | Details Extracted from Report | Evidence  |
|--------|------------------------------|--------------------------------|
| **Adversary** | Likely a Russian speaking threat actor; financially motivated or RaaS-like group; avoids infecting Russian/CIS regions | The TA excludes infections from Russian speaking region ; We suspect the TA could be a Russian-speaking individual or group. ; Evidence suggests it is likely the work of a financially motivated, Russian speaking group or RaaS entity. |
| **Infrastructure** | Malicious LNK file delivered via phishing email; PowerShell loader; CDN-hosted PNG payload on fast CDN; C2 domain; WebSocket communication ;| Distributed to users via spam email ; PNG file hosted on a CDN ; C&C server ; RAT connect ;  |
| **Capability** | Steganography-based payload delivery; Zip compressed shellcode inside PNG; DLL reflection loading; PowerShell execution; APC injection into PowerShell.exe; Go-based RAT with file ops, network scanning, AD enumeration, credential theft, and ransomware deployment | A Zip compressed payload hidden within a PNG file ; Injects shellcode using APC injection ; Final payload is a RAT written in Go ; Command ransom deploys ransomware |
| **Victim** | Individuals interested in Indian political affairs: journalists, analysts, researchers, think tanks, government observers; India as the targeted region; excludes Russia regions | Targeting individuals with a keen interest in Indian political affairs ; May include government officials, political analysts, journalists, researchers, think tanks ; Designed to prevent execution in Russian speaking regions |


Threat Actor Profile Summary
---
In this campaign, the threat actor is not formally attributed to any know group, but the reports suggests that several clues about the origin. The actor appears to be likely a Russian speaking Group supported by the use infections. also the behavioral indicators such as steganographic image originated suggest that it may be a RaaS style operation. Although attribution is not definitive.
The attacks begins with a malicious .LNK shortcut file disguised as legitimate office document, likely disturbed through phishing emails which when executed a PowerShell commands that deploy .NET loader, and creates a document and retrieve a PNG file containing a Zip payload. the loader injects decrypted shellcode into PowerShell using APC injection and delivering a RAT. This malware provides extensive capabilities inkling file manipulation, credential harvesting etc, while communicating with its server .
The targeting pattern strongly indicates a focus on individuals involved in Indian political affairs, including journalists, officials etc, The document is crafted to mimic Indian Parliament. It also exclusion Russian speaking regions.
From a Diamond model perspective , the adversary demonstrates a Russian Group, supported by a capabilities of RAT, scripting and credential stealing tools the infrastructure relies on Phishing delivery, C2 domain etc, while the victim profile centers on politically engaged individuals in India. Recommended mitigation's include avoiding suspicious attachments such as LNK files, restricting PowerShell execution, monitoring traffic.

---
Reflection

---
1. How does the Diamond Model help in understanding threat actors?

The Diamond Model helps break down a cyberattack into four clear components, making it easier to understand how a threat actor operates. By separating the adversary, their capabilities, their infrastructure, and their victims, the model shows how each part is interconnected. It forces analysts to look beyond the malware itself and consider who is behind the attack, what their tools and motives are, how they deliver their payloads, and who they are targeting. This structured approach makes complex intrusions easier to analyze and compare with other campaigns.

2. What challenges did you face in identifying each vertex?

One challenge was that the report did not explicitly name the threat actor, so determining the Adversary required interpreting indirect clues such as region exclusions and behavioral indicators. For Infrastructure, the report contained many technical elements, and it took effort to differentiate between delivery mechanisms, payload hosting, and command and control servers. Identifying Capability was difficult because the malware chain had multiple stages, including steganography, loaders, injection techniques, and RAT functions. The Victim vertex required close reading of the lure document and understanding the intended target audience.


3. How could this model support proactive defense strategies?

The Diamond Model helps defenders anticipate attacks by revealing patterns in how specific actors operate. Understanding adversary motives and victim profiles can help organizations assess whether they are likely targets. Knowing the attacker’s infrastructure such as phishing methods, CDN use, or C2 domains allows security teams to detect early indicators before a full compromise. Recognizing capabilities such as credential theft, lateral movement, or RAT behaviors enables stronger monitoring, patching, and preventive controls. Overall, the model turns complex threat data into actionable insights that support proactive defense.