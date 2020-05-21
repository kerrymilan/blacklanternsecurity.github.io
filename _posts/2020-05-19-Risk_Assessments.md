---
title: Risk Assessments
layout: post
author: tjp
description: Risk Assessments - An introduction to the risk management series
---
# **Risk Assessments**

## **Risk Assessment Series**

BLSOPS LLC ("BLS") has found that one of the most important challenges facing clients is assessing and managing risk. This blog series focuses on the value of a risk assessment and explores the consequences of various forms of compromises. This blog series also extends research from a previous post, [Assessing Your Risks](https://www.blacklanternsecurity.com/2017-01-01-cybersecurity-exposure/), as it connects regulations to companies. Further, the series explores how these regulatory risks, among others, can be managed and mitigated through the application of a risk assessment.

### **Future Posts in this Series**

This series will continue with the following topics:

1. Risk Assessmentments

2. Controls

3. Remediation

4. Primary Financial Regulations Revisited

5. Attack Narratives To Beware

The first post of this series explores the purpose and advantages of a risk assessment. The information detailed below will serve as the foundation for future blog posts.

## **The Value of a Risk Assessment**

Bearing risk is how businesses run; managing these risks is secondary to the business' top priority of generating sufficient cash flows to maintain its operations. Certain risks, however, can threaten to eliminate the business' cash flows, causing disruptive headaches.  Companies that find themselves in this situation must seek out cost-effective ways to manage these risks, ensuring that its solutions don't have the same disruptive effects on the business' cash flows. At a minimum, businesses will manage some risk through government regulations and compliance, including the risk of noncompliance fines. Noncompliant businesses are facing stricter regulations in the United States with a recent [$5 billion fine](https://www.ftc.gov/news-events/press-releases/2019/07/ftc-imposes-5-billion-penalty-sweeping-new-privacy-restrictions) and in Europe with the introduction of [the GDPR](https://gdpr.eu/fines/). So it is not a surprise that this is a growing concern. However, following compliance alone is often insufficient for providing appropriate security and protection for a business. More than just compliance, a company needs to assess its risks and determine solutions that are appropriate given its "risk appetite", the amount of risk the company is willing to accept in pursuit of value.

In a risk assessment, a company must identify all areas where it faces risk, determine the best solutions for defending against those risks, and then implement only appropriate solutions that still allow the business to operate. If it was just a simple three-step solution, companies would never face an unexpected breach, but in 2019 there were [7,098 breaches containing 15.1 billion records](https://www.helpnetsecurity.com/2020/02/11/2019-reported-breaches/). The fallout of every breach varies: [some companies lose sales](https://www.wsj.com/articles/target-profit-declines-on-data-breach-fallout-1393419381), [some companies are fined heavily](https://www.ftc.gov/news-events/press-releases/2019/07/equifax-pay-575-million-part-settlement-ftc-cfpb-states-related), and [some companies go bankrupt](https://docs.house.gov/meetings/SM/SM00/20150422/103276/HHRG-114-SM00-20150422-SD003-U4.pdf). For a company trying to protect itself and its stakeholders, they need to choose between some combination of risk assessments performed by either themselves or external consultants. It can be challenging still for a company to rely solely on an internal risk management team, as they would need to reliably evaluate each segment of the company and report findings honestly to decision-makers. While that may lead to office politics issues, it is certainly not the only challenge for internal assessors.

That is not to say it is easy for companies to work with outside assessors and consultants. One of the expected challenges is maintaining strong communication and healthy relationships. For many outside assessors, it is easy to ignore the fact that a client company has purchased an assessment specifically to improve itself. Instead, the external teams performing an engagement may break into the system in hundreds of ways and provide unclear recommendations and fixes. Alternatively, an assessor may find only a few key technical problems and provide solutions for those issues alone. This approach fails to address tactical and strategic vulnerabilities in the business processes themselvess. This can leave the client company exposed in other more serious ways. Furthermore, a highly technical report that ignores or omits systemic or strategic vulnerabilities will result in a client company being misinformed about its true risk levels. Compound these issues with the fact that it can often be hard for the client company to receive constructive feedback from the assessor and understand how to properly remediate issues. If the client company is not educated on how to best separate the technical from the non-technical and the tactical from the strategic (systemic), they will still have the same issues. 

Most importantly, a proper risk assessment should be done with a trusted partner that truly takes the time to understand the business, its mission, and critical processes. A trusted partner will be able to provide a comprehensive view on company risk and work to identify near-, mid-, and long-term mitigation strategies. As the relationship with the trusted partner develops and additional risk assessments are executed, the client should find that their defenses are being incrementally "boot-strapped" and they are approaching their target risk-rating. Over time, the recommended remediations and fixes will reflect the fact that the company's defenses have evolved from protecting against low level threats to much more advanced attackers.

### **How a Risk Assessment and Pentetration Test Differ**

It is worth mentioning penetration tests (pentests) as another option companies use to evaluate risk. A pentest and risk assessment are similar in that both aim to identify gaps in security controls and understand the associated risks, but they can differ in how they handle scoping, coverage, and technical depth of reporting.

There are many ways to scope a penetration test, but they generally involve a team of technical professionals simulating adverseries attempting to infiltrate a company's systems. The deliverable is a report that details the operators' findings and suggests remediations. These remediations, which usually take the form of technical fixes or process improvements, are presented from the assessor's perspective and are limited in their ability to incorporate knowledge about the client organization's assets, priorities, and business processes.

A risk assessment takes a more comprehensive approach, seeking to gather as much information about the client organization's operations as possible. This information comes from interviews with key personnel, including the executive team and owners of the business' most critical resources. By pairing the knowledge gathered in these interviews (e.g. revenue, profit, transaction volumes, APARs processing, vendor maintenance, treasury operations, etc.) with the data gathered during the technical portion of the assessment, the customer gains a clearer understanding of what gaps reside within their critical processes and workflows, and how those gaps could be leveraged by an attacker to disrupt their business. Unlike a penetration test, which exploits the "path of least resistance" in order to compromise an organization, a risk assessment will consider multiple attack scenarios that assess host-, network, and email-based enterprise security controls.

This approach makes risk assessments an ideal option for businesses that want to gain a more comprehensive understanding of risk as it relates to critical business processes, vulnerabilities, and representative threats.

At the end of the day, however, both methods are valuable for evaluating risk and are necessary in establishing a strong security posture.

### **A Process For Assessing Risk**

To properly evaluate a company's risk, it can help to follow a process. What follows is an example process, noting that not every identified risk will be eliminated:

1. Identify critical business processes, including their physical and electronic interactions with sensitive information.
2. Identify the technical resources (e.g. applications, services, systems) and personnel that support each business process.
3. For each business process, identify host-, network-, and email-based security controls that are appliied to the technical resources. 
4. For each business process, identify administrative security controls for personnel. 
5. For each business process, assess the personnel, processes, and technical resources and identify vulnerabilities and misconfigurations.
6. Develop a test strategy that includes overt/covert attacker tactics, techniques, and procedures (TTPs).
7. Target critical business processes, execute the attacks, and demonstrate the potential for negative impacts.
8. Measure the effectiveness of existing security controls. Document gaps, vulnerabilities, and misconfigurations.
9. Based on the data gathered in steps 1-9, develop a company risk profile. This profile wil be based on exposure and impact.
10. Identify potential remediations for each finding and break these out by near-, mid-, and long-term timelines. Wherever possible, include a level of effort (LOE) and cost.
11. Determine priorities and actions for each remediation.
12. Implement remediations.
12. Repeat the process. Each iteration elevates the defenses to protect against the deeper risks facing the business.

A business can choose any of the below options when a risk is identified in this process. Many times, a risk is kept because the remediation would more negatively impact the business process:
* Accept Risk
* Transfer Risk
* Mitigate Risk
* Eliminate Risk

### **The Complexity of a Risk Profile**

When the risk assessment is complete, the assessor should have a complete perspective into the key processes that enable a business to operate and the risks those processes face. The mind map below details many of the ways that a business can be tied to inflated risks.

For example, a company has compliance risk that is usually managed by having a compliance officer on staff to avoid regulatory fines. Additionally, the company may be a subsidiary to another company, which means threat actors may seek to breach the subidiary systems as a method of attacking the parent. If the parent company stores high-value merchandise and has security controls in the information systems, a compromise of the subsidiary could mean a potential route for compromise. As a result, the subsidiary is at a higher risk because of its relationship to the parent. Likewise, if the subsidiary is participating in financial activities such as payment processing, commercial lending, or custom PII storage, the parent company can be at risk if regulators discover that the data is not stored in a legal, encrypted way. **These regulations apply even if the company is not primarily a financial services company, which means that small, non-compliant subsidiaries put the parent company at financial risk.**

### **Risk Profiles** 

This is not a comprehensive map of risk but should illuminate just how varied risk factors are for a business. Having extensive interviews, tests, and reviews over time help to get this process under control. In reading the web, see each factor listed as another source of risk for the company. For example, any company that has banking activities, even if it is not a bank, has an expanded risk profile through any of those activities it performs.

![](/assets/img/Risk_Assessments/Risk_Profiles.png)

## **Conclusion**

Ultimately, a business must determine an appropriate level of risk for its operations and select solutions that fit its risk appetite. While the entire process can be a challenge to execute exactly right, having a consultant available removes much of the uncertainty. A consultant performing a risk assessment will review processes, engage with the systems, and provide quality solutions. Among those solutions are steps for remediation of immediate concerns, as well as setting up effective controls for prevention, both covered in this series. Additionally, a consultant will be looking for related regulations and the relevant attack narratives that can impact the business. The posts in this series consider the perspective of a company with financial operations such as accounts payable and accounts receivable operations. A deeper explanation of why those are considered is included in the linked posts, but a risk assessment needs to consider factors like these to be complete.

These goals are achieved through a proper risk assessment.

### **BLS Offerings**

One of the primary offerings from BLS are Risk Assessments. BLS works closely with its clients to follow the methods described in this post and crafts ideal security solutions for its clients.

BLS also provides a suite of security services and subscriptions to help organizations develop, implement, and mature their information security program. BLS services and subscriptions have been designed according security best practices and are ideal for any organization looking to build a solid security program that supports GLBA and SOX compliance. Our methodologies and approach have been developed over the last decade as the founding partners secured some of the Nations most sensitive systems. Services and subscriptions include:

* Risk Assessments
* Vulnerability Assessment
* Penetration Testing
* Wireless Assessment
* Web Application Assessment
* Secure Code Review
* Centralized Logging and Alerting
* Developing Bespoke Offensive and Defensive Security Tools and Utilities