# 01_add-vm: Virtual Machine Setup & Snapshot Guide

This guide details the installation, configuration, and management of the `01_add-vm` virtual machine using **VirtualBox** (X86-64).

## 1. Credentials & Info
* **VM Name:** `01_add-vm`
* **Username:** `root`
* **Password:** ` ` (A single space character)
* **Download Link:** [01_add-vm.tar.gz](https://assets.01-edu.org/sys/01_add-vm.tar.gz)

---

## 2. Installation (GUI)
1.  **Download:** Save the [01_add-vm.tar.gz](https://assets.01-edu.org/sys/01_add-vm.tar.gz) file.
2.  **Extract:** Unzip the file and move the `01_add-vm` folder into your `~/VirtualBox VMs` directory.
3.  **Import:**
    * Open **VirtualBox**.
    * Click **Machine** → **Add** from the menu.
    * Navigate to the folder and select the `01_add-vm.vbox` file.
    * The VM will appear in your list.

---

## 3. Snapshots (Critical Step)
**You must take a snapshot immediately after importing.** This acts as a save point. If you break the system during an exercise, you can revert to this state instantly.

### Method A: Graphical Interface (GUI)
1.  Select `01_add-vm` in the VirtualBox list.
2.  Click the **List Icon** (three lines) next to the name and choose **Snapshots**.
3.  Click the **Take** (Camera icon) button.
4.  **Name:** `Clean Install`
5.  Click **OK**.

### Method B: Command Line (CLI)
If you prefer the terminal, you can manage snapshots using `VBoxManage`:

```bash
# Create a snapshot
VBoxManage snapshot "01_add-vm" take "Clean Install" --description "Fresh import state"

# Restore the snapshot (if you break the VM later)
# VBoxManage controlvm "01_add-vm" poweroff
# VBoxManage snapshot "01_add-vm" restore "Clean Install"