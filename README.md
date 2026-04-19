# SDN Dynamic Host Blocking using Ryu

## 📌 Problem Statement

Implement an SDN controller that dynamically blocks hosts based on MAC address by installing drop rules using OpenFlow.

---

## ⚙️ Setup Instructions

### Step 1: Run Controller

```bash
ryu-manager learning_switch.py
```

### Step 2: Run Mininet

```bash
sudo mn --controller=remote --switch ovsk --topo single,3
```

---

## 🚀 Features

* MAC address learning (Learning Switch)
* Dynamic flow rule installation
* Host blocking using drop rules
* Controller–Switch interaction using OpenFlow

---

## 🧪 Test Scenarios

### ✅ Scenario 1: Normal Communication

* Hosts communicate successfully
* Controller learns MAC addresses
* Flow rules are installed dynamically

### 🚫 Scenario 2: Host Blocking

* One host is blocked using MAC address
* Communication fails for blocked host
* Other hosts communicate normally

---

## 📊 Results

### Ping Output

* Partial packet loss observed (blocked host)
* Example:

```
h1 -> X X
h2 -> h3
h3 -> h2
Results: 66% dropped
```

### Flow Table

* Flow entries installed dynamically
* Drop rule observed for blocked host

---

## 📸 Screenshots

* Controller running
* Mininet pingall output
* Flow table (ovs-ofctl dump-flows s1)

---

## 🧠 Concepts Used

* Software Defined Networking (SDN)
* OpenFlow Protocol
* Flow Tables
* Match-Action Rules
* Network Security (Host Blocking)

---

## 📌 Conclusion

The project successfully demonstrates dynamic host blocking using SDN principles. The controller installs flow rules to block suspicious hosts, improving network security while maintaining communication for valid hosts.
