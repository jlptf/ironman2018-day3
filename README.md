## Day 3 - k8s 安裝須知

### 本日共賞

* k8s 安裝方式
* hypervisor
* minikube
* kubectl

### 希望你知道

* [Day 2 - k8s 架構](https://ithelp.ithome.com.tw/articles/10192409)

#### k8s 安裝方式

k8s 的建立方式粗略可分為三種

* 手動安裝
* 使用雲端平台
* minikube

               | 難易度    | 價格  | 花費時間 | 用於正式環境
-------------  |:-------:|:-----: |:-----: |:--------:
手動安裝        | 高       | 中     | 高      | 是
使用雲端平台     | 中       | 高     | 中     | 是
minikube       | 低       | 低     | 低     | 否

k8s 是 [開源專案](https://github.com/kubernetes)，如果想要自己從頭開始手動安裝絕對不是問題。但是過程有點複雜，對於初學者來說很容易出錯。經由上面的比較表的粗略分析，為了讓大家更容易了解 k8s，這次我們選擇使用雲端平台及 minikube 來分享與解說 k8s 的各項功能。

> 之後會先以 minikube 為主進行解說，如果時間允許的話會多分享一些雲端平台的內容。
> 
> 目前很多雲端平台都有提供 k8s 的服務，例如 [AWS - EKS](https://aws.amazon.com/tw/eks/), [GCP - GKE](https://cloud.google.com/kubernetes-engine/), 或 [Azure - AKS](https://docs.microsoft.com/zh-tw/azure/aks/intro-kubernetes) 等等，[k8s 不自賞](https://ithelp.ithome.com.tw/users/20107062/ironman/1244) 會使用 [GCP - GKE](https://cloud.google.com/kubernetes-engine/) 當作示範的雲端平台。


#### hypervisor

minikube 必須運行在虛擬環境 (hypervisor) 下，因此在安裝 minikube 前，必須先安裝適合的 hypervisor。各作業系統可使用的 hypervisor 如下

* Linux
  * <mark>VirtualBox</mark> 或 KVM 等等
* Mac OS
  * <mark>VirtualBox</mark>, VMWare Fusion 或 xhyve driver 等等
* Windows
  * <mark>VirtualBox</mark> 或 Hyper-V 等等

不知道大家有沒有發現關鍵字? 對！ VirtualBox！怎麼大家都這麼聰明！由於它可以在大部分的系統使用，因此我們採用 VirtualBox 作為示範用的 hypervisor

>[k8s 不自賞](https://ithelp.ithome.com.tw/users/20107062/ironman/1244) 的解說內容會以 mac / linux 為主
>
> 因為手邊沒有 windows 的電腦，所以如果有 windows 的範例，基本上我都沒實際操作過，這裡先跟使用 windows 的朋友說聲抱歉了。
 
#### minikube

[minikube](https://github.com/kubernetes/minikube) 可在單機中運行 k8s 叢集，是入門練習的好工具。不論你是使用 Mac, Linux 或 Windows，minikube 皆有對應的版本可以使用。

> 不建議用於正式環境，minikube 比較適合練習測試用

昨天提到過管理者的工作就是告訴 k8s 想要做的事情，而管理者可以透過三種方式與 minikube 溝通

* APIs
* 儀表板 (Dashboard UI)
* kubectl

> 與 minikube 溝通，也就是等於跟 k8s 叢集溝通的意思。我們在後面文章會說明如何利用這三種方式與 k8s 叢集溝通

#### kubectl

kubectl 是一個用來與 k8s 叢集溝通的二進位 (binary) 工具，。我們可以透過 kubectl 對 minikube 下達命令。

>不是只能針對 minikube 而是 k8s 叢集皆可

一般來說 kubectl 會在安裝 minikube 前就先安裝好，不過並非強制，也可以在 minikube 安裝好後再安裝 kubectl。



明天我們就正式進入基礎篇，開始安裝 k8s

> 等不及的朋友可以先參考 [zxcvbnius](https://ithelp.ithome.com.tw/users/20103753/ironman) 大大在這次鐵人賽的主題 [Kubernetes 30天學習筆記](https://ithelp.ithome.com.tw/users/20103753/ironman/1590) 分享的 [[Day 2] Minikube 安裝與配置](https://ithelp.ithome.com.tw/articles/10192490)，也是寫得很好的文章喔！

本文同步發表於 [https://jlptf.github.io/ironman2018-day3/](https://jlptf.github.io/ironman2018-day3/)