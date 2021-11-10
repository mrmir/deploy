[Original from LightningFF/deploy's wiki](https://github.com/LightningFF/deploy/wiki/Deploy-with-Capistrano-&-Github-Actions-on-Git-merge#setup)

Steps:

1. Copy code here Github Actions Capistrano and save it in your repo under: .github/workflows/deploy.yml
2. Replace *example.com with your server address
3. ssh to your server: ssh user@host
4. cd into the ssh directory: cd ~/.ssh/
5. Generate an ssh-key: ssh-keygen -t rsa -b 4096 -C "user@email.com"
6. When asked for the filename, use github-actions rather than the default id_rsa
7. Make sure no passphrase is used
8. Authorize the public key for your server: cat github-actions.pub >> authorized_keys
9. On your project's Github repository, go to Settings -> Secrets -> New Repository Secret
10. Set SSH_KEY as name
11. Copy text from github-actions and paste into value
12. Repeat previous step to store another key
13. Set SSH_HOST as name
14. Set value to be the IP address of your server (i.e. 11.22.33.44)
15. Push deploy.yml code to your repo.

That's it! Now anytime you push changes to your main branch, capistrano is automatically run and deploys code to your servers.

