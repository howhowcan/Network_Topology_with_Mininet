# Network Topology with Mininet

This repository is lab for NCTU course "Introduction to Computer Networks 2018".

---
## Abstract

In this lab, we are going to write a Python program which can generate a network topology using Mininet and use iPerf to measure the bandwidth of the topology.

---
## Objectives

1. Learn how to create a network topology with Mininet
2. Learn how to measure the bandwidth in your network topology with iPerf

---
## Execution

> TODO: 
> * Describe how to execute your program
> * Show the screenshot of using iPerf command in Mininet    
> * To execute my program, you must have an linux enviroment with Mininet installed in your machine.
1. Clone my repo by `git clone https://github.com/nctucn/lab2-howhowcan.git Network_Topology`
2. Start the service of Open vSwitch by `sudo service openvswitch-switch start`
3. Check the functionality of Mininet: `sudo mn`
4. If Mininet functions correctly, using the exit command `exit` in CLI to exit
5. Clean up all the connections: `sudo mn -c` 
6. Change to the directory: `cd ./Network_Topology/src/`
7. Run the code:   
   * Change to the executable mode of topology.py   
   `sudo chmod +x topology.py`   
   * Run topology.py   
   `sudo ./topology.py`    
8. If succeed, you will go into CLI mode. Then, execute the following command to get the result:   
   `mininet> h2 iperf -s -u -i 1 > ./out/result &`    
   `mininet> h6 iperf -c 10.0.0.2 -u –i 1`    
   



   

---
## Description

### Mininet API in Python

> TODO:
> * Describe the meaning of Mininet API in Python you used in detail

### iPerf Commands

> TODO:
> * Describe the meaning of iPerf command you used in detail
1. `mininet> h2 iperf -s -u -i 1 > ./out/result &`    
   `h2`: host 2    
   `iperf`: using iPerf to measure the max achievable bandwidth    
   `-s`: let h2 play the role of server in iPerf    
   `-u`: using UDP connections    
   `-i 1`: set interval to 1s    
   `> ./out/result &`: make a file ./out/result to save the result of this test     
2. `mininet> h6 iperf -c 10.0.0.2 -u –i 1`    
   `h6`: host 6    
   `iperf`: same as above    
   `-c`: let h6 play the role of client in iPerf    
   `10.0.0.2`: connect to host 2     
   `-u`: same as above    
   `-i 1`: same as above    

### Tasks

> TODO:
> * Describe how you finish this work step-by-step in detail

1. **Environment Setup**    
    1.1 Click the link in the slide to join the lab on GitHub Classroom    
    1.2 Open Pietty and connect to the container with IP `140.113.195.69` and Port `612213`    
    1.3 Login as `root`, and the password is `cn2018`    
    1.4 Use the command `passwd` to change the password    
    1.5 Clone my repo by `git clone https://github.com/nctucn/lab2-howhowcan.git Network_Topology`    
    1.6 Initiate the git infos by the command      
```
    git config --global user.name "howhowcan"      
    git config --global user.email gktt58@gmail.com    
```    
    1.7 Run mininet for testing :`sudo mn`    
    1.8 The error mentioned in the slide occurred, so use the command `sudo service openvswitch-switch start`    
        to solve the problem    
    1.9 Run mininet again and check if miniet is work correctly this time  
    1.10 Clean up all the connections: `sudo mn -c`     
2. **Example of Mininet**    
    2.1 Change to the directory: `cd ./Network_Topology/src/`       
    2.2 Run the example code:   
        * Change to the executable mode of example.py   
          `sudo chmod +x example.py`     
        * Run example.py     
          `sudo ./example.py`       
    2.3 Check the result     
3. **Topology Generator**

    > In this task, all the steps are done in my own computer, not in the container

    3.1 Because (my student ID)%3 equals to 0, I check topo0.png     
    3.2 After refering to example.py and some articles online, I finish my work named topology.py    
    3.3 Push topology.py to github

4. **Measurement**
    
    > Go back to the container and do the following steps

    4.1 Change to the root directory by `cd ~/`    
    4.2 Remove my old directory by the command `rm -r Network_Topology/`    
    4.3 Clone my new repo by `git clone https://github.com/nctucn/lab2-howhowcan.git Network_Topology`    
    4.4 Use the command `cd ~/Network_Topology/src/` to go to the directory with topology.py    
    4.5 Run the topology.py:   
        * Change to the executable mode of topology.py   
          `sudo chmod +x topology.py`     
        * Run topology.py     
          `sudo ./topology.py`  
    4.6 The command above will create a web topo system as same as described in topo0.png and go into the CLI mode of Mininet    
    4.7 execute the following command to get the result:   
        `mininet> h2 iperf -s -u -i 1 > ./out/result &`    
        `mininet> h6 iperf -c 10.0.0.2 -u –i 1`    
    4.8 The result is what we want, so use `mininet> exit` to quit from CLI mode
    4.9 Use the command bellow to push my work on the github:    

## References

> TODO: 
> * Please add your references in the following

* **Mininet**
    * [Mininet Walkthrough](http://mininet.org/walkthrough/)
    * [Introduction to Mininet](https://github.com/mininet/mininet/wiki/Introduction-to-Mininet)
    * [Mininet Python API Reference Manual](http://mininet.org/api/annotated.html)
    * [A Beginner's Guide to Mininet](https://opensourceforu.com/2017/04/beginners-guide-mininet/)
    * [GitHub/OSE-Lab - 熟悉如何使用 Mininet](https://github.com/OSE-Lab/Learning-SDN/blob/master/Mininet/README.md)
    * [菸酒生的記事本 – Mininet 筆記](https://blog.laszlo.tw/?p=81)
    * [Hwchiu Learning Note – 手把手打造仿 mininet 網路](https://hwchiu.com/setup-mininet-like-environment.html)
    * [阿寬的實驗室 – Mininet 指令介紹](https://ting-kuan.blog/2017/11/09/%E3%80%90mininet%E6%8C%87%E4%BB%A4%E4%BB%8B%E7%B4%B9%E3%80%91/)
    * [Mininet 學習指南](https://www.sdnlab.com/11495.html)
    * [Mininet下编写python - corey611的专栏 - CSDN博客](https://blog.csdn.net/corey611/article/details/39212053)
    * [python自定义mininet拓扑 - 考拉小无 - 博客园](https://www.cnblogs.com/wpqwpq/p/6501952.html)
* **Python**
    * [Python 2.7.15 Standard Library](https://docs.python.org/2/library/index.html)
    * [Python Tutorial - Tutorialspoint](https://www.tutorialspoint.com/python/)
    * [ghost - 關於 python 中的 self](https://freedomknight.me/guan-yu-python-zhong-de-self/)

* **Others**
    * [iPerf3 User Documentation](https://iperf.fr/iperf-doc.php#3doc)
    * [Cheat Sheet of Markdown Syntax](https://www.markdownguide.org/cheat-sheet)
    * [Vim Tutorial – Tutorialspoint](https://www.tutorialspoint.com/vim/index.htm)
    * [鳥哥的 Linux 私房菜 – 第九章、vim 程式編輯器](http://linux.vbird.org/linux_basic/0310vi.php)    
    * [Learning-Markdown (Markdown 入门参考)](http://xianbai.me/learn-md)
    * [iperf命令_Linux iperf 命令用法详解：网络性能测试工具](http://man.linuxde.net/iperf)
    
---
## Contributors

> TODO:
> * Please replace "YOUR_NAME" and "YOUR_GITHUB_LINK" into yours

* [YOUR_NAME](YOUR_GITHUB_LINK)
* [David Lu](https://github.com/yungshenglu)

---
## License

GNU GENERAL PUBLIC LICENSE Version 3