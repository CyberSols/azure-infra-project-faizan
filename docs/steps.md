# Step-by-Step Implementation

## 1. Create Resource Group
- Name: `rg-azure-infra-faizan`
- Region: UK South

## 2. Create Virtual Network & Subnets
- VNet: `vnet-faizan`
- Address space: `10.0.0.0/16`

Subnets:
- `subnet-frontend` → `10.0.1.0/24`
- `subnet-backend` → `10.0.2.0/24`

## 3. Create Network Security Group (NSG)
Name: `nsg-faizan-web`

Inbound rules:
- Allow RDP (3389) or SSH (22) from **My IP**
- Allow HTTP (80) from Internet
- Allow HTTPS (443) from Internet

## 4. Create Virtual Machine
- Name: `vm-faizan-web01`
- OS: Windows Server 2022 (or Ubuntu)
- Size: `Standard_B1s`
- VNet: `vnet-faizan`
- Subnet: `subnet-backend`
- NSG: `nsg-faizan-web`

### Install Web Server

#### Windows (PowerShell)
```powershell
Install-WindowsFeature -Name Web-Server -IncludeManagementTools
