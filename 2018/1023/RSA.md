# 加密
```
root@kali:~# openssl genrsa -out public.pem  //產生私鑰
```
```

Generating RSA private key, 2048 bit long modulus
...............................................................+++
........................+++
e is 65537 (0x010001)
```
```
root@kali:~# openssl rsa -in private.pem -out public.pem -outform PEM -pubout  //產生公鑰
```
```
writing RSA key
root@kali:~# ls
CTF_ex2018  Documents  Music     private.pem  public.pem  Videos
Desktop     Downloads  Pictures  Public       Templates
```
```
root@kali:~# echo dssjakdjskadjkasjdkla > file  //新增資料夾
```
```
root@kali:~# openssl rsautl -encrypto -inkey public.pem -pubin -in file -out file.rsa
rsautl: Option unknown option -encrypto
rsautl: Use -help for summary.
```
```
root@kali:~# openssl rsautl -encrypt -inkey public.pem -pubin -in file -out file.rsa  //加密
```
```
root@kali:~# ls
CTF_ex2018  Documents  file      Music     private.pem  public.pem  Videos
Desktop     Downloads  file.rsa  Pictures  Public       Templates
root@kali:~# cat file.rsa
�X�p��e�	}�(�[욡�p8��@=��o���p��y����c��?�? .Ѭ>����N�D���5�ԫ���C��������V����^��#�}D�#�2���Ɏ���Cj��ng�w��������^>�����~�;�h�D�h�yIQ���I��gP�/�c앉�%�z	d�iG;*amH�L�����oB����Q�~�{�7��(���P)�!2�E�y|���ƚ�)����XG���g}�)root@kali:~# 
```
```
root@kali:~# openssl rsautl -decrypt -inkey private.pem -in file.rsa -out file.sol  //解密
```
```
root@kali:~# cat file.sol 
dssjakdjskadjkasjdkla
root@kali:~# cat file
dssjakdjskadjkasjdkla
```
