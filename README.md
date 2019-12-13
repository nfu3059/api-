# api
|  发布日期 | 2019-12-07 |
 | -- | -- |
 |  名称 | magic images |
 |  文件现状 | 已完成 |
 |  文件的主人 |  刘主茵|
 |  领头的设计师 | 刘主茵 |
 |  领头的开发者 |  刘主茵|
 |  领头的测试者 |  刘主茵 |
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
## （二）核心价值：（最小可行性产品）
1. 置换景观图片中的天空，使得图片更美观或有创意。
2. 将人物照中的人物抠像出来美颜后，供用户进行二次创作
3. 提供人脸融合的功能实现多张脸的自然融合，供用户娱乐和满足用户的好奇心。
## （三）背景：
当今的美颜相机十分的多，但是旗下的效果过于丰富使得用户眼花缭乱。并且目前市面的美图软件主要功能集中在人脸的美颜，对图片的创意二次制作较少。
## （四）目的：
设计一款可以让用户进行简单的二次创作生成有趣图片的产品
## （五）用户：16-30岁的年轻群体，主要是以女性为主
## （六）用户痛点：
1. 较少以二次创作功能为主的产品
2. 手机的图片编辑软件有一定的操作困难，例如抠图边缘难切合
3. 风景照，天空如果灰沉沉十分影响美观度
4. 流行的美图软件提供的多脸合成只是简单了置换五官，没有进行融合。
## （七）用户需求:（使用的人工智能要反映到需求列表中）
| 用户案例	| 对应标题	| 重要程度 |
| -- | -- | -- |
| 一个18岁的女生想要和朋友的相片合成，看看合成后的样貌	| Face++通过人脸融合生成两人面孔合成后的长相	|高  |
| 一个女士想要为自己拍的家庭照换一个更好看的背景	| Face++通过人物抠像并美颜后供用户选择背景进行置换	|  中|
| 一个女士想分享一张花草的风景照但是图中的天空太暗沉影响美观| 使用Face++无限天空置换图中的天空  |低|

### 具体应用场景
1. 用户认为图片有缺陷想要修改
2. 用户想要改变照片中人物所处的背景
3. 用户需要合成人像作创意制作
## （九）使用者交互与设计（axure产品原型）-首页

![首页](https://raw.githubusercontent.com/nfu3059/api-end/master/%E9%A6%96%E9%A1%B5.png)

## （十一）API的运用：
1. Face++人体抠像API：
* 接口描述：识别传入图片中人体的完整轮廓，进行人形抠像。
* 接口地址：https://api-cn.faceplusplus.com/humanbodypp/v2/segment
* 请求方法：POST
* 输入
```
代码示例：import urllib.request
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
* 成功后的后台返回

![后台返回](https://raw.githubusercontent.com/nfu3059/api-end/master/%E6%8A%A0%E5%83%8F%E6%88%90%E5%8A%9F.JPG)

* 使用效果示例：

![效果图](https://gitee.com/NFUNM059/api-toend/raw/master/images/%E6%95%88%E6%9E%9C%E5%9B%BE.jpg)

* 测试后存在的问题

![抠图问题图](https://gitee.com/NFUNM059/api-toend/raw/master/images/%E6%95%88%E6%9E%9C%E5%9B%BE.jpg)

** 可以看到因为图中还有出现其他人脸，因此它会将图片中所有的人像扣除，无法指定特定的人，因此需要用户选择背景无其他人的图片进行构图或者通过剪切将多余的人像清除**
2. Face++人脸融合：
* 接口描述：使用本 API，可以对模板图和融合图中的人脸进行融合操作。融合后的图片中将包含融合图中的人脸特征，以及模板图中的其他外貌特征与内容。返回值是一段 JSON，包含融合完成后图片的 Base64 编码。
* 接口地址：https://api-cn.faceplusplus.com/imagepp/v1/mergeface
* 请求方法：POST
具体代码与上差异较小
* 使用效果示例：

![效果图](https://gitee.com/NFUNM059/api-toend/raw/master/images/%E6%95%88%E6%9E%9C%E5%9B%BE.jpg)

* 测试后存在的问题

![人脸问题](https://gitee.com/NFUNM059/api-toend/raw/master/images/%E5%90%88%E6%88%90%E5%90%8E.JPG)

**可以看到如果人脸的选择的是不同性别的，无法选择以女性特征为主还是以男性特征，一些男性的特征较强融合后会有违和感，可以满足一部分用户的需求，但不能满足所有的用户 **

3. Face++人脸美颜
* 接口描述：对图片进行美颜和美白。
* 接口地址：https://api-cn.faceplusplus.com/facepp/v1/beautify
* 请求方法：POST
具体代码与上差异较小

4. Face++无限天空
* 接口描述：置换图片中的天空
* 接口地址：https://api-cn.faceplusplus.com/facepp/v1/
* 请求方法：POST
具体代码与上差异较小



## （十二）AI产品概率性：
Face++的图像识别技术，有三大优点：
1.	准确
全球领先的识别准确率， 经过各行业应用检验

2. 快速

使用Face++云服务或离线能力，无需等待，读懂世界

3. 可靠

支持高并发承载与高可用性保证。我们提供全方位的服务保障	

## (十三)API使用风险评估
- API错误率：
1. 对于图片清晰度不高的照片，进行抠图时会存在偏差
2. 天空的边界检测会有不准确的情况
3. 人脸融合需要用户提供面容清晰和完整无遮挡的脸，否则将杂物融合进去

- 错误现象处理办法：
1. 设置图片的抠图边缘值，增加容错率。
2. 加深图片线条感后在进行检测置换
3. 设置提醒让用户选择符合条件的图片

