### Rootless机制下即使是root用户对以下目录也没有“写和执行”的权限

1. /System
2. /bin
3. /sbin
4. /usr (except /usr/local)

### 禁止Rootless
1. csrutil enable --without kext (Enable SIP and allow installation of unsigned kernel extensions)
2. csrutil enable --without fs   (Enable SIP and disable filesystem protections)
3. csrutil enable --without debug(Enable SIP and disable debugging restrictions)
4. csrutil enable --without dtrace(Enable SIP and disable DTrace restrictions)
5. csrutil enable --without nvram(Enable SIP and disable restrictions on writing to NVRAM)

### 参考
1. [link1](http://apple.stackexchange.com/questions/208478/how-do-i-disable-system-integrity-protection-sip-aka-rootless-on-os-x-10-11)
