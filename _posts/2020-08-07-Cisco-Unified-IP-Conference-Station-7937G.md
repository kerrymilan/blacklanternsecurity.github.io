---
title: Cisco Unified IP Conference Station 7937G
layout: post
author: cdm
description: Public disclosure of multiple vulnerabilities affecting the Cisco 7937G Conference Station
---

Multiple vulnerabilities were discovered in the Cisco Unified IP Conference Station 7937G including two denial-of-service flaws ([CVE-2020-16139](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-16139), [CVE-2020-16138](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-16138)) and a path to privilege escalation ([CVE-2020-16137](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-16137)) via the web administration portal. Since this product has reached end-of-support/end-of-life by Cisco, no updates to the affected firmware will be provided. There are workarounds to mitigate any potential impact you may have as a result of these findings.

## Background

Most of the issues discovered stem from the device’s usage of the **localmenus.cgi** script. While testing the device, it was noted that the same XML menu generation being done in the web administration portal, was mirrored on the physical device’s menu system. This led to the belief that whatever you could do administratively to the physical device, could also be done through the web interface.

**localmenus.cgi** takes as a parameter **func**, which requires an integer value. Capturing the request and enumerating the likely value range 0-1000, we were able to isolate functionalities that were not visible to the web interface. These include benign and silly tricks like changing volumes, contrast values, ringtones, etc. It also allows for other unsavory actions.

## CVE-2020-16139 - DoS 1

<iframe width="560" height="315" src="https://www.youtube.com/embed/WmeTyZwroE0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

The first of two denial of service vulnerabilities is caused by accessing the device’s ping functionality through the web administration portal. This can be done by iterating the **func** parameter and navigating to **func=607**. This page directs you to another valid parameter combination for executing the ping request, **func=609&rphl=1&data=**. Here, **data** is the parameter of interest, as it is where you would normally place an IP address to ping against. For our testing, we instead sent it 46 “A”s repeatedly. Normal usage of the ping function through the physical menu system clears out the ping output after the task is completed, however executing it directly like this leaves the response information.

> `/localmenus.cgi?func=609&rphl=1&data=AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA`

Sending the request repeatedly causes the device to power cycle itself around the time the resulting content-length reaches about 16316. This vulnerability can be easily mitigated by disabling the web interface in your configuration files.

## CVE-2020-16138 - DoS 2

<iframe width="560" height="315" src="https://www.youtube.com/embed/plaEj1Slx6w" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

The second of the denial-of-service vulnerabilities is caused by mishandling SSH connection attempts made with unsupported key exchange algorithms. The specific cause of the problem is not known to us as of yet, and further investigations will be done to try to isolate the cause. The following algorithms are supported, and connecting with any of them will avoid triggering the DoS:

 * diffie-hellman-group-exchange-sha1
 * diffie-hellman-group14-sha1
 * diffie-hellman-group1-sha1

With an updated SSH client, connecting to the system with default options will cause the DoS. Unlike the previous vulnerability, the device will become inoperable but will not restart until power cycled manually. This situation can be mitigated by disabling SSH access to the device in your configuration files.

## CVE-2020-16137 - Privilege Escalation

<iframe width="560" height="315" src="https://www.youtube.com/embed/_689YVh4hQY" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

The last of the vulnerabilities found so far is a path to privilege escalation. It relies on both web access and SSH access being enabled. We return to the web interface to take advantage of other hidden functionality with the **localmenus.cgi** script. Navigating to **func=401** and **func=402** reveals menus for changing the SSH username and password respectively. These pages will overwrite any currently set credentials for administrative SSH access, or set credentials if none were set previously.

To change the username, simply replace the values for **user1** and **user2** with whatever you want your new username to be:

> `/localmenus.cgi?func=403&set=401&name1=test&name2=test`

To change the password, replace the values for **pwd1** and **pwd2** with whatever you want your new password to be:

> `/localmenus.cgi?func=403&set=402&pwd1=test&pwd2=test`

Now simply connect with SSH to your now accessible administrative console, specifying a valid key exchange algorithm:

> `ssh -oKexAlgorithms=+diffie-hellman-group1-sha1 test@DEVICE-IP`

To mitigate this issue, it is recommended that SSH access be disabled, or web access be disabled. If SSH access is needed for legitimate purposes, disabling web access will remove an attacker’s ability to reset the username and password arbitrarily, though the device will still be vulnerable to the before-mentioned denial-of-service attack.

## Timeline

<link href="https://fonts.googleapis.com/css?family=Material+Icons|Material+Icons+Outlined|Material+Icons+Two+Tone|Material+Icons+Round|Material+Icons+Sharp" rel="stylesheet">
<style>
.timeline {
	border: 1px solic #fff;
	border-radius: 8px;
	display: inline-block;
	margin: 60px;
	padding: 10px;
	text-align: center;
	white-space: nowrap;
}

.timeline-label {
	display: block;
	font-family: "Courier-new";
}

.timeline-text {
	display: block;
	font-family: "Courier-new";
	width: 200px;
	font-size: small;
}

.timeline-icon {
	vertical-align: middle;
	font-size: 40px;
}

.timeline-container {
	display: inline-block;
	margin: auto;
	white-space: normal;
	vertical-align: top;
}

</style>

<div class="timeline">

<span class="timeline-container">
<span class="material-icons-two-tone timeline-icon">email</span>
<span class="timeline-label">2020-05-28</span>
<span class="timeline-text">Contacted Cisco PSIRT</span>
</span>

<span class="timeline-container">
<span class="material-icons-two-tone timeline-icon">check_box</span>
<span class="timeline-label">2020-06-22</span>
<span class="timeline-text">Worked with Cisco PSIRT to identify issue, provide PoCs, coordinate additional testing of hardware, and confirmed issue isolated to EoL/EoS devices.</span>
</span>

<span class="timeline-container">
<span class="material-icons-two-tone timeline-icon">email</span>
<span class="timeline-label">2020-06-22</span>
<span class="timeline-text">Contacted MITRE to request CVEs</span>
</span>

<span class="timeline-container">
<span class="material-icons-two-tone timeline-icon">check_box</span>
<span class="timeline-label">2020-08-06</span>
<span class="timeline-text">Confirmed with MITRE on PoC and Cisco acknowledgement</span>
</span>

<span class="timeline-container">
<span class="material-icons-two-tone timeline-icon">article</span>
<span class="timeline-label">2020-08-10</span>
<span class="timeline-text">Public Disclosure</span>
</span>


</div>

## Public Exploit PoCs

As part of this publication, three metasploit modules are being released to test for the vulnerabilities discovered, as well as an all in one exploiter that can be used when metasploit is not preferred.

They can be found here: [Cisco-7937G-PoCs](https://github.com/blacklanternsecurity/Cisco-7937G-PoCs)

