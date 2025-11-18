---
title: "VMware 相關資訊筆記 "
date: "2025-11-16"
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

#### ESXi SSH 公鑰存放位置

<pre class="shell">
<span class="shell-prompt">$</span> <kbd>/etc/ssh/keys-root/authorized_keys</kbd>
</pre>

</br>

#### ESXi Web Client 的 SSL 憑證存放位置

<pre class="shell">
<span class="shell-prompt">$</span> <kbd>/etc/vmware/ssl/rui.crt</kbd>  # 權限 644
<span class="shell-prompt">$</span> <kbd>/etc/vmware/ssl/rui.key </kbd> # 權限 600
</pre>

</br>


#### 重新啟動 ESXi Web Client Service

<pre class="shell">
<span class="shell-prompt">$</span> <kbd>/etc/init.d/hostd restart</kbd>
<span class="shell-prompt">$</span> <kbd>/etc/init.d/vpxa restart</kbd>
<span class="shell-prompt">$</span> <kbd># 如果沒效可以嘗試重起全部服務</kbd>
<span class="shell-prompt">$</span> <kbd>/sbin/services.sh restart</kbd>
</pre>

</br>

#### 掛載 NFS 磁碟

<pre class="shell">
<span class="shell-prompt">$</span> <kbd>esxcfg-nas -a -o 192.168.1.21 -s /DATA NAS_DATA</kbd>
</pre>



