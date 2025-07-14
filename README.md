# Mini Project - Setting up Ansible on a Linux Server (Local Setup)

## Project Overview
This project sets up Ansible on a WSL Ubuntu control node to manage a target Linux server, configuring SSH key-based authentication, creating an inventory file, and running ad-hoc commands. Builds on previous Terraform and Kubernetes projects (Jul 8-13, 2025).

## Setup
- Initiated on Jul 14, 2025, 10:02 AM WAT.
- Used WSL Ubuntu, VS Code, and Git Bash in `C:\Users\Abraham\Documents\Workspace\ansible-setup`.
- System: 2 CPUs, 2GB free memory, 20GB free disk space.
- Target: AWS EC2 instance (optional, created with Terraform).

## Execution Steps
1. **Confirm Prerequisites**:
   - Verified AWS CLI (optional) and SSH key.
   - [Screenshot: `aws_prerequisites_output_local.png` - Shows AWS CLI verification (if used).]
   - [Screenshot: `ssh_key_output_local.png` - Shows SSH key verification.]
2. **Create Target Node (Optional)**:
   - Used Terraform to create an EC2 instance.
   - [Screenshot: `terraform_target_output_local.png` - Shows EC2 creation.]
3. **Install Ansible**:
   - Installed Ansible on WSL Ubuntu.
   - [Screenshot: `ansible_version_output_local.png` - Shows Ansible version.]
4. **Configure SSH**:
   - Set up passwordless SSH to target node.
   - [Screenshot: `ssh_access_output_local.png` - Shows SSH login.]
5. **Create Inventory**:
   - Created `inventory.ini` for target nodes.
6. **Test Connectivity**:
   - Ran `ansible ping`.
   - [Screenshot: `ansible_ping_output_local.png` - Shows ping response.]
7. **Run Ad-Hoc Commands**:
   - Ran `uptime` and `df -h` commands.
   - [Screenshot: `ansible_uptime_output_local.png` - Shows uptime output.]
   - [Screenshot: `ansible_disk_usage_output_local.png` - Shows disk usage output.]
8. **Side Hustle Task**:
   - Automated Ansible setup verification with GitHub Actions.
   - Pushed to `https://github.com/westgrin/ansible-setup`.
   - [Screenshot: `github_actions_ansible_run_local.png` - Shows workflow run.]
9. **Clean Up (Optional)**:
   - Destroyed EC2 instance (if created).
   - [Screenshot: `terraform_destroy_output_local.png` - Shows destroy output.]

## Learning Summary
This project introduced Ansible for automation, building on my Terraform and Kubernetes experience (Jul 8-13, 2025). It reinforced SSH configuration and inventory management, aligning with my DevOps goals (June 16, 2025).

## Tools Used
- **WSL Ubuntu Terminal**: For Ansible and SSH commands.
- **VS Code**: For editing `inventory.ini` and `README.md`.
- **Git Bash**: For GitHub operations.
- **GitHub Actions**: For automation verification.
- **Terraform**: For optional target node creation.
- **AWS CLI**: For optional EC2 management.

## Project Deliverables
- **Documentation**: This `README.md` with steps and learning summary.
- **Screenshots**:
  - `aws_prerequisites_output_local.png` (if applicable)
  - `ssh_key_output_local.png`
  - `terraform_target_output_local.png` (if applicable)
  - `ansible_version_output_local.png`
  - `ssh_access_output_local.png`
  - `ansible_ping_output_local.png`
  - `ansible_uptime_output_local.png`
  - `ansible_disk_usage_output_local.png`
  - `github_actions_ansible_run_local.png`
  - `terraform_destroy_output_local.png` (if applicable)
- **Script Link**: [GitHub Repository](https://github.com/westgrin/ansible-setup)

## Local Development Instructions
1. Clone repository: `git clone https://github.com/westgrin/ansible-setup.git`
2. Install Ansible: `sudo apt install ansible -y`
3. Configure SSH: `ssh-copy-id user@<target-ip>`
4. Create inventory: Edit `inventory.ini` with target details
5. Test connectivity: `ansible -i inventory.ini linux_servers -m ping`
6. Run ad-hoc commands: `ansible -i inventory.ini linux_servers -m command -a "uptime"`

## Troubleshooting
- Fixed SSH issues with `ssh-copy-id` and verified with `ssh user@<target-ip>`.
- Set DNS to `8.8.8.8` for network issues.
- Verified system resources with `lscpu`, `free -h`, `df -h`.
- Ensured target node accessibility via security group (port 22).

## Conclusion
This project successfully set up Ansible on a Linux server, configured SSH, and ran ad-hoc commands, laying the foundation for advanced automation tasks in my DevOps journey.