# Input

Write a bug bounty report about a reflected XSS. The vulnerable URL is https://example.com/?url="><script>alert(1)</script><!--

# Answer

Title: Reflected XSS on example.com

Affected URL: [https://example.com/?url=">](https://example.com/?url=%22%3E)<script>alert(1)</script><!--

Description:

I discovered a reflected cross-site scripting (XSS) vulnerability on the example.com website. The issue occurs when the `url` parameter in the query string is set to a string that contains JavaScript code. This code is then reflected in the website's HTML output, allowing an attacker to execute arbitrary JavaScript in the context of the website.

To reproduce the issue, follow these steps:

1.  Visit the following URL in a web browser: [https://example.com/?url=">](https://example.com/?url=%22%3E)<script>alert(1)</script><!--
2.  Observe that a JavaScript alert box appears, indicating that the XSS payload was executed successfully.

Impact:

This vulnerability allows an attacker to execute arbitrary JavaScript code in the context of the website. This can be used to steal sensitive information from users, such as login credentials or other personal information. It can also be used to perform actions on behalf of the user, such as making unauthorized purchases or changing their account settings.

Recommendation:

To fix this issue, the website should properly escape or encode user-supplied data before reflecting it in the HTML output. This will prevent attackers from injecting malicious code into the website.

Timeline:

-   2021-12-02: Vulnerability discovered
-   2021-12-02: Report submitted to website owner
-   2021-12-03: Website owner responds and confirms the issue
-   2021-12-03: Website owner implements a fix to prevent the issue from occurring
-   2021-12-03: Confirmed that the fix is effective

Credits:

This vulnerability was discovered by \[Your Name\].