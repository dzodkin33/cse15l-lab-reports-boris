# Lab Report 3

[Back to main page](index.md)

During weeks 5 and 6, we learned how to better our experience when working with remote machines.

---

## Streamlining ssh Configuration

I didn't have a config file so I created oune using `touch` command.

![Creating Config](/pictures/Lab-3-pics/ssh-config/create-config.png)

Then, I edited the config file. Here how the last version looks like.

![Edited Config](/pictures/Lab-3-pics/ssh-config/config-file.png)

Then, I tested the config file by trying to log in into my remore machine.

![Login with Config](/pictures/Lab-3-pics/ssh-config/ssh-login.png)

It worked! Now I had to test if I could move a file into my remote machine using the config file. I created a file that I was going to move.

![Test File](/pictures/Lab-3-pics/ssh-config/test-file1.png)

Then, I opened a new terminal window and moved this file using a following command: `scp Test.java ieng6:~/`.

![Move Test File](/pictures/Lab-3-pics/ssh-config/scp-move.png)

Now, I had to check if the file `Test1.java` was move to my remote machine. I login into my remote machine and run `ls` command to see if `Test1.java` is present. Surely enough it was there.

![Check Test File](/pictures/Lab-3-pics/ssh-config/ssh-check.png)

## Setup Github Access from ieng6

I decided to have a ceparate public key - private key pair, so I generated one for my local machine and one of my remote one.

![Generating Key Pair](/pictures/Lab-3-pics/github-access/rsa-git.png)

Thus as you can see, both of my public and private keys at my local machine are stored at `.ssh` directory.

Then, I copied and pasted the public key located at `id_rsa_github.pub` and added it to my github account.

![Pub Github SSH](/pictures/Lab-3-pics/github-access/git-ssh-local.png)

I also edited the config file so that I could use different SSH pairs on my machine.

![Github SSH](/pictures/Lab-3-pics/github-access/git-config.png)

Then I checked if it works by trying to log into my girhub with ssh.

![Git ssh login](/pictures//Lab-3-pics/github-access/local-acess.png)

## Copy whole directories with scp -r

Let's open markdown-parse directory.

![Open](/pictures/Lab-3-pics/scp-r/cd.png)

Using `scp -r .` command, move the entire directory.

![Move](/pictures/Lab-3-pics/scp-r/scp-move.png)

Now let's log into a remote machine and test it out.

![Scp run remote](/pictures/Lab-3-pics/scp-r/scp-run.png)

I made one test to fail deliberatly, so the `scp -r` works.

Now, let's try optimizing this process. This is a command I came up with:

![Error](/pictures/Lab-3-pics/scp-r/scp-gg.png)

Although we managed to move a file, we recived a randomn error.

![Error](/pictures/Lab-3-pics/scp-r/error-1.png).