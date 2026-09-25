<img width="1171" height="875" alt="image" src="https://github.com/user-attachments/assets/7981a21e-b90f-426b-a3ed-ef922ef451fe" />

# German-Threat-Intelligence-SOC-Dashboard
A Comprehensive SOC analyst frontend for the German threat intelligence sharing ecosystem. 

German Threat Intelligence Sharing Platform (ACS/UP KRITIS Integration)
The Problem: Germany has two major threat intelligence sharing initiatives—the Alliance for Cyber Security (ACS) with 6,700+ members and UP KRITIS for critical infrastructure operators—but participation is often passive (receiving alerts) rather than active (contributing IOCs, sharing incident patterns). The BSI acts as the central clearinghouse, but smaller German companies lack SOC tooling to operationalize shared intelligence quickly. ​
Project Overview: Build a SOC analyst frontend that:
 
Subscribes to BSI/ACS threat feeds and UP KRITIS sector-specific alerts (energy, health, transport, etc.)
 
Enriches incoming alerts with German-context IOCs (e.g., threats targeting German Energieversorger, attacks on Deutsche Bahn systems)
 
Allows SOC analysts to contribute anonymized incident patterns back to the community with BSI-compliant anonymization
 
Correlates shared intelligence against internal SIEM data to detect emerging threats affecting similar German sectors
 
Generates sector-specific threat briefings for management (e.g., "Healthcare ransomware trends affecting German hospitals this quarter")
Frontend Features: Threat feed dashboard with German sector filters, IOC matching engine with internal SIEM integration, anonymized incident contribution wizard, sector threat trend visualizations, and BSI Lagebericht (situation report) style executive summaries.
Why It Matters: The BSI's role as the central clearinghouse for federal cybersecurity cooperation (§4 I BSIG) makes threat intelligence sharing a national priority. With NIS2 expanding to ~30,000 entities, the ACS and UP KRITIS networks are growing rapidly. German employers value analysts who understand cooperative defense—a core pillar of Germany's cybersecurity strategy. This project shows you can bridge technical SOC work with the collaborative intelligence culture that defines the German market.

**German Threat Intelligence SOC Dashboard**

A single-file, self-contained HTML dashboard for German cybersecurity operations centers (SOCs) integrating threat intelligence from BSI-CERT, ACS (Alliance for Cyber Security), and UP KRITIS sector nodes.
Overview
This dashboard provides a unified interface for:
Monitoring real-time threat feeds from German critical infrastructure protection organizations
Correlating shared IOCs against internal SIEM logs
Contributing anonymized incident data back to the ACS/UP KRITIS sharing community
Analyzing sector-specific threat trends
Generating executive threat briefings (Lagebericht) in BSI style
File Structure
plain
german_threat_intel_dashboard.html   # Single self-contained file (HTML + CSS + JS)
No build step, no dependencies, no server required. Open directly in any modern browser.
Features
1. Threat Feed (Tab: "Threat feed")
Real-time alert table from BSI-CERT, ACS, and UP KRITIS feeds
Sector filtering: All, Energy, Health, Transport, Finance, Water, Telecom
Live search: Filter by title, sector, source, or TLP classification
Pagination: 7 alerts per page with navigation
Export: Download as CSV or JSON
Demo data: 20 realistic alerts covering German critical infrastructure threats
2. SIEM Correlation (Tab: "SIEM correlation")
IOC hit summary with match counts and correlation status
Active correlation rules table with hit statistics
Run correlation: Simulates live SIEM scanning with randomized hit updates
SIEM integration: Configurable endpoints for Splunk, Elastic, QRadar, Sentinel, Exabeam
Export rules: Download correlation rules as JSON
3. Incident Sharing (Tab: "Share incident")
4-step wizard for BSI-compliant anonymized incident contribution:
Classification: Incident type, sector, severity (BSI scale), TLP
IOCs & TTPs: MITRE ATT&CK techniques, attack vector description
Anonymization preview: BSI-compliant PII redaction demonstration
Review & submit: Final confirmation with MISP event preview
Load draft: Pre-fills a sample healthcare ransomware incident
MISP configuration: Connection settings for ACS/UP KRITIS sharing nodes
4. Sector Trends (Tab: "Sector trends")
Animated bar chart: Threat volume by German critical infrastructure sector
Sector breakdown table: Top threats, trends, NIS2 relevance
Export: Chart data and sector breakdown as CSV
5. Lagebericht (Tab: "Lagebericht")
BSI-style executive threat briefing (Q3 2026)
Auto-generated from feed data + SIEM correlation
Actions: Export PDF, Export DOCX, Email to management, Schedule recurring
Demo Mode
All features run in demo mode by default:
Simulated data (no external API calls)
Simulated SIEM/MISP connections
All export functionality works with generated files
To connect to live systems, configure the SIEM and MISP settings in their respective tabs.
Data Sources Referenced
Table
Source	Role
BSI-CERT	Federal Office for Information Security — national CERT
ACS	Alliance for Cyber Security (Allianz für Cybersicherheit)
UP KRITIS	Sector-specific critical infrastructure protection nodes
MISP	Malware Information Sharing Platform for threat sharing
MITRE ATT&CK	TTP framework for attack technique classification
TLP	Traffic Light Protocol for information sharing control
Technical Details
Single file: HTML5 + vanilla CSS + vanilla JavaScript
No dependencies: Zero external libraries or frameworks
Responsive: Works on desktop and mobile (media queries at 640px breakpoint)
Dark mode: Respects prefers-color-scheme: dark
Browser support: Chrome, Firefox, Safari, Edge (last 2 versions)
Usage
Download german_threat_intel_dashboard.html
Open in any modern web browser (double-click or File > Open)
Navigate tabs using the top navigation bar
Interact with filters, search, pagination, and export buttons
Use the wizard to simulate incident sharing
Customization
Adding Real Data
Replace the feedData, siemData, and rulesData arrays in the <script> section with API calls to your live threat intelligence feeds.
Connecting to Live SIEM
In the SIEM tab, select your SIEM type and enter:
API endpoint URL
Authentication token
Index/sourcetype filter
Click "Test connection" then "Save configuration"
Connecting to MISP
In the Share incident tab, enter:
MISP instance URL
API authentication key
Default sharing group (ACS Community or UP KRITIS sector)
Organization UUID
License
Internal use for German critical infrastructure operators and ACS members.
Contact
For questions about ACS/UP KRITIS integration, contact your sector node coordinator or BSI-CER
