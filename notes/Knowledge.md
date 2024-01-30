---
id: cbdsdoplo1hlzwkmb2asb50
title: Knowledge Base
desc: ''
updated: 1706646347527
created: 1706640249443
---
## How to Setup Maestro and Buffalo Gold on Windows
  
### Setting up SSH

1. Generate a new SSH key:

   <code>
   $ ssh-keygen -t rsa -b 4096 -C "&lt;your email&gt;"
   </code>

   You will see the message "Generating public/private rsa key pair." and complete the SSH key generation process.

2. Copy the public key:

   - For Mac:
     <code>
     pbcopy &lt; ~/.ssh/id_rsa.pub
     </code>

   - For Linux (Option 1):
     <code>
     xclip -sel clip &lt; ~/.ssh/id_rsa.pub
     </code>

   - For Linux (Option 2):
     <code>
     cat ~/.ssh/id_rsa.pub
     </code>

   - For Windows:
     <code>
     cat ~/.ssh/id_rsa.pub | clip
     </code>

3. Add to Github:

   - Log in to GitHub.
   - Go to <em>Settings</em> → <em>SSH and GPG keys</em> → <em>New SSH key</em>.
   - Paste your public key into the provided box.
   - Once the key is created, configure the SSO and allow the appropriate organizations. 

4. Test:

    Test the connection with:
   <code>
   ssh -T git@github.com
   </code>

5. Open your preffered Git Client and you configure SSH Key. Each client is slightly different and might require different steps. It is recommended that you search how the client needs to be configured. 

6. Once this is completed, you will have access to the repos and will be able to clone using the SSH address. 


### Downloading Repositories and Creating Symlinks

<p>Follow the tutorial <a href="https://aristocratdd.atlassian.net/wiki/spaces/ALT/pages/2127036690/Maestro+GDK+Development+Environment">here</a> to download and set up the repositories correctly:</p>
This tutorial assumes that you are able to open the Unity project without running into issues with Git. If you do run into issues, the next step has instructions on how to fix those issues. 
  

### Opening the Unity Project BuffaloGoldUnity
Use the editor version mentioned in the instructions of the previous step. 
Upon opening you will be prompted to choose an git account to use to access UPM packages. 
You can choose an account or add a new one. 
If you have 2FA turned on for your GitHub account. You must make a personal token and use that token to authenticate. 
<details>
<summary> How to create a personal token </summary>
<ol>
  <li>Verify your email address, if it hasn't been verified yet.</li>
  <li>In the upper-right corner of any page, click your profile photo, then click <strong>Settings</strong>.</li>
  <li>In the left sidebar, click <strong>Developer settings</strong>.</li>
  <li>In the left sidebar, under <strong>Personal access tokens</strong>, click <strong>Tokens (classic)</strong>.</li>
  <li>Select <strong>Generate new token</strong>, then click <strong>Generate new token (classic)</strong>.</li>
  <li>In the "Note" field, give your token a descriptive name.</li>
  <li>To give your token an expiration, select <strong>Expiration</strong>, then choose a default option or click <strong>Custom</strong> to enter a date.</li>
  <li>Select the scopes you'd like to grant this token. To use your token to access repositories from the command line, select <strong>repo</strong>. A token with no assigned scopes can only access public information.
  <li>Click <strong>Generate token</strong>.</li>
  <li>Optionally, to copy the new token to your clipboard. 
  <li>To use your token to access resources owned by an organization that uses SAML single sign-on, authorize the token. 
</ol>
</details>

### Issues you might run into
The Buffalo game might be stuck on the loading screen and you might see an error about SSL certificates. Most IDE will prompt you to setup the certificates when you run the backend on ``localhost`` for the first time. 

