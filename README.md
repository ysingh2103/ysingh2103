<p align="center">
  <a href="https://ysingh2103.github.io"><img src="assets/header.svg" width="100%" alt="Yuvraj Singh, The TechGuy. Technical support and infrastructure, Toronto. Technical Support Specialist at DLC."></a>
</p>

<p align="center">
  <a href="https://ysingh2103.github.io"><img src="assets/btn-portfolio.png" height="40" alt="Portfolio"></a>
  <a href="https://ysingh2103.github.io/synapse/"><img src="assets/btn-synapse.png" height="40" alt="Synapse"></a>
  <a href="https://linkedin.com/in/y-singh-gill"><img src="assets/btn-linkedin.png" height="40" alt="LinkedIn"></a>
  <a href="mailto:ys.gill21@gmail.com"><img src="assets/btn-email.png" height="40" alt="Email ys.gill21@gmail.com"></a>
</p>

<p align="center">
  <img src="assets/terminal.svg" width="760" alt="$ whoami: Yuvraj Singh, technical support and infrastructure, Toronto. Technical Support Specialist at DLC. 900+ users, 15+ client organizations, 1,000+ incidents resolved. Read the logs before you guess.">
</p>

I work where things break. I've supported identity, networks, endpoints and servers across fifteen client environments, and no two behave the same way. Outside work I run a home lab and **break things on purpose**, then diagnose them from the logs. Every incident gets written up like a real ticket: symptom → hypothesis → diagnostics → root cause → verification.

<img src="assets/divider.svg" width="100%" alt="">

### Projects

<table>
  <tr>
    <td width="50%" valign="top">
      <a href="https://ysingh2103.github.io/retail-network/"><img src="assets/card-retail.png" width="100%" alt="Retail Network Lab"></a>
      <p align="center"><a href="https://ysingh2103.github.io/retail-network/"><img src="assets/btn-live.png" height="34" alt="Live demo"></a> <a href="https://github.com/ysingh2103/retail-network"><img src="assets/btn-code.png" height="34" alt="Code"></a></p>
    </td>
    <td width="50%" valign="top">
      <a href="https://ysingh2103.github.io/synapse/"><img src="assets/card-synapse.png" width="100%" alt="Synapse"></a>
      <p align="center"><a href="https://ysingh2103.github.io/synapse/"><img src="assets/btn-live.png" height="34" alt="Live demo"></a> <a href="https://github.com/ysingh2103/synapse"><img src="assets/btn-code.png" height="34" alt="Code"></a></p>
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <a href="https://github.com/ysingh2103/infra-lab"><img src="assets/card-infra.png" width="100%" alt="Self-Hosted Infrastructure Lab"></a>
      <p align="center"><a href="https://github.com/ysingh2103/infra-lab"><img src="assets/btn-code.png" height="34" alt="Code"></a></p>
    </td>
    <td width="50%" valign="top">
      <a href="https://github.com/ysingh2103/docvault"><img src="assets/card-docvault.png" width="100%" alt="DocVault"></a>
      <p align="center"><a href="https://github.com/ysingh2103/docvault"><img src="assets/btn-code.png" height="34" alt="Code"></a></p>
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <a href="https://github.com/ysingh2103/Ultron"><img src="assets/card-ultron.png" width="100%" alt="Ultron"></a>
      <p align="center"><a href="https://github.com/ysingh2103/Ultron"><img src="assets/btn-code.png" height="34" alt="Code"></a></p>
    </td>
    <td width="50%" valign="top">
      <a href="https://ysingh2103.github.io"><img src="assets/card-portfolio.png" width="100%" alt="The TechGuy portfolio"></a>
      <p align="center"><a href="https://ysingh2103.github.io"><img src="assets/btn-live.png" height="34" alt="Live site"></a> <a href="https://github.com/ysingh2103/ysingh2103.github.io"><img src="assets/btn-code.png" height="34" alt="Code"></a></p>
    </td>
  </tr>
</table>

<img src="assets/divider.svg" width="100%" alt="">

### How it connects

A small version of [Synapse](https://ysingh2103.github.io/synapse/): the skills I use, how I work, and what they built.

```mermaid
%%{init: {'theme':'base','themeVariables':{'background':'#0A0A0B','primaryColor':'#18181B','primaryTextColor':'#F2F2F4','primaryBorderColor':'#A57BFF','secondaryColor':'#111113','tertiaryColor':'#111113','lineColor':'#A57BFF','clusterBkg':'#111113','clusterBorder':'#33303d','fontFamily':'ui-monospace, monospace','fontSize':'14px'}}}%%
flowchart LR
  subgraph S[" Skills "]
    direction TB
    N[Networking]
    L[Linux]
    W[Windows Server]
    D[Databases and SQL]
    C[Cloud and Containers]
    SE[Security]
    A[Automation]
  end
  subgraph M[" How I work "]
    direction TB
    DG((Diagnose)) --> B((Build)) --> DC((Document))
  end
  subgraph P[" Projects "]
    direction TB
    R[Retail Network Lab]
    F[Store Fault Trace]
    I[Infrastructure Lab]
    DV[DocVault]
    U[Ultron]
  end
  N & L & W & D & C & SE & A --> DG
  DC --> R & F & I & DV & U
```

<img src="assets/divider.svg" width="100%" alt="">

### Incident files

Real failures from my lab, written up like support tickets. Open one.

<details>
<summary><b>INC-07</b> · CoreDNS crash-looping with clean exit codes</summary>
<br>

| | |
|---|---|
| **Symptom** | CoreDNS kept restarting in k3s while reporting clean exit codes. Nothing had been broken on purpose; it surfaced in a routine health check. |
| **Root cause** | Memory exhaustion on the node, cascading into liveness-probe timeouts. Found by tracing the k3s service logs. |
| **Write-up** | [Read the full incident →](https://github.com/ysingh2103/infra-lab/blob/main/docs/07-resource-starvation-incident.md) |

</details>

<details>
<summary><b>Mail</b> · Users could send but nobody received anything</summary>
<br>

| | |
|---|---|
| **Symptom** | Outbound mail worked, inbound never arrived. Postfix looked healthy. |
| **Root cause** | Four faults stacked on one symptom: a version-breaking config change, duplicate definitions, an mbox file/directory mismatch and wrong group permissions between Postfix and Dovecot. |
| **Lab** | [infra-lab](https://github.com/ysingh2103/infra-lab) |

</details>

<details>
<summary><b>Tomcat</b> · The service refused to start after a deploy</summary>
<br>

| | |
|---|---|
| **Symptom** | Tomcat failed on start and served nothing. |
| **Root cause** | The installed Java version didn't match what that Tomcat release needs. Found in the startup log, not by guessing. |
| **Lab** | [infra-lab](https://github.com/ysingh2103/infra-lab) |

</details>

<details>
<summary><b>IIS</b> · A site wouldn't come up on its port</summary>
<br>

| | |
|---|---|
| **Symptom** | The site wouldn't serve on Windows Server. |
| **Root cause** | A port binding conflict with another site. |
| **Lab** | [infra-lab](https://github.com/ysingh2103/infra-lab) |

</details>

<img src="assets/divider.svg" width="100%" alt="">

### Stack

<p align="center"><img src="assets/stack.png" width="100%" alt="Identity: Entra ID, Active Directory, Okta, MFA, Conditional Access, RBAC. Network: DNS, DHCP, TCP/IP, VLANs, VPNs, Fortinet, WatchGuard, pfSense. Endpoint: Intune, SCCM, Datto RMM/EDR, Microsoft Defender, BitLocker. Servers: Windows Server, Ubuntu Server, IIS, Tomcat, NGINX, Postfix/Dovecot. Cloud: Azure, VMware ESXi, Hyper-V, Docker, Kubernetes. Automate: PowerShell, Bash, Python, SQL Server, PostgreSQL, Prometheus, Grafana. Process: ServiceNow, Jira, Azure DevOps, ITIL, Selenium, UAT."></p>

### Now

```
✅ Networking, Entra ID / Active Directory, Intune
✅ Linux administration and log analysis
✅ Web and app servers: IIS, Tomcat, NGINX
✅ SQL Server and PostgreSQL
✅ Docker and Kubernetes fundamentals (k3s)
✅ Observability: Prometheus and Grafana
🔄 DocVault: Windows leg (IIS + SQL Server Express)
🔄 Ultron: fault injection, then an Azure deployment
🔄 AZ-900 Azure Fundamentals
🔄 Python for automation
⬜ CI/CD with GitHub Actions
⬜ Terraform
```

<img src="assets/divider.svg" width="100%" alt="">

<p align="center">
  <i>"Read the logs before you guess."</i><br><br>
  <a href="https://ysingh2103.github.io">ysingh2103.github.io</a> · <a href="https://ysingh2103.github.io/synapse/">Synapse</a> · <a href="https://linkedin.com/in/y-singh-gill">LinkedIn</a>
</p>
