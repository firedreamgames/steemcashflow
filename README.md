## SteemCashFlow - A Steem.js project to see cash flow on Steemit
#### About [SteemCashFlow](https://steemcash.neocities.org)
SteemCashFlow is a tool inspired by the [SteemViz](https://steemviz.com/pendingpayouts) tool created by @ausbitbank, that is used to show the pending payouts.

Additional to SteemViz, with the developed features you can see :
* Payouts day by day

![image.png](https://res.cloudinary.com/hpiynhbhq/image/upload/v1521281513/vvnvzq7w9ke5nj5mu29r.png)

* Exact time ( UTC ) of each pay-out

![image.png](https://res.cloudinary.com/hpiynhbhq/image/upload/v1521281557/tr0mkgbdthq1olv2ytcu.png)

* See your posts and comments even with "zero payout"

![image.png](https://res.cloudinary.com/hpiynhbhq/image/upload/v1521281711/o5cydortqbn5nwygwphw.png)


* Total payout in SBD

![image.png](https://res.cloudinary.com/hpiynhbhq/image/upload/v1521281884/xegqyolfy84zera51sw1.png)

#### Usage
Go to the web-site https://steemcash.neocities.org

Enter your steemit name in the input box and press "CALCULATE" button.

![image.png](https://res.cloudinary.com/hpiynhbhq/image/upload/v1521283813/sqgtih8qlmkhyrzmprsh.png)


#### Technical Details

[SteemCashFlow](https://steemcash.neocities.org) is opensource one page HTML coded with JavaScript using steem.js API.
The full source code is in the GitHub as : https://github.com/firedreamgames/steemcashflow/blob/master/index.html

The main functions used :
* SEARCH()

Initial function. 
Extract the posts and comments 

![image.png](https://res.cloudinary.com/hpiynhbhq/image/upload/v1521282531/si9b1ndonilnuaiagwrz.png)

Merges the posts and comments in one array, send the array to MATRIX(res) function.

Thanks to @stoodkev for the [tutorial](https://steemit.com/utopian-io/@stoodkev/steem-js-for-dummies-5-getting-user-s-last-post) on the *getDiscussionbyAuthorBeforeDate* using.

This really made life easier.

* MATRIX(res)

![image.png](https://res.cloudinary.com/hpiynhbhq/image/upload/v1521283076/glyojfq9rz4y9dn5weca.png)


This function is where we arrange our matrix according to the payment date.
We eliminate the already paid posts and comments and send the results to *function see-sbd(permlink,date,sbd)*

* SEE_SBD(permlink, date, sbd)

This fuction may not be necessary but, if the post or comment is edited, we may have a duplicate result.
This function is put to delete if there is any duplication because of edited posts or comments.

![image.png](https://res.cloudinary.com/hpiynhbhq/image/upload/v1521283392/k6kgxun3o9lxou7byywl.png)

The output is sent to function  final(permlink, payout, paytime)

* FINAL (permlink, payout, paytime)

This is the final function where we calculate,sort and write the data on innerHTML of div's.

### Roadmap
The project is a tool to predict the cash flow for the posts and comments.
It can be used by all Steemians to predict and regulate their Steem income daily, even hourly.
This one page is planned to be be merged with seperate other tools to create a toolbox.
### Connect
@FireDream - Steemit

@firedream#3528 - Discord
