# Bug Bounty Definition
A bug bounty program is a crowdsourcing initiative that rewards individuals for finding and reporting security vulnerabilities in software products, websites, and other digital assets. These programs are typically run by companies or organizations to identify and fix security issues before they can be exploited by malicious actors. Bounty rewards can vary depending on the severity of the vulnerability and the company's budget.
# Asset Types
- Social Sites and Applications
- General Web Applications
- Mobile Applications (Android, iOS, and Windows)
- APIs
- Source Code and Executables
- Hardware and IoT

# Bug Bounty Platforms

Bug bounty programs can be hosted by companies in two ways: through bug bounty platforms or independently hosted websites. Bug bounty platforms, such as HackerOne and Bugcrowd, provide logistical assistance for tasks like payment and communication, and offer help managing incoming reports. They also provide a way for companies to gauge a hacker's skill level via hacker statistics and reputation. From the hacker's perspective, bug bounty platforms provide a centralized place to submit reports and offer a seamless way to get recognized and paid for findings. However, some hackers avoid bug bounty platforms because they dislike how those platforms deal with reports, and programs on platforms can be crowded. Ultimately, the decision to participate in a bug bounty program on a platform or independently hosted website depends on personal preference.

# How to choose the right program 

When choosing a bug bounty program, it's important to pick one that you can succeed in from the start. Beginners should look for underpopulated programs to avoid competition, such as unpaid programs or programs with large scopes. Programs with fast response times are also recommended to prevent frustration and get feedback as soon as possible. Additionally, it's important to consider the reputation of the program and gather information about a company's process through its disclosed reports and other hackers' experiences. Pick programs that will be supportive while you are still learning and that will reward you for the value that you provide.

# Writing Good Reports

### 1- Craft a Descriptive Title

The title should answer questions such as what the vulnerability is, whether it's a well-known vulnerability type, and where it was found on the target application. A descriptive title like "IDOR on https://example.com/change_password Leads to Account Takeover for All Users" gives the security engineer reading the report a good idea of the content that will be discussed in the rest of the report.

### 2- Provide a Clear Summary
The next step in writing a good vulnerability report is to provide a clear summary. This section includes all the relevant details that weren't able to be communicated in the title, such as the HTTP request parameters used for the attack and how the vulnerability was found. A good report summary is clear and concise, containing all the information needed to understand the vulnerability, including what the bug is, where it's found, and what an attacker can do when it's exploited. An effective example of a report summary is provided above.

### 3- Include a Severity Assessment

When writing a vulnerability report, it's important to include an honest assessment of the bug's severity. This helps the security team prioritize which vulnerabilities to fix first and ensures that critical vulnerabilities are taken care of right away. A severity assessment can be communicated using a scale such as low, medium, high, or critical. It's important to customize the assessment to fit the client's business priorities and to use the rating scale of a bug bounty platform if unsure. Providing an accurate assessment of severity will make everyone's lives easier and contribute to a positive relationship between you and the security team.

- Low severity: An open redirect that can be used only for phishing.
- Medium severity: A cross-site request forgery (CSRF) on a sensitive action such as password change.
- High severity: An open redirect that can be used to steal OAuth tokens.
- Critical severity: A SQL injection leading to remote code execution (RCE) on the production server.

### 4 - Give Clear Steps to Reproduce

When writing a vulnerability report, it's important to provide clear and comprehensive steps to reproduce the vulnerability. This includes all relevant setup prerequisites and details, assuming that the engineer on the other side has no knowledge of the vulnerability and doesn't know how the application works. A good report should provide step-by-step instructions that are explicit and comprehensive, such as the example provided above. By providing many relevant details, you can avoid any misunderstanding and speed up the mitigation process.
**example of a bad report**
- List itemLog in to the site and visit https://example.com/change_password.
- List itemClick the Change Password button.
- List itemIntercept the request, and change the user_id parameter to another
user’s ID.

**example of a better report**

- List itemMake two accounts on example.com: account A and account B.
- List item Log in to example.com as account A, and visit https://example.com/
change_password.
- List item Fill in the desired new password in the New password field, located at
the top left of the page.
- List item Click the Change Password button located at the top right of the page.
- List item Intercept the POST request to https://example.com/change_password and
change the user_id POST parameter to the user ID of account B.
- List itemYou can now log in to account B by using the new password you’ve
chosen.

### 5- Provide a Proof of Concept

When reporting more complex vulnerabilities, it's helpful to provide a proof-of-concept (POC) file, such as a video, screenshots, or photos documenting the exploit. For example, for a CSRF vulnerability, you could include an HTML file with the CSRF payload embedded, or for an XML external entity attack, include the crafted XML file that you used to execute the attack. POC files save the security team time because they won't have to prepare the attack payload themselves. You can also include any crafted URLs, scripts, or upload files you used to attack the application.

### 6- Describe the Impact and Attack Scenarios
To help the security team understand the potential impact of a vulnerability, it's important to provide a plausible attack scenario. This section is different from the severity assessment, which describes the severity of the consequences of an attacker exploiting the vulnerability. The attack scenario explains what those consequences would actually look like. A good impact section should illustrate how an attacker can realistically exploit a bug, taking into account any mitigating factors as well as the maximum impact that can be achieved. It should never overstate a bug's impact or include any hypotheticals. By putting yourself in a malicious hacker's shoes, you can give the client company a realistic sense of the worst-case scenario, which will help them prioritize the fix internally and determine if any additional steps or internal investigations are necessary.

### 7- Recommend Possible Mitigations

When reporting a vulnerability, it's helpful to recommend possible steps the security team can take to mitigate the vulnerability. This can save the team time when researching mitigations. However, it's important to only propose fixes if you have a good understanding of the root cause of the issue. Internal teams may have more context and expertise to provide appropriate mitigation strategies applicable to their environment. If you're not sure what caused the vulnerability or what a possible fix might be, it's best to avoid giving any recommendations to avoid confusing the reader. A possible mitigation that could be proposed is to validate the user's user_id parameter within the change password request to ensure that the user is authorized to make account modifications. Unauthorized requests should be rejected and logged by the application. While technical details of the fix are not necessary, providing a direction for mitigation can be helpful.

### 8- Validate the Report

When submitting a vulnerability report, it's important to validate the report to minimize the possibility of submitting an invalid report. This involves going through the report one last time to ensure that there are no technical errors or anything that might prevent the security team from understanding it. It's also important to follow the steps to reproduce to ensure that they contain enough details and to examine all POC files and code to make sure they work. By validating the report, you can ensure that it is clear, accurate, and effective in communicating the vulnerability to the security team.

# Building a Relationship with the Development Team

### Understanding Report States :

after submiting the report, the security team classify it into a report state showcasing the current state of your report (mitigation process) these are the different report states that u might encounter:
- Need More Information
- Informative (the security team dont think the bug is severe enough so they wont fix it)
- Duplicate (another bug bounty hunter found the bug first)
- Triaged (the security team will fix the issue and give you the bounty)
- Resolved
### Dealing with Conflict

### Building a Partnership

### Understanding Why You’re Failing
- Why You’re Not Finding Bugs:
1. You Participate in the Wrong Programs
2. You Don’t Stick to a Program
3. You Don’t Recon
4. You Go for Only Low-Hanging Fruit (dont just use vulnerability scanner)
5. You Don’t Get into Private Programs.

- Why Your Reports Get Dismissed:
1. You Don’t Read the Bounty Policy
2. You Don’t Put Yourself in the Organization’s Shoes
3. You Don’t Chain Bugs
4. You Write Bad Reports
-  What to Do When You’re Stuck
1. Take a Break!
2. Build Your Skill Set
3. Gain a Fresh Perspective
