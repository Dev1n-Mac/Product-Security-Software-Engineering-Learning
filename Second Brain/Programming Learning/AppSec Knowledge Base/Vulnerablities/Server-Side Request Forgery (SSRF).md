## Description

SSRF flaws occur whenever a web application is fetching a remote resource without validating the user-supplied URL. It allows an attacker to coerce the application to send a crafted request to an unexpected destination, even when protected by a firewall, VPN, or another type of network access control list (ACL).

As modern web applications provide end-users with convenient features, fetching a URL becomes a common scenario. As a result, the incidence of SSRF is increasing. Also, the severity of SSRF is becoming higher due to cloud services and the complexity of architectures.

## How to Prevent

Developers can prevent SSRF by implementing some or all the following defense in depth controls:

### **From Network layer**

- Segment remote resource access functionality in separate networks to reduce the impact of SSRF
    
- Enforce “deny by default” firewall policies or network access control rules to block all but essential intranet traffic.  
    _Hints:_  
    ~ Establish an ownership and a lifecycle for firewall rules based on applications.  
    ~ Log all accepted _and_ blocked network flows on firewalls (see [A09:2021-Security Logging and Monitoring Failures](https://owasp.org/Top10/A09_2021-Security_Logging_and_Monitoring_Failures/)).
    

### **From Application layer:**

- Sanitize and validate all client-supplied input data
    
- Enforce the URL schema, port, and destination with a positive allow list
    
- Do not send raw responses to clients
    
- Disable HTTP redirections
    
- Be aware of the URL consistency to avoid attacks such as DNS rebinding and “time of check, time of use” (TOCTOU) race conditions
    

Do not mitigate SSRF via the use of a deny list or regular expression. Attackers have payload lists, tools, and skills to bypass deny lists.

### **Additional Measures to consider:**

- Don't deploy other security relevant services on front systems (e.g. OpenID). Control local traffic on these systems (e.g. localhost)
    
- For frontends with dedicated and manageable user groups use network encryption (e.g. VPNs) on independent systems to consider very high protection needs
    

## Example Attack Scenarios

Attackers can use SSRF to attack systems protected behind web application firewalls, firewalls, or network ACLs, using scenarios such as:

**Scenario #1:** Port scan internal servers – If the network architecture is unsegmented, attackers can map out internal networks and determine if ports are open or closed on internal servers from connection results or elapsed time to connect or reject SSRF payload connections.

**Scenario #2:** Sensitive data exposure – Attackers can access local files or internal services to gain sensitive information such as `file:///etc/passwd` and `http://localhost:28017/`.

**Scenario #3:** Access metadata storage of cloud services – Most cloud providers have metadata storage such as `http://169.254.169.254/`. An attacker can read the metadata to gain sensitive information.

**Scenario #4:** Compromise internal services – The attacker can abuse internal services to conduct further attacks such as Remote Code Execution (RCE) or Denial of Service (DoS).