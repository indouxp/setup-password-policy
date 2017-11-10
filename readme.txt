CentOS 7.3のパスワードポリシーのセットアップ

1. c73
  0 171110-145452 indou@c73:~:$ mkdir ~/.ssh
  0 171110-145515 indou@c73:~:$ chmod 700 ~/.ssh
  0 171110-145521 indou@c73:~:$ touch ~/.ssh/authorized_keys
  0 171110-145533 indou@c73:~:$ chmod 600 ~/.ssh/authorized_keys
  0 171110-145538 indou@c73:~:$ vi ~/.ssh/authorized_keys
  0 171110-145540 indou@c73:~:$ visudo

2. t3600
  0 171110-150126 indou@t3600:setup-password-policy:$ ansible c73 -m ping -i hosts -u indou --private-key=/home/indou/.ssh/id_rsa
  Enter passphrase for key '/home/indou/.ssh/id_rsa':
  192.168.0.76 | SUCCESS => {
      "changed": false,
      "ping": "pong"
  }
  0 171110-150238 indou@t3600:setup-password-policy:$

  0 171110-172901 indou@t3600:~:$ eval `ssh-agent`
  Agent pid 4330
  0 171110-172947 indou@t3600:~:$ ssh-add ~/.ssh/id_rsa
  Enter passphrase for /home/indou/.ssh/id_rsa:
  Identity added: /home/indou/.ssh/id_rsa (/home/indou/.ssh/id_rsa)
  0 171110-173001 indou@t3600:~:$ 
  
