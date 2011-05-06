Bash script for automatically create remote git repositories.
=============================================================

Useful for "backup" and control some-files. e.g. /etc
-----------------------------------------------------


On server side:

    # useradd -m git
    # passwd git # optional. for key exchange only
    # su - git
    $ mkdir .ssh

On client side (/etc for example):

    # git-backup-addkey git@<server>
    # cd /etc
    /etc# git init
    /etc# git add .
    /etc# git commit -a -m "Initial"
    /etc# git remote add origin git@<server>:~/etc-git/`hostname`
    /etc# git push origin master # optional. by cron must exec etc-git.cron
