🌐 **Today's Focus: The juc.edu.bd Website** 🌐

I embarked on exploring the juc.edu.bd website, adhering to the guidelines set by my instructor for a vulnerability assessment task. My first step involved conducting a WHOIS lookup to ascertain the website's origins.

![Whois](websites/edubd/img/image.png)

Upon discovering that this is a Bangladeshi website, I delved into researching information-oriented aspects like domain validation, which is valid up until January 16, 2024.

![Domain Validation Information](websites/edubd/img/image-1.png)

Further research using Wappalyzer revealed that the website is built using PHP.

![PHP Usage Details](websites/edubd/img/image-2.png)

Examining the website thoroughly, I focused on the login page. Utilizing SQLMap, I identified several vulnerabilities.


![Vulnerability 1](websites/edubd/img/image-3.png)

![Vulnerability 2](websites/edubd/img/image-4.png)

After further research, my curiosity led me to a file named `results-01022024_0740am.csv`. In this file, I found a target link.

![Target](websites/edubd/img/target.png)

Upon opening this link, I was directed to a specific webpage.

![Website](websites/edubd/img/website.png)

Suspecting the presence of a database service, I conducted research using SQL. The command I used was:

```
python3 sqlmap.py https://www.juc.edu.bd/page.php?id=1,GET,id,BTU --dbs
```

This led me to discover the parameter-related vulnerabilities in the assignment.

![dbs1](websites/edubd/img/dbs.png)

![dbs2](websites/edubd/img/dbs2.png)

![dbs3](websites/edubd/img/dbs3.png)

Although we have fetched data, we will not misuse it. Now, let's discuss how we can remedy this SQL injection and enhance the security of this website.

1. **Immediate Mitigation:**
   - Disable the vulnerable parameter: Temporarily prevent access to the id parameter in the page.php file. This can be done by removing it from the URL or filtering it out in the server-side code.

    - Implement input validation and sanitization:
        - Validate all user-supplied data to ensure it conforms to expected formats and lengths.

        - Sanitize data by escaping or removing special characters that could be used in SQL injection attacks.
    - Apply a Web Application Firewall (WAF): If possible, deploy a WAF to filter malicious traffic and block attempts to exploit the vulnerability.

2. **Code Fix:**
    - Identify the root cause: Inspect the code that handles the id parameter to determine how it's being incorporated into SQL queries.

    - Use prepared statements with parameterized queries: This approach separates SQL syntax from user input, preventing injection attacks. Adopt it for all dynamic queries.

    - Employ escaping functions: If prepared statements aren't feasible, meticulously escape user input before incorporating it into SQL queries.


3. **Penetration Testing:**
   - Conduct thorough penetration testing: Engage a security professional or use tools like SQLMap to uncover any additional vulnerabilities.

   - Address all identified vulnerabilities promptly: Prioritize fixes based on severity.

4. **Continuous Monitoring:**
   - Implement a vulnerability management program: Regularly scan for new vulnerabilities and apply patches promptly.
   
   - Stay informed: Keep abreast of security updates for the web application framework and database.


5. **Additional Recommendations:**
    - Upgrade the web application and database: If possible, update to the latest versions, as they often contain security fixes.
    - Review code for other vulnerabilities: Conduct a comprehensive security review to identify and address potential weaknesses.

    -  Educate developers on secure coding practices: Raise awareness about SQL injection and other web application vulnerabilities to prevent similar issues in the future.


6. **Remember:**
    - Ethical disclosure: If you're not the owner or administrator of the juc.edu.bd website, contact them responsibly to disclose the vulnerability.
    - Avoid sharing sensitive information: Refrain from publicly disclosing details that could assist malicious actors.


7. **cyber city:**
   - we discuss this vulnerblity prevent in future cyber city website and the payloads we give the user fix it cyber city will take responsblity to fix the vulnerblity in future 
