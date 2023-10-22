## Post #1
- Username: theultramage
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 07, 2015 6:21 pm
- Post datetime: 2015-10-07T11:00:52+00:00
- Post Title: forum mail server uses SSLv2

I had trouble registering because the activation e-mail would not arrive. The immediate reason was a "no shared cipher" protocol disagreement.
The problem is that your mail server responds to the STARTTLS opportunistic encryption offer using the ancient 1995 SSLv2 protocol and its cipher suite, which is [banned](https://tools.ietf.org/html/rfc6176) since 2011 and blocked by default on Postfix. It retried several times, but it did not try ignoring the STARTTLS offer and sending plain text. Eventually I temporarily disabled crypto support to get the mail delivered.

In the FAQ section, a lot of the advice says "contact a board administrator". But it seems there is no page with actual contact information, the list of administrators is available to logged in users only, and the administrators' profiles do not list an e-mail address. So if I'm in a situation where I can't access my account, there's no means of asking for support.
