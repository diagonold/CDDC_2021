

# Tips when playing CTF

- Start from the simple solutions
- Investigate the problem and ideate possible solutions
- Document what you have and have not tried
- If you are stuck for way too long, ask for help or ideate with team
- Learn as much and have fun!!

# Challenge 1: Access
AccessKey		38	200	Hint #1	 Submit
Your next target doesn’t look so interesting, but maybe there is a hidden secret somewhere that can be used as the access key

Target URL: http://122.248.246.76/YY67RIGZ

## Hints
  
## Possible Approaches (Include those that you have tried too)


unescape is a url decoder

var pass = unescape("unescape%28%22String.fromCharCode%252867%252C68%252C68%252C67%252C50%252C49%252C123%252C95%252C32%252C68%252C101%252C48%252C98%252C102%252C117%252C36%252C99%252C97%252C116%252C101%252C100%252C45%252C70%252C33%252C97%252C71%252C95%252C125%2529%22%29");


the input to this is this

unescape("String.fromCharCode%2867%2C68%2C68%2C67%2C50%2C49%2C123%2C95%2C32%2C68%2C101%2C48%2C98%2C102%2C117%2C36%2C99%2C97%2C116%2C101%2C100%2C45%2C70%2C33%2C97%2C71%2C95%2C125%29")

the input for unescape is 

string.fromCharCode(67,68,68,67,50,49,123,95,32,68,101,48,98,102,117,36,99,97,116,101,100,45,70,33,97,71,95,125)

the above function returns a string

console.log(String.fromCharCode(67,68,68,67,50,49,123,95,32,68,101,48,98,102,117,36,99,97,116,101,100,45,70,33,97,71,95,125))


##  Flag

CDDC21{_ De0bfu$cated-F!aG_}






# Challenge 2: Integrity

We got an  intel that Cyber-Bots develop a new integrity system. The server will be used further for malicious proposes, and we must stop it. Try to find any manipulation that can be done by the client-side of it.

Target URL: http://122.248.246.76/8NR7Z67K


## Hints
  
## Possible Approaches (Include those that you have tried too)

Client-side attack

break integrity

`<script>alert(1);</script>` works. susceptible to XSS attacks
 
when password and login is entered a statement is returned whether that exists or not

Tried admin and admin, they said the password for adming is incorred

username admin exist in the system



Trying new xss attacks on the password
- `<script>alert(1);</script>` works but the one below does not
- `<script>alert(document.cookie);</script>`
- the xss atttack is only possible on the username


I think the attack is meant to use xss?

- How can we use XSS to access the password or get access to the site?


In the sources section, there is a comment 

`/*John, the next generation platform is going to be deployed next week. Make sure to review all the backup files in "/stage-03-03/".*/`

This means that there is a backup folfer called stage-03-03

I checked this and it was an availabe directory

They said that it will be deployed bext week. 

am stuck here
