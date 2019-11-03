# SimplePokemonGO
## 引言
Niantic 旗下手机游戏《Pokemon GO》如今已经是一款火遍全球的社交游戏，无论是只在电视里看过《宠物小精灵》动画片的人，还是精通宝可梦的“宝学家”，都沉迷在宝可梦的交换与对战的乐趣当中。截至2019年10月，数据显示，《Pokemon GO》在全球下载量已超过 5.41 亿次，平均每次下载营收为 5.60 美元。每年，《Pokemon GO》都会更新新种类的宝可梦，增加新的游玩方式和活动，来吸引全球越来越多的玩家，加入到Pokemon粉丝大家庭。

然而《Pokemon GO》并没有进入中国大陆市场，对于在中国大陆地区的宝可梦粉丝来说，不能参与到全球玩家的行列当中实在是很大的一种遗憾。狂热的宝可梦粉丝虽然也会采用修改IP、GPS等“开飞机”的手段，试图绕过验证系统来体验这款游戏，但由于使用的不是中国大陆地图，玩家们没办法真正走出房间，来到户外亲身体验探险、发现宝可梦并将它们全部捕捉的乐趣。

于是，本项目将尝试借助Azure Maps，实现一个简易版《Pokemon GO》，并将其命名为《SimplePokemonGO》。相信这个项目可以真正让全球每一个角落的玩家都能体验这款时下最流行的户外探险游戏。

## Get started
### 创建Azure Maps资源
Azure Maps 为各行各业的开发人员提供强大的地理空间功能，并搭配了可用于为 Web 和移动应用程序提供地理环境的最新地图数据。虽然Azure Maps对中国大陆、日本等地区的支持仍不够充分和完善，但本项目完全由经纬度操作，因此只要用户有一个国外IP，便仍可以使用这一套服务，并体验我们的简易版《Pokemon GO》。下面将介绍Azure Maps服务的开通方法。
1. 打开Microsoft Azure 门户网站https://portal.azure.com。如果你不曾拥有一个Azure账户，可以访问https://azure.microsoft.com/en-us/，创建一个免费Azure账户。
2. 创建一个资源，在搜索框中输入“maps”，找到Azure Maps，选择订阅、资源组、名称和“标准 S1”定价层后，创建该服务。
3. 进入该资源，选择设置下的身份验证选项卡，将主密钥复制下来，暂时记录到某个地方，后面会用到。
### 下载SimplePokemonGO项目并使用
顺利完成了上述创建Azure Maps资源的准备工作后，还要做一些SimplePokemonGO项目使用前的准备。
1. 打开项目主页https://github.com/txfs1926/SimplePokemonGO，下载这个项目（或者在shell中使用命令`git clone https://github.com/txfs1926/SimplePokemonGO.git`）
2. 使用你喜欢的文本编辑器，打开目录下index.js文件，并查找代码中的subscriptionKey，将之前记录的主密钥粘贴到冒号后面部分,这样一来就可以向AzureMaps APIs发送请求获取服务。修改完毕后记得保存。
3. 用浏览器打开index.html文件，开始体验SimplePokemonGO。
