# office-network-infrastructure
Office Network Setup and IT Infrastructure Management - Windows Server, Active Directory, DHCP, DNS, VLAN, Office 365 deplo

## 📋 Project Overview

This repository documents the complete setup and management of an office network infrastructure for 50+ users, including Windows Server deployment, Active Directory configuration, network services, and Office 365 integration.

## 🎯 Objectives

- Design and implement a scalable network infrastructure
- Centralize user management with Active Directory
- Automate IT operations using PowerShell scripts
- Deploy and configure Office 365 suite
- Establish security best practices and documentation

## 🏗️ Infrastructure Components

### 1. Windows Server 2019 Active Directory
- **Domain Controller**: Primary DC with FSMO roles
- **Organizational Units**: Structured OU design for users, groups, and computers
- **Group Policy Objects**: Centralized policy management
- **User Management**: 50+ user accounts with role-based access

### 2. Network Services
- **DHCP Server**: Automated IP address management
  - Scope: 192.168.1.0/24
  - Reservations for servers and printers
  - Lease time: 8 days
- **DNS Server**: Internal name resolution
  - Forward and reverse lookup zones
  - Conditional forwarders for external domains
- **VLAN Configuration**: Network segmentation
  - VLAN 10: Management
  - VLAN 20: Users
  - VLAN 30: Guests
  - VLAN 40: Servers

### 3. Office 365 Deployment
- **Exchange Online**: Email and calendar services
- **Microsoft Teams**: Collaboration and meetings
- **SharePoint Online**: Document management
- **OneDrive for Business**: Cloud storage
- **Azure AD Connect**: Hybrid identity synchronization

### 4. Security Implementation
- Windows Defender ATP
- Firewall rules and network security groups
- BitLocker encryption for endpoints
- Regular security updates and patch management

## 📁 Repository Structure

```
office-network-infrastructure/
├── README.md
├── docs/
│   ├── network-architecture.md
│   ├── active-directory-setup.md
│   ├── dhcp-dns-configuration.md
│   ├── vlan-implementation.md
│   └── office365-deployment.md
├── scripts/
│   ├── powershell/
│   │   ├── create-ad-users.ps1
│   │   ├── configure-dhcp.ps1
│   │   ├── backup-gpo.ps1
│   │   └── audit-ad-health.ps1
│   └── batch/
│       └── network-diagnostics.bat
├── diagrams/
│   ├── network-topology.png
│   └── ad-structure.png
└── policies/
    ├── password-policy.md
    ├── backup-policy.md
    └── disaster-recovery.md
```

## 🚀 Quick Start

### Prerequisites
- Windows Server 2019 or later
- Active Directory Domain Services role
- DHCP and DNS server roles
- Office 365 tenant
- PowerShell 5.1 or later

### Installation Steps

1. **Install Active Directory**
```powershell
Install-WindowsFeature -Name AD-Domain-Services -IncludeManagementTools
Install-ADDSForest -DomainName "yourdomain.local"
```

2. **Configure DHCP**
```powershell
Add-DhcpServerv4Scope -Name "Office Scope" -StartRange 192.168.1.100 -EndRange 192.168.1.200 -SubnetMask 255.255.255.0
Set-DhcpServerv4OptionValue -DnsDomain "yourdomain.local" -DnsServer 192.168.1.10
```

3. **Create AD Users**
```powershell
Import-Module ActiveDirectory
New-ADUser -Name "John Doe" -SamAccountName jdoe -UserPrincipalName jdoe@yourdomain.local
```

## 📊 Monitoring & Maintenance

- **Event Viewer**: Daily log review
- **Performance Monitor**: Resource utilization tracking
- **Backup**: Daily system state and GPO backups
- **Updates**: Monthly Patch Tuesday implementation

## 🔧 Troubleshooting

Common issues and solutions:
- **DNS Resolution**: Check forwarders and root hints
- **DHCP Leases**: Review scope utilization
- **AD Replication**: Use `repadmin /showrepl`
- **Group Policy**: Use `gpresult /r` for troubleshooting

## 📈 Future Enhancements

- [ ] Implement Network Access Protection (NAP)
- [ ] Deploy Windows Admin Center
- [ ] Automate with Azure Automation
- [ ] Implement Multi-Factor Authentication
- [ ] Set up monitoring with System Center

## 👨‍💻 Author

**Karthi G**
- System Administrator
- Location: Bangalore, India
- LinkedIn: https://www.linkedin.com/in/karthi-g17/

## 📄 License

This project is for educational and documentation purposes.

## 🤝 Contributing

Feel free to fork this repository and submit pull requests for improvements.
yment and automation project
