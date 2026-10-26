Netfilter: Desynchronizing Evasion Against Filters

A tool to inject a bogus request into a TCP stream, useful for evading IDS.

Usage:
1. Build and install the module.  
[How to Build External Modules](https://www.kernel.org/doc/html/latest/kbuild/modules.html)
2. Customize the inject buffer at `/sys/kernel/debug/nf_deaf/buf`. You can use `vi` or `cat`.
3. Use iptables or nftables to mark the packet to be processed
   mark format: `0xdeafNNNN`, where:
   `[31:16]` - the magic number `0xdeaf`  
   `[15]` - whether to corrupt ACK SEQ  
   `[14]` - whether to corrupt SEQ  
   `[13]` - whether to corrupt TCP checksum  
   `[12:10]` - send the injected packets for `<num>` more times  
   `[9:5]` - delay the original packets for `<num>` jiffies  
   `[4:0]` - TTL of injected packets  

[:heart: Support my work on GitHub Sponsors](https://github.com/sponsors/LGA1150)

## 捐赠支持 / Donate

如果本仓库对你有帮助，欢迎通过支付宝自愿捐赠，支持本仓库维护者 **bg4hsi**。

If you find this repository useful, you can optionally support its maintainer, **bg4hsi**, via Alipay.

<p align="center">
  <a href="assets/alipay-donate.jpg">
    <img src="assets/alipay-donate.jpg" alt="支持本仓库维护者 bg4hsi 的支付宝捐赠二维码 / Alipay donation QR code for repository maintainer bg4hsi" width="320">
  </a>
</p>

使用支付宝扫一扫，或点击图片查看原图。感谢你的支持！
