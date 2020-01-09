[toc]
# api
| 发布日期 | 2019-12-07 |
 | -- | -- |
 | 名称 | magic images |
 | 文件现状 | 已完成 |
 | 文件的主人 | 刘主茵|
 | 领头的设计师、开发者、测试者 | 刘主茵 |
 # 目录
* [（一）加值宣言]()
* [（二）核心价值]()
* [（三）价值策略]()
* [（四）背景]()
* [（五）目的]()
* [（六）用户]()
  * [用户调研：访谈法（6人）]()
  * [用户痛点]()
  * [用户需求]()
  * [用户画像]()
* [（七）具体应用场景]()
* [(八）人工智能概率性]()
* [（八）使用者交互与设计（axure产品原型）]()
  * [交互及界面设计]()
  * [信息设计]()
    1. 主要功能
    2. 上传图片，一键合成
    3. 分享效果图
    4. 发布内容
  * [原型文档]()
  * [口头操作说明]()
* [（九）API的运用]()
  * [API.使用水平]()
    1. Face++人体抠像API：
    2. Face++人脸融合：
    3. Face++人脸美颜
    4. Face++无限天空
    5. base64编码转换为图片
* [（十）API.使用比较分析]()
   * [Face++的图像识别技术优点]()
   * [其他同类图像处理api]()
   * [价格对比]()
* [(十一）API.使用后风险报告]()
   * [API错误率]()
   * [错误现象处理办法]()
   * [API使用文档]()
# 价值主张设计：
设计一款供用户恶搞图片的产品，让用户可以二次创作图片，为图片置换背景、融合图像等。

本产品主要提供三种功能，第一是使用Face++无限天空api检测出图片中的天空部分并且置换为用户选择的其他天空背景图，从而美化图片制造更多可能性。
第二是使用Face++的人脸美颜和人物抠像功能将图片中的人物独立出来并且进行自然美颜，然后供用户添加自己喜欢的背景图进行二次创作。
第三是使用Face++的人脸融合api让用户可以选择两张脸进行合成，提供趣味性。
## （一）加值宣言：
1. Face++无限天空，精准语义分割，全自动天空替换，支持蓝天白云、彩虹、星空、极光等各种天空替换，适应各种场景和多种素材。
2. Face++人脸美颜api可以基于高精度的人脸关键点，实现贴合脸型的智能美颜，并且能根据不同光照场景实现自然的美颜效果。
3. Face++人物抠像api，识别出图像中人体的轮廓范围，与背景进行区分，适应人体位置重叠场景和各种人体姿态。
4. Face++人脸融合对模板图和融合图中的人脸进行人脸融合操作，并返回融合后的模板图片。其融合效果自然逼真，不限模板数量，融合比例灵活。
5. 及时引进新型的智能图片技术
## （二）核心价值：（最小可行性产品）
产品让用户可以利用提供的三种核心功能来进行图片的二次创作。
1. 置换景观图片中的天空，使得图片更美观或有创意。
2. 将人物照中的人物抠像出来美颜后，供用户进行二次创作
3. 提供人脸融合的功能实现多张脸的自然融合，供用户娱乐和满足用户的好奇心。
## (三）价值策略
当前的图片处理软件较多，其提供的功能也较为齐全和专业，在这方面本产品的竞争力度较弱。而本产品主要以操作简洁明了，界面清晰、功能明确为主要价值吸引点，具有一定的娱乐性，主要面向年轻群体，后续会更新其它更有趣的一键图片处理功能。
## （四）背景：
当今的美颜相机十分的多，但是旗下的效果过于丰富使得用户眼花缭乱。并且目前市面的美图软件主要功能集中在人脸的美颜，对图片的创意二次制作较少。在抠图方面，一些软件表现的性能并不稳定，差错比较多。而且有越来越多的用户喜欢使用移动设备进行简单的图片处理和美化，因此在这方面的产品还是可以依据自身的特色和功能获得自己的用户群体的。
## （五）目的：
设计一款可以让用户进行简单的二次创作生成有趣图片的产品
## （六）用户
年龄：16-30岁的年轻群体

性别：主要是以女性为主

个性和特征：追求简便明了的操作、喜欢对图片稍加美化、有创意
* 用户画像
![用户画像](https://github.com/nfu3059/api-end/blob/master/yonghuhuaxiang.jpg)
## （七）用户调研：访谈法（6人）
* 问题
1. 你平常经常使用处理图片的软件么？
2. 你觉得市面上的图片处理软件有什么缺点？
3. 你期待图片处理软件能有什么新功能？
4. 一个能一键抠图让你置换背景的软件吸引你么？
5. 你对人脸的合成感兴趣吗？
6. 你觉得通过置换图片中的天空来增加图片美观度是可行的么？ 

* 调研结果

| 调研结果| 
| -- |
| 调查用户的图片软件的使用度为适中水平| 
| 其认为目前的图片处理软件主要有清晰度下降、操作复杂、功能性不全的缺点| 
| 期待抠图更智能化、更个性化、滤镜更多、一键换底，并且保持图片清晰度| 
| 大部分认为一键抠图实用但不够吸引| 
| 认为是可行的| 
## （八）用户痛点：
1. 较少以二次创作功能为主的产品
2. 手机的图片编辑软件有一定的操作困难，例如抠图边缘难切合
3. 风景照，天空如果灰沉沉十分影响美观度
4. 流行的美图软件提供的多脸合成只是简单了置换五官，没有进行融合。
## （九）用户需求:（使用的人工智能要反映到需求列表中）
| 用户案例 | 对应标题 | 重要程度 |
| -- | -- | -- |
| 一个18岁的女生想要和朋友的相片合成，看看合成后的样貌 | Face++通过人脸融合生成两人面孔合成后的长相 |高 |
| 一个女士想要为自己拍的家庭照换一个更好看的背景 | Face++通过人物抠像并美颜后供用户选择背景进行置换 | 中|
| 一个女士想分享一张花草的风景照但是图中的天空太暗沉影响美观| 使用Face++无限天空置换图中的天空 |低|
## (十）具体应用场景
1. 用户认为图片有缺陷想要修改
2. 用户想要改变照片中人物所处的背景
3. 用户需要合成人像作创意制作
## （十一）使用者交互与设计（axure产品原型）
* 产品架构

![产品架构图](https://github.com/nfu3059/api-end/blob/master/%E4%BA%A7%E5%93%81%E6%A1%86%E6%9E%B6%E5%9B%BE.jpg)

* 产品操作流程
![产品流程图](https://github.com/nfu3059/api-end/blob/master/%E4%BA%A7%E5%93%81%E6%B5%81%E7%A8%8B%E5%9B%BE.jpg)

### 交互及界面设计
* APP界面图
![界面图](https://github.com/nfu3059/api-end/blob/master/%E6%80%BB%E9%A1%B5%E9%9D%A2.jpg)

1. 在magic首页中的人物照，使用Face++的人脸美颜和人物抠像功能将图片中的人物独立出来并且进行自然美颜，用户可以挑选背景直接进行二次创作。
2. 在magic首页中的风景照，使用Face++无限天空api检测出图片中的天空部分并且置换为用户选择的其他天空背景图。
3. 在magic首页中的人脸融合，使用Face++的人脸融合api使得用户可以选择两张脸进行人脸自然的融合。
### 信息设计
#### 1. 主要功能
![主要功能](https://github.com/nfu3059/api-end/blob/master/%E9%A6%96%E9%A1%B5.jpg)
#### 2. 上传图片，一键合成
![添加图片](https://github.com/nfu3059/api-end/blob/master/%E4%BA%BA%E7%89%A9%E7%85%A7.jpg)
#### 3. 分享效果图
![分享图片](https://github.com/nfu3059/api-end/blob/master/%E4%BA%BA%E7%89%A9%E8%BE%93%E5%87%BA%E7%BB%93%E6%9E%9C.jpg)
#### 4. 发布内容
![发布内容](https://github.com/nfu3059/api-end/blob/master/%E5%8F%91%E5%B8%83.jpg)
### 原型文档
[原型链接](http://nfunm059.gitee.io/magic-images)
### 口头操作说明
产品用户可以使用此产品进行简单的图片再创作，操作简单编辑，用户根据自身需求点击人物照、风景照或人脸融合，只需要上传相应的图片即可一键生成效果图。人物照可以对人物进行截取并与用户选择的背景合成，风景照则是将用户上传的风景图当中的天空进行置换，而人脸融合则是用户可以通过拍照或上传图片的方式将人脸上传，点击合成，产品就会生成自然的合成图。
## （十二）API的运用：
### API.使用水平
#### 1. Face++人体抠像API：
* 接口描述：识别传入图片中人体的完整轮廓，进行人形抠像。
* 接口地址：https://api-cn.faceplusplus.com/humanbodypp/v2/segment
* 请求方法：POST
* 输入
```
代码示例：

import urllib.request
import urllib.error
import time

http_url = 'https://api-cn.faceplusplus.com/humanbodypp/v2/segment'
key = "_jXbMw1QVFqVtk-adtYw7NAQqPB9BIQp"
secret = "FtUxmlgjwcy8GRoIV9bXDpdZev****"
filepath = r"Desktop/test.jpg"

boundary = '----------%s' % hex(int(time.time() * 1000))
data = []
data.append('--%s' % boundary)
data.append('Content-Disposition: form-data; name="%s"\r\n' % 'api_key')
data.append(key)
data.append('--%s' % boundary)
data.append('Content-Disposition: form-data; name="%s"\r\n' % 'api_secret')
data.append(secret)
data.append('--%s' % boundary)
fr = open(filepath, 'rb')
data.append('Content-Disposition: form-data; name="%s"; filename=" "' % 'image_file')
data.append('Content-Type: %s\r\n' % 'application/octet-stream')
data.append(fr.read())
fr.close()
data.append('--%s' % boundary)
data.append('Content-Disposition: form-data; name="%s"\r\n' % 'return_landmark')
data.append('1')
data.append('--%s' % boundary)
data.append('Content-Disposition: form-data; name="%s"\r\n' % 'return_attributes')
data.append(
    "gender,age,smiling,emotion,skinstatus")
data.append('--%s--\r\n' % boundary)

for i, d in enumerate(data):
    if isinstance(d, str):
        data[i] = d.encode('utf-8')

http_body = b'\r\n'.join(data)

# build http request
req = urllib.request.Request(url=http_url, data=http_body)

# header
req.add_header('Content-Type', 'multipart/form-data; boundary=%s' % boundary)

try:
    # post data to server
    resp = urllib.request.urlopen(req, timeout=5)
    # get response
    qrcont = resp.read()
    # if you want to load as json, you should decode first,
    # for example: json.loads(qrount.decode('utf-8'))
    print(qrcont.decode('utf-8'))
except urllib.error.HTTPError as e:
    print(e.read().decode('utf-8'))

```

* 使用效果示例：

![效果图](https://github.com/nfu3059/api-end/blob/master/%E6%95%88%E6%9E%9C%E5%9B%BE.jpg)

* 测试后存在的问题

![抠图问题图](https://github.com/nfu3059/api-end/blob/master/%E4%BA%BA%E5%83%8F%E6%8A%A0%E5%9B%BE%E5%A4%B1%E8%B4%A5.jpg)

**可以看到因为图中还有出现其他人脸，因此它会将图片中所有的人像扣除，无法指定特定的人，因此需要用户选择背景无其他人的图片进行构图或者通过剪切将多余的人像清除**

#### 2. Face++人脸融合：
* 接口描述：使用本 API，可以对模板图和融合图中的人脸进行融合操作。融合后的图片中将包含融合图中的人脸特征，以及模板图中的其他外貌特征与内容。返回值是一段 JSON，包含融合完成后图片的 Base64 编码。
* 接口地址：https://api-cn.faceplusplus.com/imagepp/v1/mergeface
* 请求方法：POST
具体代码与上差异较小
* 成功后的后台返回

![后台返回](https://github.com/nfu3059/api-end/blob/master/%E6%8A%A0%E5%83%8F%E6%88%90%E5%8A%9F.JPG)

* 测试后存在的问题

![人脸问题](https://github.com/nfu3059/api-end/blob/master/%E5%90%88%E6%88%90%E5%90%8E.JPG)

**可以看到如果人脸的选择的是不同性别的，无法选择以女性特征为主还是以男性特征，一些男性的特征较强融合后会有违和感，可以满足一部分用户的需求，但不能满足所有的用户**

* 避免出现以下事件

| 序号 | 事件 |
 | -- | -- |
|1| 参数 <param>对应的图像无法正确解析,有可能不是一个图像文件、或有数据破损。|
|2 |参数<pam>对应的客户上传的图像像素尺寸太大或太小,图片要求请参照本AP描述。paam>对应图像太大的那个参数的名称|
|3 |无法从参数< param>对应的 image url下载图片,图片URL错误或者无效。|
|4| 参数<paam>对应的客户上传的图像文件太大。本AP要求图片文件大小不超过2MB|
|5 |参数<paam>对应的图片未检测到人脸|
|6 |上传的图片人脸不符合要求。已知情况|
|7| 只有半张脸|
|8 |传入的人脸框格式不符合要求,或者人脸框位于图片外|


#### 3. Face++人脸美颜
* 接口描述：对图片进行美颜和美白。
* 接口地址：https://api-cn.faceplusplus.com/facepp/v1/beautify
* 请求方法：POST
* 测试时美颜的效果较为自然，美颜的痕迹较轻，但是人脸美观度得到的一定的提升，符合产品的需求定位

#### 4. Face++无限天空
* 接口描述：置换图片中的天空
* 接口地址：https://api-cn.faceplusplus.com/facepp/v1/
* 请求方法：POST
* 使用效果

![无限天空](https://github.com/nfu3059/api-end/blob/master/%E7%BD%AE%E6%8D%A2%E5%A4%A9%E7%A9%BA.JPG)

* 该产品还处于测试阶段，其功能稳定性较弱

#### 5. base64编码转换为图片
#### 由于face++所返回的结果是base64编码，因此还需在后台完成编码的转换。
* 提取返回的数据中的抠图结果编码
![编码](https://github.com/nfu3059/api-end/blob/master/%E6%8F%90%E5%8F%96%E5%9B%BE%E7%89%87%E7%9A%84%E7%BC%96%E7%A0%81.JPG)
* 将base64编码转换为图片显示
![转换](https://github.com/nfu3059/api-end/blob/master/%E8%BD%AC%E6%8D%A2.JPG)
### API.使用比较分析
#### Face++的图像识别技术，有三大优点：
1. 准确 全球领先的识别准确率， 经过各行业应用检验

2. 快速 使用Face++云服务或离线能力，无需等待，读懂世界

3. 可靠 支持高并发承载与高可用性保证。我们提供全方位的服务保障 
* 总的来说，Face++的图片处理技术较为成熟和专业，旗下的图片处理产品也在不停的更新和迭代，未来的发展空间较高，并且使用的价格也较为合理，因此主要运用旗下的api接口为本产品的功能加值。
#### 其他同类图像处理api
1. 百度云图片处理，旗下关于图片处理的api功能目前已经较为常见，甚至手机本地编辑即可，因此没有运用在产品的功能上。

![产品](https://github.com/nfu3059/api-end/blob/master/%E7%99%BE%E5%BA%A6%E6%97%97%E4%B8%8B%E4%BA%A7%E5%93%81.JPG)

2.商汤api，旗下的人脸美颜api可以自定义选择妆容进行美颜，但是美颜效果较高，会有点不自然，不是本产品追求的效果。

3.云从科技，旗下的对人脸智能修图功能较为完善，官方文字和视频介绍其会进行脸型五官矫正、祛痘祛瑕疵、黑眼圈修复、高光修复、肤色调整、发丝级分割等修图项，但是并没有开放api文档，无法进行验证和运用。
#### 价格对比
![价格比对](https://github.com/nfu3059/api-end/blob/master/%E4%BB%B7%E6%A0%BC%E6%AF%94%E5%AF%B9.JPG)
* 总结：在商业模式上，云从是B2B模式，而旷世和商汤做B2C更多一点。关于旷视科技、云从科技、商汤这三家提供人脸识别系统供应服务商的收费的问题，它们之间的相互差异表现较大。旷视科技在线API按照调用量统一价格收费和包时收费，SDK可分为联网和离线两种类型，并按照时间和授权设备数收费；云从科技提供在线API和在线与离线SDK，其中在线API按照调用量进行阶梯价格收费，在线SDK按照授权设备数收费，离线SDK须一次性支付费用购买使用。
### API.使用后风险报告
#### API错误率：
1. 对于图片清晰度不高的照片，进行抠图时会存在偏差
2. 天空的边界检测会有不准确的情况
3. 人脸融合需要用户提供面容清晰和完整无遮挡的脸，否则将杂物融合进去

 
#### 错误现象处理办法：
1. 设置图片的抠图边缘值，增加容错率。
2. 加深图片线条感后在进行检测置换
3. 设置提醒让用户选择符合条件的图片

