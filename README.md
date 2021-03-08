# NETFLIX-VERIFY

流媒体NetFlix解锁检测脚本，使用Go语言编写。经目前的所有反馈，本脚本准确性为99%。

在VPS网络正常的情况下，哪怕是双栈网络也可在几秒内快速完成IPv4/IPv6的NF解锁情况判断。

## 提醒

在观看Netflix影片，有一种情况极少遇到，那就是“**半解锁**”，可以观看一部分的非自制剧，却不会显示任何地域排行榜有关的信息。

这种情况由于太少见以至于**很容易被忽略**，我会在未来认真研究它，以推出更健壮的检测脚本。如果您手里有可以半解锁Netflix的机器，欢迎联系我测试，我会将您的名字加入鸣谢名单中，非常感谢。

## 新特性

**你的Netflix脚本你做主！** 在`2.51`版本中，提供了2种不同的模式，将显示完全不同的结果：

* 运行`./nf -method full`将专门为发烧友准备的利器，显示更全面的结果
* 而普通用户当以缺省参数运行`./nf`或者是`./nf -method lite`将显示更轻量级的结果，显示更加友好

## 鸣谢

1. 感谢 [@CoiaPrant](https://github.com/CoiaPrant) 指出对于地域检测更简便的方法
2. 感谢 [@XmJwit](https://github.com/XmJwit) 解决了IPV6 Only VPS无法下载脚本的问题

## 功能实现

- [X] 解锁情况判断
- [X] 地域信息显示
- [X] 双栈网络测试
- [ ] 半解锁检测（待实现）

## 相关名词解释

1. **不提供服务** - 所在的地区NF没开通，连自制剧也看不了
2. **宽松版权** - 有些NF拍摄的影片不是特别注重版权，所以限制放的很开
3. **解锁自制剧** - 代表可以看由NF自己拍摄的影片
4. **解锁非自制剧** - 代表可以看NF买下的第三方版权影片
5. **地域解锁** - NF在不同的地区可以看的片源都是不同的，有些影片只能在特定区观看

一般通俗意义上来说，需要能看非自制剧才算真正意义上的NF解锁

## 使用方法

#### 1. 部署 `golang` 环境，执行 `go run nf.go` 运行本小应用

#### 2. 懒人一键运行包（使用编译好的二进制文件执行本小程序）

**Github主站下载链接:**
  
  `wget -O nf https://github.com/sjlleo/netflix-verify/releases/download/2.51/nf_2.51_linux_amd64 && chmod +x nf && clear && ./nf`

**CDN下载链接(此CDN支持IPV6网络):**

  `wget -O nf https://cdn.jsdelivr.net/gh/sjlleo/netflix-verify/CDNRelease/nf_2.51_linux_amd64 && chmod +x nf && clear && ./nf`

## 效果演示图

### 简约模式

![Lite Method](https://user-images.githubusercontent.com/13616352/110276737-c5b80100-800e-11eb-8281-b4c3c9bd63a0.png)


![Lite Method2](https://user-images.githubusercontent.com/13616352/110276620-7e317500-800e-11eb-9a21-3800b9c687c5.png)

### 发烧模式

![Full Method](https://user-images.githubusercontent.com/13616352/110276768-d9636780-800e-11eb-9b10-3ada67402f94.png)


![Full Method2](https://user-images.githubusercontent.com/13616352/110276684-a4efab80-800e-11eb-8e73-4facf417ab52.png)


## 第三方 Linux Shell 脚本

此脚本为 CoiaPrant 所开发，支持双栈的检测，仅作收录

https://github.com/CoiaPrant/Netflix_Unlock_Information/

