## Pytorch 安装

### win10 系统下的安装

1. 下载anaconda3 基于3.7版本，然后进行安装

2. 打开anaconda prompt建立虚拟环境pytorch，然后 activate pytorch

    ```
    conda create --name pytorch python=3.7
    ```

3. 在官网上找到适合的pytorch，然后安装

    ![pytorch](https://raw.githubusercontent.com/Stylite-Y/MyTypora/master/img/pytorch.PNG)
    
    ```
    conda install pytorch torchvision cudatoolkit=10.1 -c pytorch
    ```





## scikit 安装

1. 打开anaconda prompt并激活pytorch虚拟环境 activate pytorch
2. 通过conda install scikit-learn