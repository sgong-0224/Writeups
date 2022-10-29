# Hackergame 2022 Writeup

## Preface

计科新生乐子人，打不来CTF，Crypto/Web/Disassembly除了一眼看出来的基本挂零。

## 签到(web,分值50)

#### 题目描述：

众所周知，签到题是一道手速题。

为了充分发挥出诸位因为各种原因而手速优异于常人的选手们的特长，我们精心设计了今年的签到题。进一步地，为了更细致地区分不同手速的选手，我们还通过详尽的调研及统计分析，将签下字符的时间限制分为了多个等级。只有最顶尖的手速选手，才能在 CPU 来得及反应之前顺利签下 2022，从而得到光荣的 flag！

提示：完成题目遇到困难？你可以参考 [2018 年签到题题解](https://github.com/ustclug/hackergame2018-writeups/tree/master/official/qiandao)、[2019 年签到题题解](https://github.com/ustclug/hackergame2019-writeups/blob/master/official/签到题/README.md)、[2020 年签到题题解](https://github.com/USTC-Hackergame/hackergame2020-writeups/blob/master/official/签到/README.md) 和 [2021 年签到题题解](https://github.com/USTC-Hackergame/hackergame2021-writeups/blob/master/official/签到/README.md)。

#### 题解：

如何在0.0秒内写下"2"？摆烂乐子人选择直接提交。这当然拿不到flag，但注意比对地址栏和识别结果处的“????"。发现这是Hackergame签到题的老套路了。

<img src="C:\Users\Gong Steven\Desktop\PB22111955_龚子祺_Hackergame题解提交.assets\屏幕截图(1509).png" style="zoom:50%;" />

接下来当然是在网址上动手脚了！将地址栏中的”????"改为“2022”即可获得flag:

<img src="E:\Photos\Screenshots\屏幕截图(1114).png" alt="屏幕截图(1114)" style="zoom: 33%;" />



## 猫咪问答(general)

#### 题目描述&题解(问题1~3,分值100)：

1. **中国科学技术大学 NEBULA 战队（USTC NEBULA）是于何时成立的喵？**

   **提示：格式为 YYYY-MM，例如 2038 年 1 月即为 2038-01。**

善用搜索引擎搜索特定时间段的结果，关键词为“中国科大星云战队”，可以搜索到中科大信院的新闻稿。

<img src="E:\Photos\Screenshots\屏幕截图(1115).png" alt="屏幕截图(1115)" style="zoom: 50%;" />

容易发现答案为**2017-03**。

2. **2022 年 9 月，中国科学技术大学学生 Linux 用户协会（LUG @ USTC）在科大校内承办了软件自由日活动。除了专注于自由撸猫的主会场之外，还有一些和技术相关的分会场（如闪电演讲 Lightning Talk）。其中在第一个闪电演讲主题里，主讲人于 slides 中展示了一张在 GNOME Wayland 下使用 Wayland 后端会出现显示问题的 KDE 程序截图，请问这个 KDE 程序的名字是什么？**
   **提示：英文单词，首字母大写，其他字母小写。**

   访问LUG wiki的SFD活动页([Software Freedom Day - LUG @ USTC](https://lug.ustc.edu.cn/wiki/lug/events/sfd/))下载相关slides，

   标题为闪电演讲：《GNOME Wayland 使用体验：一个普通用户的视角》

   <img src="E:\Photos\Screenshots\屏幕截图(1117).png" alt="屏幕截图(1117)" style="zoom: 33%;" />

   找到第15张，答案见上图绿色高亮部分，即**Kdenlive**。

3. **22 年坚持，小 C 仍然使用着一台他从小用到大的 Windows 2000 计算机。那么，在不变更系统配置和程序代码的前提下，Firefox 浏览器能在 Windows 2000 下运行的最后一个大版本号是多少？**
   **提示：格式为 2 位数字的整数。**

   直接搜索即可，答案为**12**。

flag1:

<img src="E:\Photos\Screenshots\屏幕截图(1171).png" alt="屏幕截图(1171)" style="zoom: 33%;" />



## 线路板(general,分值150)

#### 题目描述：

中午起床，看到室友的桌子上又多了一个正方形的盒子。快递标签上一如既往的写着：线路板。和往常一样，你“帮”室友拆开快递并抢先把板子把玩一番。可是突然，你注意到板子表面似乎写着些东西……看起来像是……flag？

<img src="https://hack.lug.ustc.edu.cn/media/65bb85b1-2152-55b2-b58c-7078883b3eff/circuit_boards.png" alt="circuit_boards" style="zoom: 40%;" />

可是只有开头的几个字母可以看清楚。你一时间不知所措。

幸运的是，你通过盒子上的联系方式找到了制作厂家，通过板子丝印上的序列号查出了室友的底细，并以放弃每月两次免费 PCB 打样包邮的机会为代价要来了这批带有 flag 的板子的生产文件。那这些文件里会不会包含着更多有关 flag 的信息呢？

#### 题解：

下载fabrication_files.zip并解压，用gerber文件查看器(**以KiCad为例**，很遗憾USTC镜像站并没有收录它，可以去TUNA等镜像站下载)打开ebaz_sdr-job.gbrjob文件。

注意到Copper,L1层包含flag，其它图层并没有什么用。怎么把遮罩去掉呢？

<img src="E:\Photos\Screenshots\屏幕截图(1108).png" alt="屏幕截图(1108)" style="zoom: 25%;" />

选中遮罩，右键高亮即可看到flag。

<img src="E:\Photos\Screenshots\屏幕截图(1110).png" alt="屏幕截图(1110)" style="zoom: 50%;" />

flag:

<img src="E:\Photos\Screenshots\屏幕截图(1109).png" alt="屏幕截图(1109)" style="zoom: 33%;" />



## 旅行照片2.0(general，分值100+150)

#### 第一题：照片分析(分值100):

##### 题目描述：

1. 图片所包含的 EXIF 信息版本是多少？（如 2.1）。
2. 拍照使用手机的品牌是什么？
3. 该图片被拍摄时相机的感光度（ISO）是多少？（整数数字，如 3200）
4. 照片拍摄日期是哪一天？（格式为年/月/日，如 2022/10/01。按拍摄地点当地日期计算。）
5. 照片拍摄时是否使用了闪光灯？

##### 题解：

(Windows下)查看照片属性-详细信息获得EXIF，这一道题只需要EXIF就够了。

<img src="E:\Photos\Screenshots\屏幕截图(1151).png" alt="屏幕截图(1151)" style="zoom: 25%;" /><img src="E:\Photos\Screenshots\屏幕截图(1152).png" alt="屏幕截图(1152)" style="zoom: 25%;" /><img src="E:\Photos\Screenshots\屏幕截图(1153).png" alt="屏幕截图(1153)" style="zoom: 25%;" />

答案为：1.**2.31**	2.**小米/红米**	3.**84**	4.**2022/05/14**	5.**否**

flag1:

![屏幕截图(1172)](E:\Photos\Screenshots\屏幕截图(1172).png)



####第二题：社工实践(分值150)：

##### 题目描述：

**酒店**

1. 请写出拍照人所在地点的邮政编码，格式为 3 至 10 位数字，不含空格或下划线等特殊符号（如 230026、94720）。

2. 照片窗户上反射出了拍照人的手机。那么这部手机的屏幕分辨率是多少呢？（格式为长 + 字母 x + 宽，如 1920x1080）

**航班**

仔细观察，可以发现照片空中（白色云上方中间位置）有一架飞机。你能调查出这架飞机的信息吗？

3. 起飞机场（IATA 机场编号，如 PEK）

4. 降落机场（IATA 机场编号，如 HFE）

5. 航班号（两个大写字母和若干个数字，如 CA1813）

##### 题解：

1.放大图片，注意到场馆名称 **ZOZO Marine Stadium**：<img src="E:\Photos\Screenshots\屏幕截图(1188).png" alt="屏幕截图(1188)" style="zoom: 33%;" />

直接搜索它，然后在地图软件/网站中打开：

<img src="E:\Photos\Screenshots\屏幕截图(1189).png" alt="屏幕截图(1189)" style="zoom: 25%;" />

容易发现场馆西侧靠海，结合照片面向海边、无遮挡的视角，判断作者所处的酒店为上图右侧的**千叶县幕张新大谷酒店**。

<img src="E:\Photos\Screenshots\屏幕截图(1175).png" style="zoom:50%;" />

我们搜索到了它的邮编，按照答案格式要求，本题答案为**2610021**。

**2.**分析exif。

<img src="E:\Photos\Screenshots\屏幕截图(1177).png" style="zoom: 50%;" />

容易发现这台手机为小米生产，搭载的处理器为高通骁龙662。而且作者在2022年5月身处日本，判断这台手机很可能是小米的某台国际版机型。我们搜索xiaomi+snapdragon+662试试看。

<img src="E:\Photos\Screenshots\屏幕截图(1190).png" style="zoom: 33%;" />

第一个结果就是红米9T，从产品名推断，这台手机很可能是我们想要的国际版小米手机，去GSMArena看看。

<img src="E:\Photos\Screenshots\屏幕截图(1181).png" alt="屏幕截图(1181)" style="zoom: 33%;" />

再看看照片反射中手机的镜头排列：

<img src="E:\Photos\Screenshots\屏幕截图(1191).png" alt="屏幕截图(1191)" style="zoom: 25%;" />

就是它了！把**2340x1080**这个分辨率填进去吧！

**3~5.**这三问确实有一点小技巧，不过挺有意思的。

我们首先判断这架飞机在哪里。

从拍摄视角来看，这架飞机大致沿下图红线向北飞行。

<img src="E:\Photos\Screenshots\屏幕截图(1193).png" alt="屏幕截图(1193)" style="zoom: 25%;" />

看到地图左下角的羽田机场了吗？先别高兴太早，东京空域挺乱的。即使我们大胆猜想，也要小心求证。毕竟遇到答案错误时，你并不知道错在哪一小题。

我们直接请出开源的模飞航线规划神器Little Navmap([albar965/littlenavmap: Little Navmap is a free flight planner, navigation tool, moving map, airport search and airport information system for Flight Simulator X, Microsoft Flight Simulator 2020, Prepar3D and X-Plane. (github.com)](https://github.com/albar965/littlenavmap))一探究竟。

先看看IFR航路(下图蓝线):

<img src="E:\Photos\Screenshots\屏幕截图(1235).png" alt="屏幕截图(1235)" style="zoom: 33%;" />

镜头视角内没有IFR航路！因此我们猜测这个航班是向北离开羽田的航班。其实这里就可以把第三问答案**HND**填进去了。不过为了严谨地证实一下先前的猜测，我们再搜索一下羽田的离场程序，比如MITOH(下图蓝线)。

<img src="E:\Photos\Screenshots\屏幕截图(1234).png" alt="屏幕截图(1234)" style="zoom: 33%;" />

注意TORAM PLUTO KAIJI这一段，完全可能以照片作者的拍摄视角看到飞机！那么出发地就是**HND**了。

有了出发地，我们还缺一个出发时间。查看EXIF：

![](E:\Photos\Screenshots\屏幕截图(1196).png)

日本时间18:23分，即中国标准时间CST17:23。还是没有头绪？我们来看一个从羽田离场的航班记录，进入航班跟踪网站(比如FlightAware)，查看羽田机场的历史航班记录，随便找到一个看起来和下图差不多航迹飞越东京湾的航班，我们来研究一下。

<img src="E:\Photos\Saved Pictures\图片1.png" style="zoom: 80%;" />

注意到下方的“4m",从羽田出发到拍摄地点只要4分钟！那么它的起飞时间大概在17:20CST。通过航班跟踪网站(比如FlightAware)查询羽田的离港大盘。

![](E:\Photos\Screenshots\屏幕截图(1197).png)

羽田以日本国内线为主，准点率堪比公交，无需担心大幅延误，关注17:15CST~17:25CST出发的航班即可。一共就没几个航班，直接穷举。注意把航司的ICAO码(四字码)换成IATA码(三字码)，机场填写IATA码(三字码)。

经过尝试，本题的答案为**NH683,HND-HIJ**，就是上图倒数第四行。

flag2:

![屏幕截图(1194)](E:\Photos\Screenshots\屏幕截图(1194).png)

(我们不run许用ADS-B接收机,hhhh)



## 企鹅拼盘(math)

#### 题目描述：

这是一个可爱的企鹅滑块拼盘。（觉得不可爱的同学可以换可爱的题做）

和市面上只能打乱之后拼回的普通滑块拼盘不同，这个拼盘是自动打乱拼回的。一次游戏可以帮助您体验到 `16/256/4096` 次普通拼盘的乐趣。

每一步的打乱的方式有两种，选择哪一种则由您的输入（长度为 `4/16/64` 的 `0/1` 序列）的某一位决定。如果您在最后能成功打乱这个拼盘，您就可以获取到 flag 啦，快来试试吧wwwwww

#### 这么简单我闭眼都可以！(分值100) 题解：

只有16种情况，直接暴力枚举即可，看看Inputs为何值可以打乱这个拼盘。

e.g.Inputs为"1000"可获得flag：

<img src="E:\Photos\Screenshots\屏幕截图(1118).png" alt="屏幕截图(1118)" style="zoom: 38%;" />

flag1:

![屏幕截图(1173)](E:\Photos\Screenshots\屏幕截图(1173).png)



## Heilang(general,分值100)

#### 题目描述：

来自 Heicore 社区的新一代编程语言 HeiLang，基于第三代大蟒蛇语言，但是抛弃了原有的难以理解的 `|` 运算，升级为了更加先进的语法，用 `A[x | y | z] = t` 来表示之前复杂的 `A[x] = t; A[y] = t; A[z] = t`。

作为一个编程爱好者，我觉得实在是太酷了，很符合我对未来编程语言的想象，科技并带着趣味。

#### 题解：

下载getflag.hei.py，先拉到最底下，发现它会输出flag，而且flag仅与前面这个数组元素的值有关系。

我们只需要改写代码、让这个.py文件正常运行就可以了。

如何一键Heilang转换为Python？替换关键字即可。

<img src="E:\Photos\Screenshots\屏幕截图(1127).png" alt="屏幕截图(1127)" style="zoom: 33%;" />

是不是觉得很熟悉了？Run the code and capture the flag!

![屏幕截图(1154)](E:\Photos\Screenshots\屏幕截图(1154).png)



## 家目录里的秘密(general，分值100+150)

#### 题目描述：

实验室给小 K 分配了一个高性能服务器的账户，为了不用重新配置 VSCode, Rclone 等小 K 常用的生产力工具，最简单的方法当然是把自己的家目录打包拷贝过去。

但是很不巧，对存放于小 K 电脑里的 Hackergame 2022 的 flag 觊觎已久的 Eve 同学恰好最近拿到了这个服务器的管理员权限（通过觊觎另一位同学的敏感信息），于是也拿到了小 K 同学家目录的压缩包。

然而更不巧的是，由于 Hackergame 部署了基于魔法的作弊行为预知系统，Eve 同学还未来得及解压压缩包就被 Z 同学提前抓获。

为了证明 Eve 同学不良企图的危害性，你能在这个压缩包里找到重要的 flag 信息吗？

**公益广告：题目千万条，诚信第一条！解题不合规，同学两行泪。**

#### VSCode里的flag(分值100)题解：

既然要找个人信息，什么乱七八糟的程序目录、缓存目录就不要浪费时间去看了，密切留意各种带user字眼的东西。这个\User\History就很可疑，点开它。

如下图所示，flag1在DUGV.c文件中。

<img src="E:\Photos\Screenshots\屏幕截图(1134).png" alt="屏幕截图(1134)" style="zoom:33%;" />



#### Rclone里的flag(分值150)题解：

和刚才一样，找到rclone.conf:

flag只能藏在密码里面了，但是密码被加密了：

<img src="E:\Photos\Screenshots\屏幕截图(1360).png" style="zoom:50%;" />

执行rclone config也可以印证：

<img src="E:\Photos\Screenshots\屏幕截图(1358).png" style="zoom:50%;" />

查找Rclone官网关于加密的描述:加密的pass中有AES盐和密文，然而仅靠这两个绝对没法解密。

<img src="E:\Photos\Screenshots\屏幕截图(1356).png" style="zoom:50%;" />

凉拌还是手算？凉拌肯定不行，但自己造轮子也太麻烦了！去GitHub看看，已经有人写好解密函数了，直接用：

<img src="E:\Photos\Screenshots\屏幕截图(1357).png" style="zoom:50%;" />

执行下面这一份golang代码，直接获取flag:

```go
package main
import (
	"crypto/aes"
	"crypto/cipher"
	"crypto/rand"
	"encoding/base64"
	"errors"
	"fmt"
	"log"
)

// crypt internals
var (
	cryptKey = []byte{
		0x9c, 0x93, 0x5b, 0x48, 0x73, 0x0a, 0x55, 0x4d,
		0x6b, 0xfd, 0x7c, 0x63, 0xc8, 0x86, 0xa9, 0x2b,
		0xd3, 0x90, 0x19, 0x8e, 0xb8, 0x12, 0x8a, 0xfb,
		0xf4, 0xde, 0x16, 0x2b, 0x8b, 0x95, 0xf6, 0x38,
	}
	cryptBlock cipher.Block
	cryptRand  = rand.Reader
)

// crypt transforms in to out using iv under AES-CTR.
// in and out may be the same buffer.
// Note encryption and decryption are the same operation
func crypt(out, in, iv []byte) error {
	if cryptBlock == nil {
		var err error
		cryptBlock, err = aes.NewCipher(cryptKey)
		if err != nil {
			return err
		}
	}
	stream := cipher.NewCTR(cryptBlock, iv)
	stream.XORKeyStream(out, in)
	return nil
}

// Reveal an obscured value
func Reveal(x string) (string, error) {
	ciphertext, err := base64.RawURLEncoding.DecodeString(x)
	if err != nil {
		return "", fmt.Errorf("base64 decode failed when revealing password - is it obscured? %w", err)
	}
	if len(ciphertext) < aes.BlockSize {
		return "", errors.New("input too short when revealing password - is it obscured?")
	}
	buf := ciphertext[aes.BlockSize:]
	iv := ciphertext[:aes.BlockSize]
	if err := crypt(buf, buf, iv); err != nil {
		return "", fmt.Errorf("decrypt failed when revealing password - is it obscured? %w", err)
	}
	return string(buf), nil
}

// MustReveal reveals an obscured value, exiting with a fatal error if it failed
func MustReveal(x string) string {
	out, err := Reveal(x)
	if err != nil {
		log.Fatalf("Reveal failed: %v", err)
	}
	return out
}

func main() {
	fmt.Println(MustReveal("tqqTq4tmQRDZ0sT_leJr7-WtCiHVXSMrVN49dWELPH1uce-5DPiuDtjBUN3EI38zvewgN5JaZqAirNnLlsQ"))//put ENCRYPTED pass "HERE"
}
```

拿到flag2:

![](E:\Photos\Screenshots\屏幕截图(1361).png)



## 片上系统(binary)

#### 题目描述：

你的室友在学习了计算机组成原理之后沉迷 RISC-V 软核开发。

RISC-V，是一个近年来兴起的开放指令集架构。

软核，意思是这个 RISC-V CPU（如果能称之为 CPU 的话）是在 FPGA 等可编程芯片中运行的（而不是在真正硅片上固定的物理电路）。同时，CPU 需要的外部硬件，如字符打印、图像显示、LED 点灯等等，均需要自己用硬件描述语言编写（而不像单片机等设备开发时只要调用库函数就可以了）。有些人会选择已经实现好的开源部件和处理器，组合定制成为一套片上系统（System on Chip, SoC），用于嵌入式开发、工业控制或个人娱乐等目的。而另外一些失去理智的人们则选择以一己之力，从零开始编写自己的 CPU 和外设，并企图用自己几个月摸鱼摸出的处理器与嵌入式大厂数十年的积累抗衡，尽管 Ta 们的 CPU 通常性能不如 i386、没有异常处理、甚至几十个周期才能完成一条指令，而外设也通常仅限于串口和几个屈指可数的 LED 灯。

最近，你听说室友在 SD 卡方面取得了些进展。在他日复一日的自言自语中，你逐渐了解到这个由他一个人自主研发的片上系统现在已经可以从 SD 卡启动：先由“片上 ROM 中的固件”加载并运行 SD 卡第一个扇区中的“引导程序”，之后由这个“引导程序”从 SD 卡中加载“操作系统”。而这个“操作系统”目前能做的只是向“串口”输出一些字符。

同时你听说，这个并不完善的 SD 卡驱动只使用了 SD 卡的 SPI 模式，而传输速度也是低得感人。此时你突然想到：如果速度不快的话，是不是可以用逻辑分析仪来采集（偷窃）这个 SD 卡的信号，从而“获得” SD 卡以至于这个“操作系统”的秘密？

你从抽屉角落掏出吃灰已久的逻辑分析仪。这个小东西价格不到 50 块钱，采样率也只有 24 M。你打开 PulseView，把采样率调高，连上室友开发板上 SD 卡的引脚，然后接通了开发板的电源，希望这聊胜于无的分析仪真的能抓到点什么有意思的信号。至于你为什么没有直接把 SD 卡拿下来读取数据，就没人知道了。

**引导扇区**

听说，第一个 flag 藏在 SD 卡第一个扇区的末尾。你能找到它吗？

**操作系统**

室友的“操作系统”会输出一些调试信息和第二个 flag。从室友前些日子社交网络发布的终端截图看，这个“操作系统”每次“启动”都会首先输出：

```
LED: ON
Memory: OK
```

或许你可以根据这一部分固定的输出和引导扇区的代码，先搞清楚那“串口”和“SD 卡驱动”到底是怎么工作的，之后再仔细研究 flag 到底是什么，就像当年的 Enigma 一样。

#### 引导扇区(分值200)题解：

题目已经提示使用Pulseview读取信号，打开Pulseview，按照metadata给的参数:4通道/采样率16MHz打开逻辑文件。打开完成后将会看到4个波形。

![屏幕截图(1142)](E:\Photos\Screenshots\屏幕截图(1142).png)

SPI总线的四条信号线分别为主输出/从输入（MOSI）、主输入/从输出（MISO）、时钟线（SCLK）、从线选择（SS或CS）。SD卡上电时CS信号立即转为低电平；频率恒定的波形是SCLK无疑；主机输出必然在主机输入之前，因此确定四条信号线为D0-CS,D1-SCLK,D2-MOSI,D3-MISO。

选择工具栏上右侧第二个按钮，添加SD卡(SPI模式)的解码器。我们已经对应好了各通道和信号线的关系，直接如图填入CLK,MISO,MOSI,CS#即可。

<img src="E:\Photos\Screenshots\屏幕截图(1143).png" alt="屏幕截图(1143)" style="zoom:80%;" />

我们就可以看到具体的指令和数据了。

![屏幕截图(1144)](E:\Photos\Screenshots\屏幕截图(1144).png)

注意到CMD8和CMD55、ACMD41命令中，SD卡都出于识别模式，我们还没有看到扇区内容，不用管它。需要留意主机发送的CMD17(READ_SINGLE_BLOCK)命令，用来读取SD卡的第一个扇区，我们的flag就在这个扇区末尾。最困难的地方已经结束了，我们把flag找出来。

可以先把扇区内容Block data复制到剪贴板:

<img src="E:\Photos\Screenshots\屏幕截图(1145).png" alt="屏幕截图(1145)" style="zoom:50%;" />

找到扇区末尾的数据：

<img src="E:\Photos\Screenshots\屏幕截图(1146).png" alt="屏幕截图(1146)" style="zoom:50%;" />

这串数据之前是一长串0，应该就是我们要找的flag了。找到数据的起始位置：

<img src="E:\Photos\Screenshots\屏幕截图(1147).png" alt="屏幕截图(1147)" style="zoom:50%;" />

数据的特点(0~127的十进制整数)让我们很容易把它同ASCII联系起来。

试试看吧！将ASCII码(10进制)转换为字符：

<img src="E:\Photos\Screenshots\屏幕截图(1148).png" alt="屏幕截图(1148)" style="zoom: 67%;" />



## LaTeX机器人(web)

#### 题目描述：

在网上社交群组中交流数学和物理问题时，总是免不了输入公式。而显然大多数常用的聊天软件并不能做到这一点。为了方便大家在水群和卖弱之余能够高效地进行学术交流，G 社的同学制作了一个简单易用的将 LaTeX 公式代码转换成图片的网站，并通过聊天机器人在群里实时将群友发送的公式转换成图片发出。

这个网站的思路也很直接：把用户输入的 LaTeX 插入到一个写好头部和尾部的 TeX 文件中，将文件编译成 PDF，再将 PDF 裁剪成大小合适的图片。

“LaTeX 又不是被编译执行的代码，这种东西不会有事的。”

物理出身的开发者们明显不是太在意这个网站的安全问题，也没有对用户的输入做任何检查。

那你能想办法获得服务器上放在根目录下的 flag 吗？

**纯文本**

第一个 flag 位于 `/flag1`，flag 花括号内的内容由纯文本组成（即只包含大写小写字母和数字 0-9）。

**特殊字符混入**

第二个 flag 位于 `/flag2`，这次，flag 花括号内的内容除了字母和数字之外，还混入了两种特殊字符：下划线（`_`）和井号（`#`）。你可能需要想些其他办法了。

#### 纯文本(分值150)题解：

直接用input语句，题解如下，flag加上一对花括号提交即可。

<img src="E:\Photos\Screenshots\屏幕截图(1199).png" style="zoom: 25%;" />



## 杯窗鹅影

#### 题目描述：

说到上回，小 K 在获得了实验室高性能服务器的访问权限之后就迁移了数据（他直到现在都还不知道自己的家目录备份被 Eve 下载了）。之后，为了跑一些别人写的在 Windows 下的计算程序，他安装了 wine 来运行它们。

「你用 wine 跑 Windows 程序，要是中毒了咋办？」

「没关系，大不了把 wineprefix 删了就行。我设置过了磁盘映射，Windows 程序是读不到我的文件的！」

但果真如此吗？

为了验证这一点，你需要点击「打开/下载题目」按钮，上传你的程序实现以下的目的：

1. `/flag1` 放置了第一个 flag。你能给出一个能在 wine 下运行的 x86_64 架构的 Windows 命令行程序来读取到第一个 flag 吗？
2. `/flag2` 放置了第二个 flag，但是需要使用 `/readflag` 程序才能看到 `/flag2` 的内容。你能给出一个能在 wine 下运行的 x86_64 架构的 Windows 命令行程序来执行 `/readflag` 程序来读取到第二个 flag 吗？

提示：

1. 该环境为只读环境，运行在 x86_64 架构的 Linux 上。我们未安装图形库与 32 位的相关运行库，因此需要使用图形界面的 Windows 程序与 32 位的 Windows 程序均无法执行；
2. 包括 `start.exe`, `cmd.exe`, `winebrowser.exe`, `wineconsole.exe` 在内的部分程序已从环境中删除；
3. 作为参考，你可以在 Linux 下使用 MinGW 交叉编译出符合要求的 Windows 程序，以 Ubuntu 22.04 为例（其他 Linux 发行版所需操作类似）：
   1. 安装 MinGW 工具链，在 Ubuntu 22.04 下其对应的软件包为 `gcc-mingw-w64-x86-64`；
   2. 使用 C 编写 Windows 程序，这里使用 Hello, world 为例（代码见下） ；
   3. 使用命令 `x86_64-w64-mingw32-gcc helloworld.c` 编译，得到的 `a.exe` 文件即为符合要求的 x86_64 架构的 Windows 命令行程序。

#### flag1(分值150)题解:

不要想多了，只是用C语言写一个读取文件的程序而已。

注意:直接读取/flag1，wineprefix已经没了。下面上代码：

```c
#include<stdio.h>
#include<stdlib.h>
int main()
{
	FILE *flagop;
	char c;
	flagop =fopen("/flag1","r");
	while((c=fgetc(flagop))!=EOF)
		putchar(c);
	return 0;
}
```

上传程序并得到flag1:

<img src="E:\Photos\Screenshots\屏幕截图(1271).png" style="zoom: 67%;" />



## 火眼金睛的小 E

#### 题目描述：

小 E 有很多的 ELF 文件，它们里面的函数有点像，能把它们匹配起来吗？

小 A：这不是用 BinDiff 就可以了吗，很简单吧？

#### 有手就行(分值150)题解：

题面既然这样说那应该不难(狗头)

Note:首次答题时，时间戳尽量选在区间中段。不然对(像我这样菜的)新手来说，在超时结束之前大概率做不完。

以我手上拿到的题目为例。

Note+:本题的ELF文件需要使用IDA64打开。

<img src="C:\Users\Gong Steven\Desktop\PB22111955_龚子祺_Hackergame题解提交.assets\屏幕截图(1433).png" style="zoom: 50%;" />

**第一组: "e1*" vs "60\*"**

<img src="C:\Users\Gong Steven\Desktop\PB22111955_龚子祺_Hackergame题解提交.assets\屏幕截图(1436).png" style="zoom: 50%;" />

显然不难，BinDiff给出81%相似度和91%置信，看起来结果还挺可靠的。**0x87d0**，就是它了。

<img src="C:\Users\Gong Steven\Desktop\PB22111955_龚子祺_Hackergame题解提交.assets\屏幕截图(1435)-16669527981842.png" style="zoom: 50%;" />

**第二组："fd*" vs "a5\*"**

这次不一样了，BinDiff并没有给出任何有价值的信息，甚至连0x6b02这个数的影子都没有。

看看1号ELF的0x6b02位置是个什么东西。

<img src="C:\Users\Gong Steven\Desktop\PB22111955_龚子祺_Hackergame题解提交.assets\屏幕截图(1428).png" style="zoom:50%;" />

记住它的样子，既然是“有手就行”的题，我们直接对2号ELF反编译出来的的汇编代码进行搜索，用肉眼即可。

<img src="C:\Users\Gong Steven\Desktop\PB22111955_龚子祺_Hackergame题解提交.assets\屏幕截图(1429).png" style="zoom:50%;" />

**0x6b80**，和刚才的那一段真的很像，唯独少了一个无所谓的减法。

拿到flag1：

<img src="C:\Users\Gong Steven\Desktop\PB22111955_龚子祺_Hackergame题解提交.assets\屏幕截图(1434).png" style="zoom:67%;" />



## 《关于 RoboGame 的轮子永远调不准速度这件事》(binary，分值300)

#### 题目描述：

今年，李德川和张修院两位同学报名参加了由淳平粮油店赞助的会员制比赛 RoboGame。

学院为了宣传近期科考领域的重大发现，定今年 RoboGame 的主题是《楼兰古国科考机器人》。

由于现实中楼兰古国的地形地貌漂亮得很啊！需要精细的移动控制，所以这个科考机器人需要使用 0x24 个轮子进行精密操控，这些轮子由下北泽的黑色高级轿车专用智能芯片控制，据说，这张芯片采用的是 `8051` 架构。另外，这台机器有 114514 个甚至 **128** 个 `I2C` 端口可以进行数据传输，其中的一些端口与机器人的某些部件相连接，每个 `I2C` 端口都以一个 ASCII 字符作为标识。为了降低操控难度，学院下发的机器中只有前十个轮子需要选手自己调速。

可是面对着这台机器，两人面露难色：他们发现，只要固定一个轮子的速度，相邻的两个轮子的速度就会不受控制。

李德川同学不禁发出了“鸭蛋莫鸭蛋”的抱怨。此时，机器内部忽然发出了野兽般的咆哮：

**“`0x24` 号，是 `EEPROM`。”**

“`EEPROM` 的话，那么 `读取和写入` 什么的都有在做吗？”

“那是当然啦！**输入 `指令`、`端口` 和 `发送字节长度` 以后，如果指令是 `写入`，写入的第一个字节就是之后读写的页面序号，后面跟的字节就会一个一个一个一个地擦写。上电以后默认操作的页面是第 0 页。**”

“大人，您写入的高电平都白啦！”

“戳啦！`EEPROM` 嘛！**里面存着固件，上电后写入的 `1` 只能把 `EEPROM` 中的对应位擦成低电平。由于硬件的奇妙性质，你只有甚至九比特的擦除机会**。”

两人对着这台机器给出的提示摸不着头脑。此时，比赛方发来了信息：“根据赞助方的要求，我们的中期考核会降低难度，**在九次调速中，能把前十个轮子的速度调成一样**，老爷有赏啊！赏赐就藏在 0x24 个轮子的转速数据之中。”

#### **题解：**

首先我们发现，一个轮子的速度会影响相邻两个轮子的速度。

那么，每次间隔一个轮子写入速度，它们之间的轮子的速度如何？

这问题很有意思，我们对1,3,5,7,9(或0,2,4,6,8)号端口执行写入，并且写入空数据，即执行5次`w <port> 1`命令。

结果如下：

<img src="C:\Users\Gong Steven\Desktop\PB22111955_龚子祺_Hackergame题解提交.assets\屏幕截图(1486).png" style="zoom:50%;" />

接下来就是读取各端口以获取flag。看题目提示，“赏赐就藏在 0x24 个轮子的转速数据之中。”，我们需要搞明白这**36个**端口的编号。

先看源码：

<img src="C:\Users\Gong Steven\Desktop\PB22111955_龚子祺_Hackergame题解提交.assets\屏幕截图(1489).png" style="zoom: 50%;" />

注释很贴心，告诉我们端口号只有一位，连读函数的时间都省了。然后开始读取端口：

从0开始：

<img src="C:\Users\Gong Steven\Desktop\PB22111955_龚子祺_Hackergame题解提交.assets\屏幕截图(1488).png" style="zoom:50%;" />

或许细心的同学已经看出来了，"66 6C 61 67 7B"就是"flag{"的ASCII码。但是，如果我们只读0~9号端口，得出来的"flag"长这样:`flag{seNpa`，连“先辈”都没写全！

我们看看有什么别的端口可以读，既然题目多次用“0x"提示可以用**16进制**，我们试试读取端口A~F：

<img src="C:\Users\Gong Steven\Desktop\PB22111955_龚子祺_Hackergame题解提交.assets\屏幕截图(1490).png" style="zoom:50%;" />

A~F也可以！然而十个数字和ABCDEF一共也只有16个，离36个数据还差20，我们继续读取大写字母编号的端口，发现可以一直读到T，其中留意S端口的"7D"即"}"，flag在这里结束了：

<img src="C:\Users\Gong Steven\Desktop\PB22111955_龚子祺_Hackergame题解提交.assets\屏幕截图(1400).png" style="zoom: 50%;" />

愿意继续尝试的同学当然可以把端口号换成a,b,c,...等小写字母，但是这些端口号都是无效的。我们注意到10个数字和A~S一共19个字母只覆盖了29个端口号，离我们想要的36个端口号还差**7个**。

T-Z与a~z都不是我们想要的端口号，这就排除了33个可打印字符。那我们要的flag去哪里找呢？

我们先把已经有的flag信息拼凑起来看一看,它长这样:`flag{seNpa1rmwar3_6050ab924c}`

"seNpa1rmwar3"?如果不是恶作剧的话，这***下北泽智能移动化粪池固件***的味儿也太冲了。如果你直接把上面这一串东西敲到写着flag{...}的输入框里，你将收获一个巨大的WA横幅。因此我们推断，"seNpa1rmwar3"是由两个字符串"seNpa1"和"F1rmwar3"拼接而成的，而嫌疑最大的地方就是"a""1"和"r"，它们的ASCII码分别是"61""31"和"72"，来自端口"9","A"和"B"。

那么，缺少的这7个端口号，应该就在"9"和"A"之间。

|   HEX    |  DEC   | CHAR  |
| :------: | :----: | :---: |
| **0x39** | **57** | **9** |
|   0x3A   |   58   |   :   |
|   0x3B   |   59   |   ;   |
|   0x3C   |   60   |   <   |
|   0x3D   |   61   |   =   |
|   0x3E   |   62   |   >   |
|   0x3F   |   63   |   ?   |
|   0x40   |   64   |   @   |
| **0x41** | **65** | **A** |

查找ASCII码表，我们发现"9"和"A"之间有":" ";" "<" "=" ">" "?" "@" 共**7个**字符。它们是否就是我们要的端口号呢？我们试着从这几个端口读取数据：

<img src="C:\Users\Gong Steven\Desktop\PB22111955_龚子祺_Hackergame题解提交.assets\屏幕截图(1482).png" style="zoom: 67%;" />

这些端口号果然是合法的！我们需要的端口号就是从**ASCII:0x30~ASCII:0x53**一共36个。

所有端口的数据如下表，直接把它们转换成字符就得到了flag：

<img src="C:\Users\Gong Steven\Desktop\PB22111955_龚子祺_Hackergame题解提交.assets\屏幕截图(1492).png" style="zoom: 40%;" />

(下北泽智能汽车软件公司hhh)

**----------------------------------------------------------------END-----------------------------------------------------------------------**
