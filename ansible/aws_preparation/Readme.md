# AWS Preparation
Toolset to prepare AWS server. It configures swap, changes name, updates motd and setup imprescindible software.

## ✅ Prerequisites
* SSH Root access to server.
* In remote server: `apt update && apt install python-minimal -y`

## 🚀 Usage
* fullfil hosts file with aws servers to prepare (group [aws]).
* Edit vars/main.yml with desired variables
* Launch with `ansible-playbook main.yml`