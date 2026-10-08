# Windows Failed Login Investigation

## 📌 Project Overview

This is a beginner SOC Analyst task using **Windows Event Viewer** to investigate failed login attempts.

I analyzed **Windows Security Event ID 4625** to understand failed authentication activity, including the account involved, logon type, source IP address, and authentication method.

## 🎯 Objective

The main objective of this task was to learn how a SOC Analyst can use Windows Security logs to investigate suspicious or unsuccessful login activity.

## 🛠️ Tool Used

* Windows Event Viewer
* Windows Security Logs

## 🔍 Event Analyzed

### Event ID 4625 — Failed Logon

Event ID 4625 is generated when a Windows logon attempt fails.

During my investigation, I found:

| Field                  | Finding                    |
| ---------------------- | -------------------------- |
| Event ID               | 4625                       |
| Account                | guest                      |
| Logon Type             | 3 - Network                |
| Source Network Address | 10.119.232.96              |
| Source Port            | 46654                      |
| Authentication Package | NTLM                       |
| Failure Reason         | Account currently disabled |
| Result                 | Login rejected             |

## 🔎 Investigation

I reviewed the Windows Security logs and filtered for **Event ID 4625**.

I checked:

* Failed login events
* Account name
* Logon type
* Source network address
* Source port
* Failure reason
* Authentication package

The investigated event showed a failed network login attempt against the `guest` account.

The `guest` account was disabled, so Windows rejected the login attempt.

## 🧠 SOC Analysis

The event came from the private/internal IP address `10.119.232.96`.

The failed authentication used **NTLM** and was recorded as a network logon.

This event alone does **not** confirm a cyber attack. A SOC Analyst would investigate further if multiple failed attempts were observed from the same source or against multiple accounts.

## 📸 Screenshots

### Event ID 4625

![Event ID 4625](screenshots/01-event-4625.png)

### Network Information

![Network Information](screenshots/02-network-information.png)

### Failed Login Events

![Failed Login Events](screenshots/03-failed-login-events.png)

## 📚 What I Learned

Through this task, I learned:

* How to open Windows Event Viewer
* How to access Windows Security logs
* How to filter Event ID 4625
* How to investigate failed login attempts
* How to identify the account involved
* How to understand Logon Type 3
* How to find the source IP address
* How to identify the authentication method
* How SOC Analysts investigate authentication events

## 🛡️ Security Note

This investigation was performed on my own Windows system for cybersecurity learning and SOC Analyst practice.

The findings are based on local Windows Security logs and should not be considered proof of malicious activity without additional investigation.

## 🎯 Learning Goal

This task helped me build practical skills in **Windows log analysis, authentication monitoring, and basic SOC investigation**.
