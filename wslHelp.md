# wsl 远程vscode

1.设置 `/etc/ssh/sshd_config`

`
Port 6666
ListenAddress 0.0.0.0
`

2.在powershell 设置转发

`
netsh interface portproxy show all
0.0.0.0 9999 localhost 6666

netsh interface portproxy add v4tov4 listenport=9999 listenaddress=0.0.0.0 connectionport=6666 connectaddress=localhost
`
