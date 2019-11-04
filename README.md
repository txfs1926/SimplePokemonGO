# SimplePokemonGO
## 引言
![go](https://github.com/txfs1926/SimplePokemonGO/blob/master/doc/go.jpg?raw=true)

Niantic 旗下手机游戏《Pokemon GO》如今已经是一款火遍全球的社交游戏，无论是只在电视里看过《宠物小精灵》动画片的人，还是精通宝可梦的“宝学家”，都沉迷在宝可梦的交换与对战的乐趣当中。截至2019年10月，数据显示，《Pokemon GO》在全球下载量已超过 5.41 亿次，平均每次下载营收为 5.60 美元。每年，《Pokemon GO》都会更新新种类的宝可梦，增加新的游玩方式和活动，来吸引全球越来越多的玩家，加入到Pokemon粉丝大家庭。

然而《Pokemon GO》并没有进入中国大陆市场，对于在中国大陆地区的宝可梦粉丝来说，不能参与到全球玩家的行列当中实在是很大的一种遗憾。狂热的宝可梦粉丝虽然也会采用修改IP、GPS等“开飞机”的手段，试图绕过验证系统来体验这款游戏，但由于使用的不是中国大陆地图，玩家们没办法真正走出房间，来到户外亲身体验探险、发现宝可梦并将它们全部捕捉的乐趣。

于是，本项目将尝试借助Azure Maps，实现一个简易版《Pokemon GO》，并将其命名为《SimplePokemonGO》。相信这个项目可以真正让全球每一个角落的玩家都能体验这款时下最流行的户外探险游戏。

## Get started
### 创建Azure Maps资源
Azure Maps 为各行各业的开发人员提供强大的地理空间功能，并搭配了可用于为 Web 和移动应用程序提供地理环境的最新地图数据。虽然Azure Maps对中国大陆、日本等地区的支持仍不够充分和完善，但本项目完全由经纬度操作，因此只要用户有一个国外IP，便仍可以使用这一套服务，并体验我们的简易版《Pokemon GO》。下面将介绍Azure Maps服务的开通方法。
1. 打开Microsoft Azure 门户网站(https://portal.azure.com)
如果你不曾拥有一个Azure账户，可以访问(https://azure.microsoft.com/en-us/)
创建一个免费Azure账户。

![Azure1](https://github.com/txfs1926/SimplePokemonGO/blob/master/doc/a1.jpg?raw=true)

2. 创建一个资源，在搜索框中输入“maps”，找到Azure Maps，选择订阅、资源组、名称和“标准 S1”定价层后，创建该服务。

![Azure2](https://github.com/txfs1926/SimplePokemonGO/blob/master/doc/a2.jpg?raw=true)

3. 进入该资源，选择设置下的身份验证选项卡，将主密钥复制下来，暂时记录到某个地方，后面会用到。

![Azure3](https://github.com/txfs1926/SimplePokemonGO/blob/master/doc/a3.jpg?raw=true)

4. 如果你希望对Azure Maps有进一步的了解，可以访问文档https://docs.microsoft.com/zh-cn/azure/azure-maps/index
### 下载SimplePokemonGO项目并使用
顺利完成了上述创建Azure Maps资源的准备工作后，还要做一些SimplePokemonGO项目使用前的准备。
1. 打开项目主页https://github.com/txfs1926/SimplePokemonGO
下载这个项目（或者在shell中使用命令`git clone https://github.com/txfs1926/SimplePokemonGO.git`）
2. 使用你喜欢的文本编辑器，打开目录下index.js文件，并查找代码中的subscriptionKey，将之前记录的主密钥粘贴到冒号后面部分,这样一来就可以向AzureMaps APIs发送请求获取服务。修改完毕后记得保存。
3. 用浏览器打开index.html文件，开始体验SimplePokemonGO。
## 体验SimplePokemonGO
下面是一段简短的演示：

![gif](https://github.com/txfs1926/SimplePokemonGO/blob/master/doc/GIF.gif?raw=true)

进入主页，我们可以看到大量宝可梦分布在了中国大陆地区的各个景点，想必这是真实的Pokemon GO所看不到的景象。
![main](https://github.com/txfs1926/SimplePokemonGO/blob/master/doc/main.jpg?raw=true)
通过点击右上角的+、-按钮可以缩放地图，当然如果是电脑端或手机端访问，用鼠标滚轮和手势缩放更为便利。点击右上角的![icon](https://github.com/txfs1926/SimplePokemonGO/blob/master/images/GpsIcon.png?raw=true)便可以定位到用户真实位置（为了让定位功能不受Azure Maps支持地区限制，这里使用`Geolocation`接口提供的`Geolocation.getCurrentPosition()`方法用来获取设备当前位置，中国大陆地区用户可能只能获得粗略定位），当然请注意允许该程序使用定位功能，否则会获取失败，影响后面的游戏。

我们可以点击地图上一个精灵球图标，查看这只宝可梦的基本信息，可以在弹出的框中看到这只宝可梦的名字和图标，以及所在地和邮编，下半部分有距离当前中心光标指向的位置的距离，还有这只宝可梦的等级，以及一个关于这只宝可梦详细信息的链接，点击后在新的窗口可以看到这只pm的百科信息（感谢https://wiki.52poke.com/wiki/
）。

![info](https://github.com/txfs1926/SimplePokemonGO/blob/master/doc/pokemon%20info.jpg?raw=true)

我们还可以看到一个写有Capture的按钮，点击它便可以开始对这只pm的捕捉。
![captureFailed](https://github.com/txfs1926/SimplePokemonGO/blob/master/doc/capture%20failed.jpg?raw=true)

也许你会发现捕捉提示失败，并给出了用户和宝可梦的经纬度，这是因为你与它的距离太远，接下来尝试捕获与你距离近的宝可梦。

![captureSuccess](https://github.com/txfs1926/SimplePokemonGO/blob/master/doc/capture%20success.jpg?raw=true)

捕捉家门口的皮卡丘成功！让我们在宝可梦收藏里查看我们的收获吧。点击左侧按钮![bag](https://github.com/txfs1926/SimplePokemonGO/blob/master/images/Bag.png?raw=true)可以在弹出的小窗口中看到我们的新伙伴。

![collection](https://github.com/txfs1926/SimplePokemonGO/blob/master/doc/collection.jpg?raw=true)

左侧是一个搜索框，输入地名后（例如Beijing），点击按钮![search](https://github.com/txfs1926/SimplePokemonGO/blob/master/images/SearchIcon.png?raw=true)（或者按下回车键），地图会自动切换至这个位置，并在左侧显示这附近出现的宝可梦和地址与距离信息。
## 生成Pokemon
在本项目“根目录/doc/生成Pokemon”目录下，给出了宝可梦数据的生成教程和脚本，如果你希望让地图更加热闹起来，请参阅该目录下的教程`genData.ipynb`。
## 其他
你可以尝试将这个项目部署到自己的Azure服务器上，并将网址分享给自己的好友让他们参与体验，如果你有国外的朋友，不妨参照上方给出的教程，生成一些在国外的宝可梦。另外，本项目对手机体验也做了一定的适配，效果图如下。
![mobile](https://github.com/txfs1926/SimplePokemonGO/blob/master/doc/mobile.jpg?raw=true)

## 总结
至此，这里对SimplePokemonGO的介绍暂时告一段落，虽然与真实的《Pokemon GO》在游戏体验方面还有着不小的差距，但Azure Maps服务的支持下，该项目还是为中国大陆玩家开放了一个小窗口。希望Azure Maps完全支持中国大陆地区和《Pokemon GO》登陆中国大陆地区的日子早日到来！
