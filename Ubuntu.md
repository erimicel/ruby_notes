## How to Install openVpn Ubuntu 20

```bash
Sudo -s => to switch root
apt update
apt upgrade
apt install ca-certificates wget net-tools gnupg
wget -qO - https://as-repository.openvpn.net/as-repo-public.gpg | apt-key add -
echo "deb http://as-repository.openvpn.net/as/debian focal main">/etc/apt/sources.list.d/openvpn-as-repo.list
apt update
apt install openvpn-as
```

Get openvpn user pw: cat /usr/local/openvpn_as/init.log | grep 'To login'

In the admin dashboard, you can add users under User Management. Users can access the OpenVPN server at https://<your-ip>:943 or https://<your-domain>:943 where they can login and download the client software for their device. Supported operating systems include Mac, Windows, iOS, Android, and Linux.
