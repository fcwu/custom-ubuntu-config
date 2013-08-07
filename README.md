使用 live-build 客製化無人值守 Ubuntu 安裝光碟

要客製化 Ubuntu 安裝光碟，在 Ubutnu wiki 有兩篇教學。1) [LiveCDCustomization](https://help.ubuntu.com/community/LiveCDCustomization) 描述 LiveCD 環境的客製化。2) [InstallCDCustomization](https://help.ubuntu.com/community/InstallCDCustomization) 描述安裝完後的環境客製化。這兩篇文章雖然都很有參考價值，但需要先下載 Ubuntu 的光碟，並以此加工。

小弟早有所聞用 [live-build](http://live.debian.net/manual/stable/html/live-manual.en.html) 也可自製開機光碟，google 一下便又找到 [Ubuntu 12.04 Cloud Live](http://blog.init.hr/?p=183) 及 [Live-build使用指南](http://www.ubuntukylin.com/ukylin/forum.php?mod=viewthread&tid=20)，由於不需先下載光碟，個人偏好使用這種方式，本文也將以此繼續發揮。

# Build ISO

不囉嗦，請照下面步驟做：

```
$ sudo apt-get install 
$ mkdir live-build && cd live-build
$ git clone https://github.com/fcwu/custom-ubuntu-config.git
$ sudo PROJECT=ubuntu SUITE=precise ARCH=amd64 lb build
```

約過半小時或好幾個小時，便會生成 binary.iso，此檔便是 Ubuntu 12.04 的安裝光碟。若要改成 13.04 的話，只需將 SUITE=precise 改成 SUITE=raring 即可。

# 無人值守

# 安裝更多軟體

# live-build

live-build 在製作 iso 時，共分 4 大步驟：

1. bootstrap
2. chroot
3. binary
4. source

更進一步在查看源碼後，可以發現在執行 lb build 時，會分別做這 4 大步的指令 lb bootstrap, lb chroot, lb binary, lb source。相關源碼在 `/usr/share/live/build/scripts/build` 裡，如 lb_bootstrap, lb_chroot 這些 scripts。

## bootstrap

## chroot

## binary

## stage

= config/chroot_packages
add some file or remove by git in chroot_packages
$ sudo rm .stage/chroot_install-packages.live .stage/chroot_packages .stage/binary_iso .stage/binary_rootfs .stage/binary_manifest

= config/binary_local-includes
$ sudo rm .stage/binary-includes .stage/binary_local-includes .stage/binary_iso .stage/binary_rootfs .stage/binary_manifest

