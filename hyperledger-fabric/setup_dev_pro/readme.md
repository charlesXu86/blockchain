ֱ��ʹ���Ѿ����úÿ���������box
-----------------------
1. �ο�[setup_dev](../setup_dev)��1~5����
2. ����fabric.box (https://pan.baidu.com/s/1mi9VINu)��
   Ȼ��ִ�У�
  ```Bash
  vagrant.exe box add fabric.box  --name fabric
  ```
3. �޸�[Vagrantfile](./Vagrantfile):
  ```diff
  -Vagrant.configure("2") do |config|
  -   config.vm.box = "ubuntu/xenial64"            
  +Vagrant.configure("2") do |config|
  +   config.vm.box = "fabric"
  ```
  ע�͵�setup.sh�ĵ��ã���ʱ����Ҫ��װ����Ĺ��ߣ�fabric.box�Ѱ�����ع���
  ```diff
  cd #{SRCMOUNT}/devenv
  -./setup.sh
  ```
  ���޸ĺ��Vagrantfile���Ƶ�fabric/devenvĿ¼����ԭ���ļ�

4. ��fabric/devenvĿ¼ִ�У�
  ```Bash
  vagrant.exe up
  ```
5. ��fabric/devenvĿ¼ִ�У�
  ```Bash
  vagrant.exe ssh
  ```


�ʺ�ִ�����setup��ͬѧ
-----------------------
  
�����setup���ػ���֮��ִ�У�
  ```Bash
  vagrant.exe ssh
  ```

��������ͼƬ��˵�����ػ�����һ��С���⣺

![issue-1](https://github.com/shanlusun/blockchain/blob/master/hyperledger-fabric/setup_dev_pro/images/issue-1.PNG "issue-1")

�������googleһ�»ᷢ��[Hyperledger�ٷ���˵��](https://github.com/hyperledger-archives/fabric/wiki/Troubleshooting-devenv-provisioning "Hyperledger�ٷ�˵��")
���ǲ�û�и������������
>���������ʾ��**Ӱ��**��
>>�޷���fabricĿ¼ִ��make docker��makeһЩ���������peer��order��tools��

----------
[setup_dev](../setup_dev)�����п�����һЩ���⣺
��ִ�е�6����vagrant.exe up�����п��������Ĵ�����ʾ��

1. ��ʾubuntu/xenial64 ����timeout
2. ��װdocker-ce������repository��ַ����ʧ�ܻ�timeout
3. zookeeper�汾3.4.9��kafka�汾0.9.0.1�Ѿ���������

��ν����
----------
>**ע��**��
>>��ǰĿ¼�Ѿ��ṩ[Vagrantfile](./Vagrantfile)��[setup.sh](./setup.sh)������ֱ�Ӹ��Ƶ�fabric/devenvĿ¼��ʹ�ã�

1. ʹ��Ѹ��ֱ������һ�����õ�ubuntu�������������ѡ��https://vagrantcloud.com/hyperledger/boxes/fabric-baseimage/versions/0.3.0/providers/virtualbox.box
  �������ļ�������Ϊvirtualbox.box��Ȼ��ִ�У�
  ```Bash
  vagrant.exe box add virtualbox.box  --name fabric
  ```
  �޸�[Vagrantfile](./Vagrantfile):
  ```diff
  -Vagrant.configure("2") do |config|
  -   config.vm.box = "ubuntu/xenial64"            
  +Vagrant.configure("2") do |config|
  +   config.vm.box = "fabric"
  ```
2. �޸�[setup.sh](./setup.sh)�����Ӱ�����repository��
  ```Bash
  add-apt-repository "deb [arch=amd64] http://mirrors.aliyun.com/docker-ce/linux/ubuntu
$(lsb_release -cs) stable"
  ```
3. �޸�[setup.sh](./setup.sh)������zookeeper��kafka�İ汾�����ڵ��°汾

���⽨��GO�İ汾������1.9.2��Node�İ汾������8.9.0
���ϸĶ�����֮�����ִ�У�
```Bash
vagrant.exe provision
```
�����ִ�У�
```Bash
vagrant.exe ssh
```
�������½���˵����һ�й���������

![success-1](https://github.com/shanlusun/blockchain/blob/master/hyperledger-fabric/setup_dev_pro/images/success-1.PNG "success-1")

