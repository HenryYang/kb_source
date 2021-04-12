---
title: "VMware info & notes / VMware 相關資訊筆記 "
date: "2021-03-27"
---

#### VMwave 虛擬磁碟格式

完整佈建消極式歸零 `Thick Provision Lazy Zeroed (zeroedthick)`  
在建立虛擬硬碟時會一次給足所設定的硬碟大小，虛擬硬碟一開始時只會將目前所使用到的部分先進行初始化，其它的部分只是當有用到時才會做初始化的動作。  

</br>

完整佈建積極性歸零 `Thick Provision Eager Zeroed (eagerzeroedthick)`  
在建立虛擬硬碟時會一次給足所設定的硬碟大小，虛擬硬碟一開始時就會將所有的部分先行初始化，所以開始時會耗費一些時間，但後續使用時，不用在做初始化，所以效能會稍微好一些。  

</br>

精簡佈建 `Thin Provision`  
會隨著虛擬硬碟的使用量而增加硬碟的大小，直到達到當時建立的磁碟空間上限為止  

</br>


#### 重新啟動 ESXi Web Client Service

<pre class="shell">
<span class="shell-prompt">$</span> <kbd>/etc/init.d/hostd restart</kbd>
<span class="shell-prompt">$</span> <kbd>/etc/init.d/vpxa restart</kbd>
</pre>

