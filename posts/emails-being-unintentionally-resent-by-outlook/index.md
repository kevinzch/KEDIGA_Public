# Emails being unintentionally resent by Outlook


## Issues

Lately, I developed a Python tool that automates sending emails through the Outlook client. After a while, I noticed that sometimes the same email is sent twice.
I went through my code thoroughly but couldn't identify any factors that could be causing this issue.
After some debugging, I realized that the duplicated emails were always sent right after the moment Outlook was opened...

## Solution

I came across a post[^1] incidentally that explained the reason behind the duplicate email sending behavior in the Outlook client. It turns out that if the Outlook client doesn't receive a reply from the Exchange server after sending the first email, it sends a second one to ensure the delivery.

My Python tool was closing the Outlook client shortly after sending the email, which I suspected might be preventing it from receiving a reply from the Exchange server.
To resolve this issue, I added a 30-second waiting period before closing the Outlook client, and the problem disappeared.

[^1]: [【Outlook】送信したメールが意図せず再送される驚きの仕様](https://mosomoso-history.com/%E3%80%90outlook%E3%80%91%E9%80%81%E4%BF%A1%E3%81%97%E3%81%9F%E3%83%A1%E3%83%BC%E3%83%AB%E3%81%8C%E6%84%8F%E5%9B%B3%E3%81%9B%E3%81%9A%E5%86%8D%E9%80%81%E3%81%95%E3%82%8C%E3%82%8B%E9%A9%9A%E3%81%8D/).

*If you have any questions or advice, leave me a comment below and I will try my best to respond!*

