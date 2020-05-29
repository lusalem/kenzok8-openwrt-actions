## 搭建教程

[openwrt-actions 详细图文教程](https://p3terx.com/archives/build-openwrt-with-github-actions.html)


* 修改默认ip

```bash
sed -i 's/192.168.1.1/192.168.10.1/g' package/base-files/files/bin/config_generate
```
* 删除原主题	
```bash
rm -rf package/lean/luci-theme-argon
```

* 添加新的主题
```bash
git clone https://github.com/kenzok8/luci-theme-atmaterial.git package/lean/luci-theme-atmaterial
```
* 添加常用软件包
```bash
git clone https://github.com/kenzok8/openwrt-packages.git package/openwrt-packages
```
* 删除默认密码
```bash
sed -i "/CYXluq4wUazHjmCDBCqXF/d" package/lean/default-settings/files/zzz-default-settings
```

* 取消bootstrap为默认主题	
```bash
sed -i '/set luci.main.mediaurlbase=\/luci-static\/bootstrap/d' feeds/luci/themes/luci-theme-bootstrap/root/etc/uci-defaults/30_luci-theme-bootstrap
```
##### 固件下载链接

- [Lienol固件下载地址](https://github.com/kenzok8/actions-openwrt-passwall/actions)
- [Lean  固件下载地址](https://github.com/kenzok8/LEDE-x86_64/actions)
- [ctc team  固件下载地址](https://github.com/kenzok8/openwrt-actions/actions?query=workflow%3Actc-19.07)

#### 固件包含

#### SSRPLUS +passwall+clash+openclash （Lienol固件多smartdns）
