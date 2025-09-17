# OpenShift CLI Setup on Windows

## Prerequisites
- Windows operating system.
- PowerShell installed (version 5.1 or later recommended).
- OpenShift CLI (`oc.exe`) downloaded.

## Steps to Set Up OpenShift CLI

### 1. Download the OpenShift CLI
- Visit [OpenShift CLI Downloads](https://cloud.redhat.com/openshift).
- Download the `oc` CLI for Windows.

### 2. Create a Directory for the CLI
- Open PowerShell and run:
New-Item -ItemType Directory {directory}

### 3. Move `oc.exe` to the Directory
- Place the `oc.exe` file in the {directory}.

### 4. Add the Directory to PATH

#### For the Current Session:
- Run the following command in PowerShell:
$env:Path += ";{directory}"

#### For All Future Sessions:
- Run the following commands in PowerShell:
$CurrentPath = [Environment]::GetEnvironmentVariable('Path', [System.EnvironmentVariableTarget]::User)
[Environment]::SetEnvironmentVariable("Path", $CurrentPath + ";{directory}", [System.EnvironmentVariableTarget]::User)

### 5. Verify the Installation
- Open a new terminal and run:
oc version
- You should see the version information for the `oc` CLI.

## Notes
- Ensure you have the necessary permissions to modify environment variables.
- If you encounter issues, restart your terminal or system to apply changes.

---

Happy OpenShift-ing!
