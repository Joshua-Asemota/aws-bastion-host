##This ssh setup helped me simplify the proxy jump, because each of the hosts uses a separate key pair.

Host *
  AddKeysToAgent yes
  UseKeychain yes


Host bastion_host
    HostName 13.51.85.56
    User ubuntu
    IdentityFile ~/.ssh/bastion_host_kp.pem
    IdentitiesOnly yes

Host private_host
    HostName 10.0.0.210
    User ubuntu
    IdentityFile ~/.ssh/private_subnet_kp.pem
    IdentitiesOnly yes
    ProxyJump bastion_host

