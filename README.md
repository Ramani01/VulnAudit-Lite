# VulnAudit-Lite

![VulnAudit-Lite Banner](https://raw.githubusercontent.com/yourusername/VulnAudit-Lite/main/banner.png)

A lightweight system vulnerability scanner written in Python.

[![Python](https://img.shields.io/badge/python-3.7%2B-blue)](#python)
[![Cybersecurity](https://img.shields.io/badge/cybersecurity-security%20tool-orange)](#cybersecurity)
[![Vulnerability Scanner](https://img.shields.io/badge/vulnerability--scanner-infosec-brightgreen)](#vulnerability-scanner)
[![License](https://img.shields.io/badge/license-MIT-blue)](LICENSE)

## Features

- 🔍 **Antivirus Status**: Checks Windows Defender (Windows) and UFW (Linux) status
- 🔄 **Update Detection**: Identifies pending OS updates
- 🚫 **Malware Protection**: Scans USB drives for autorun.inf files
- 🦠 **Advanced Malware Detection**: Enhanced .exe file scanning with threat intelligence
- 🔐 **Password Security**: Weak password detection (placeholder)
- 🛡️ **CVE Lookup**: Real-time CVE information via NVD API
- 📊 **Risk Scoring**: Weighted vulnerability assessment with risk scores
- 📈 **Historical Tracking**: SQLite database for scan history
- 📋 **Multiple Reports**: JSON and HTML report generation
- ⌨️ **CLI Interface**: Comprehensive command-line argument support

## Demo

![Report Screenshot](https://raw.githubusercontent.com/yourusername/VulnAudit-Lite/main/screenshot.png)

## Requirements

- Python 3.7+
- See [requirements.txt](file:///c%3A/Users/mitti/Downloads/VulnAudit-Lite/requirements.txt) for Python package dependencies

## Installation

```bash
pip install -r requirements.txt
```

## Usage

### Basic Scan
```bash
python main.py
```

### Advanced Options
```bash
# Custom output filename
python main.py --output report.html

# Specify database path
python main.py --db-path /path/to/database.db

# Disable database storage
python main.py --no-db

# List previous scans
python main.py --list-scans

# Quarantine suspicious files
python main.py --quarantine

# Configure malware scanning
python main.py --scan-malware --directories ~/Downloads ~/Documents --virustotal-key YOUR_API_KEY --real-time-alerts
```

## Malware Engine Features

### Enhanced Detection Capabilities
- **Threat Intelligence Feeds**: Integration with open-source threat feeds for larger signature database
- **VirusTotal Integration**: Optional verification using VirusTotal API for comprehensive file analysis
- **Real-time Alerts**: Immediate notifications when malicious files are detected
- **Configurable Scanning**: Enable/disable malware detection and specify directories to monitor

### CLI Options for Malware Detection
- `--scan-malware`: Enable malware scanning (default: enabled)
- `--no-scan-malware`: Disable malware scanning
- `--directories`: Specify custom directories to scan for malware
- `--virustotal-key`: Provide VirusTotal API key for enhanced verification
- `--real-time-alerts`: Show real-time alerts for detected threats

## Output

The tool generates:
1. Console output with summarized results and risk score
2. Detailed JSON report file with timestamp
3. Styled HTML report with visual indicators
4. SQLite database for historical tracking

## Risk Scoring

Vulnerabilities are weighted as follows:
- Windows Defender Disabled: 10 points
- UFW Disabled: 8 points
- Pending Critical Updates: 9 points
- Autorun.inf Files Found: 7 points
- Malware .exe Files Found: 10 points
- Critical CVE Found: 10 points
- High Severity CVE: 8 points
- Medium Severity CVE: 5 points

Risk Levels:
- 80-100: CRITICAL
- 60-79: HIGH
- 40-59: MEDIUM
- 20-39: LOW
- 0-19: MINIMAL

## Malware Detection

VulnAudit-Lite includes advanced malware detection capabilities:
- Scans common directories for suspicious .exe files
- Checks file hashes against known malware signatures
- Identifies files with suspicious names (crack.exe, keygen.exe, etc.)
- Optional quarantine functionality for suspicious files
- Integration with VirusTotal for comprehensive file analysis
- Real-time alerts for immediate threat notification

## Notes

- Some checks may require administrator/root privileges for full functionality
- CVE lookups require internet connectivity
- USB scanning only works on mounted removable drives
- Password strength checking requires elevated privileges and is not implemented in this lightweight scanner
- Malware detection is signature-based and may not catch all threats
- VirusTotal integration requires an API key (https://www.virustotal.com/)

## Tags

#python #cybersecurity #vulnerability-scanner #infosec #security-audit #penetration-testing #network-security #malware-detection

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Version

v1.0.0