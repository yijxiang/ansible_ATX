## Ansible_ATX

主要是演示Cisco DNA center 与 Ansible互操作。

### Python、Ansible 准备和说明

- 在部署ansible之前，请首先完成python环境的准备，具体方法请参考 [ python on ubuntu ](https://github.com/yijxiang/python-on-ubuntu)
- 并进入Python 虚拟环境。
- Ansible安装请参考 [ dnac_ansible 使用和安装方法 ](https://github.com/yijxiang/python-on-ubuntu/blob/main/dnac_ansible%20%E4%BD%BF%E7%94%A8%E5%92%8C%E5%AE%89%E8%A3%85%E6%96%B9%E6%B3%95.md)


### Ansible 配置

密码、用户名等配置请修改文件 *credentials.yml* ，建议现在测试环境中测试和试用 ansible playbook，如果密码敏感，则需要使用Ansible vault。


### Ansible Playbook 命令使用方法

ansible-playbook -i hosts main.yml

其中 *main.yml* 文件替换为其他playbook.yml即可。


main.yml playbook 实现几个任务：
- 从DNAC中获取交换机的资产信息；
- 保存交换机hostname、uuid 至变量；
- 从DNAC中获取指定的交换机的配置；
- 保存该交换机的配置到backup目录；
- 通过GIT 同步文件至remote github；



