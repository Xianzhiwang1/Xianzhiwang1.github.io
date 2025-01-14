+++
date = '2025-01-14T12:51:24-06:00'
draft = false 
title = 'Project 02'
+++

# Project-02 Email without leaving the comfort of one's terminal using Mutt

A quick and easy guide to use [Mutt](http://www.mutt.org/) as your email client. 
Long story short, if we just want to use mutt with, say, our personal gmail account, 
then we could just open up a browser, go to our google account, and create a thing called `app password`,
then go to github and install [mutt-wizard](https://github.com/LukeSmithxyz/mutt-wizard), 
follow the instructions there, and it works pretty much out of the box. 
(Well, assuming one is familiar with the command line...) However, if you happen to have school/work
gmail account that disables the `app password` feature, then you need to go thru some extra steps, 
and let me tell you how I went through these steps (tried and worked for me in April 2024).

Essentially, one could follow the guidence outlined in this 
[article](https://www.redhat.com/sysadmin/mutt-email-oauth2),
but the problem is that as in April 2024, 
the oauth2 access token will expire in one hour, and somehow the script
`mutt_oauth2.py` does not get back a refresh token from the Google API, 
so if we stick with this script, after one hour, the access token expires,
then we need to go thru the authentication process again, meaning:
1. copy paste a url from command line to a browser,
1. login to google account and authorize your own API to access your own account,
1. paste the response code back to the command line.
Then you just gained yourself another hour of access.

Thus, here comes the second solution, using 
[`oauth2.py` from gmail-oauth2-tools](https://github.com/google/gmail-oauth2-tools/blob/master/python/oauth2.py),
and this time, it does return a refresh token, if you use the *first mode of operation* on the command line.
```sh
 oauth2 --user=xxx@gmail.com \
    --client_id=1038[...].apps.googleusercontent.com \
    --client_secret=VWF[...]OplZ \
    --generate_oauth2_token
```
so after hit `Enter`, you would get back a url to paste into a browser, 
then hit `Enter` again, you would need to login and authorize 
the API to access your account, and after that, it will return a url, pasting
that returned url back into the terminal completes the process.

Now, in the terminal, standard input and standard output of getting 
access token and refresh token should look somewhat like this
```sh
$ ./oauth2.py --user=your.gmail --client_id=your.client.id --client_secret=your.client.secret --generate_oauth2_token
To authorize token, visit this url and follow the directions:
  https://accounts.google.com/long.foo.bar.url.string
Enter verification code: code.you.get.back
Refresh Token: your.refresh.token.is.here 
Access Token: your.access.token.is.here 
Access Token Expiration Seconds: 3599
```
After you get that refresh token, you are basically done! 
What you need next is the following lines in your `~/.mutt/muttrc` config file
(or whichever location you put your muttrc file)
```
set editor = "vim"
set charset = "utf-8"
set record = ''

set imap_authenticators="oauthbearer:xoauth2"
set imap_oauth_refresh_command="/you/path/to/oauth2.py --quiet \
    --user=xxx@gmail.com \
    --client_id=1038[...].apps.googleusercontent.com \
    --client_secret=VWF[...]OplZ \
    --refresh_token=1/Yzm6M[...]oyTum4YA"

set smtp_authenticators=${imap_authenticators}
set smtp_oauth_refresh_command=${imap_oauth_refresh_command}
```
Then with some additional config that look more or less like the following,
you will have a completely functional email client right in your terminal!
```
set from = "your@gmail.com"
set realname = "your name"

# Imap settings
set imap_user = "your@gmail.com"
# set imap_pass = "<mutt-app-specific-password>" # do not need this since we have oauth 2

# Smtp settings
set smtp_url = "smtps://your@smtp.gmail.com"
# set smtp_pass = "<mutt-app-specific-password>" # do not need this

# Remote gmail folders
set folder = "imaps://imap.gmail.com/"
set spoolfile = "+INBOX"
set postponed = "+[Gmail]/Drafts"
set record = "+[Gmail]/Sent Mail"
set trash = "+[Gmail]/Trash"
```
Just remember to replace lines with `your` 
to your actual email address and so on.

The next time you want to access email, just type `mutt` on the 
command line and hit `Enter`, and everything will work! (Hopefully!)




