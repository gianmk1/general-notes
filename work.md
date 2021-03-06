# General notes

## OpenVAS
1. External scan with "Full And Fast" - "All IANA assigned TCP" - "OpenVAS default scanner"
2. External scan with "Full And Fast" - "All IANA assigned TCP" - "CVE scanner"
3. Internal scan with "Full And Fast" - "All IANA assigned TCP" - "OpenVAS default scanner" + CREDENTIALS

NB. "Full and Fast" config can cause a lot of noise. It's recommended to look for alternative scanning configurations.


## Nessus notes
- Is possible to change the license code without losing the scans already done
- Is not possible to reset the scan count with another license code
- Maybe is possible to recieve more licence codes with the same email address


## TODO
- Performe an advanced Active Directory analysis
- Python script to extract CVEs from Nmap scans
- Python script to calculate CVSS score with the CVE discovered and Nessus/OpenVAS
- Performe a web application scan also with OpenVAS
- Python script to automatic rename reports specifying the configuration used


## Port scanning
- Alternative NSE script for vulnerabilities: https://null-byte.wonderhowto.com/how-to/easily-detect-cves-with-nmap-scripts-0181925/