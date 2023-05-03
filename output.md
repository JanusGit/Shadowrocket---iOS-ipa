# Fiddler抓包工具总结

> https://www.cnblogs.com/yyhh/p/5140852.html

发表日期：2016-01-18 23:43

<div class="blogpost-body blogpost-body-html" id="cnblogs_post_body">
 <h2>
  序章
 </h2>
 <p>
  Fiddler是一个蛮好用的抓包工具，可以将网络传输发送与接受的数据包进行截获、重发、编辑、转存等操作。也可以用来检测网络安全。反正好处多多，举之不尽呀！当年学习的时候也蛮费劲，一些蛮实用隐藏的小功能用了之后就忘记了，每次去网站上找也很麻烦，所以搜集各大网络的资料，总结了一些常用的功能。
 </p>
 <p>
 </p>
 <p>
  Fiddler 下载地址 ：
  <a href="https://www.telerik.com/download/fiddler" rel="noopener" target="_blank">
   https://www.telerik.com/download/fiddler
  </a>
 </p>
 <p>
  Fiddler 离线下载地址：
  <a href="https://pan.baidu.com/s/1bpnp3Ef" rel="noopener" target="_blank">
   https://pan.baidu.com/s/1bpnp3Ef
  </a>
  密码:5skw
 </p>
 <p>
  下载Fiddler要FQ，我费了好大得劲才翻出去下载到…
 </p>
 <p>
  win8之后用“Fiddler for .NET4”而win8之前用“Fiidler for .NET2”比较好
 </p>
 <p>
  <img alt="image" border="0" height="819" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118234152406-1895206856.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="839"/>
 </p>
 <h2>
  1. Fiddler 抓包简介
 </h2>
 <p>
  Fiddler是通过改写HTTP代理，让数据从它那通过，来监控并且截取到数据。当然Fiddler很屌，在打开它的那一瞬间，它就已经设置好了浏览器的代理了。当你关闭的时候，它又帮你把代理还原了，是不是很贴心。。。
 </p>
 <p>
  <img alt="image" border="0" height="849" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118234154922-335265309.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="900"/>
 </p>
 <h5>
 </h5>
 <h3>
  1） 字段说明
 </h3>
 <p>
  Fiddler想要抓到数据包，要确保Capture Traffic是开启，在File –&gt; Capture Traffic。开启后再左下角会有显示，当然也可以直接点击左下角的图标来关闭/开启抓包功能。
 </p>
 <p>
  <img alt="image" border="0" height="845" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118234157312-154346340.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="895"/>
 </p>
 <p>
  Fiddler开始工作了，抓到的数据包就会显示在列表里面，下面总结了这些都是什么意思：
 </p>
 <p>
  <img alt="image" border="0" height="567" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118234158609-143657944.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="867"/>
 </p>
 <table border="0" cellpadding="0" cellspacing="0" style="width: 808px">
  <tbody>
   <tr>
    <th width="157">
     <p align="center">
      <strong>
       名称
      </strong>
     </p>
    </th>
    <th width="649">
     <p align="center">
      <strong>
       含义
      </strong>
     </p>
    </th>
   </tr>
   <tr>
    <td width="161">
     <p align="center">
      #
     </p>
    </td>
    <td width="645">
     <p>
      抓取HTTP Request的顺序，从1开始，以此递增
     </p>
    </td>
   </tr>
   <tr>
    <td width="165">
     <p align="center">
      Result
     </p>
    </td>
    <td width="642">
     <p>
      HTTP状态码
     </p>
    </td>
   </tr>
   <tr>
    <td width="168">
     <p align="center">
      Protocol
     </p>
    </td>
    <td width="639">
     <p>
      请求使用的协议，如HTTP/HTTPS/FTP等
     </p>
    </td>
   </tr>
   <tr>
    <td width="171">
     <p align="center">
      Host
     </p>
    </td>
    <td width="637">
     <p>
      请求地址的主机名
     </p>
    </td>
   </tr>
   <tr>
    <td width="173">
     <p align="center">
      URL
     </p>
    </td>
    <td width="635">
     <p>
      请求资源的位置
     </p>
    </td>
   </tr>
   <tr>
    <td width="175">
     <p align="center">
      Body
     </p>
    </td>
    <td width="634">
     <p>
      该请求的大小
     </p>
    </td>
   </tr>
   <tr>
    <td width="176">
     <p align="center">
      Caching
     </p>
    </td>
    <td width="633">
     <p>
      请求的缓存过期时间或者缓存控制值
     </p>
    </td>
   </tr>
   <tr>
    <td width="177">
     <p align="center">
      Content-Type
     </p>
    </td>
    <td width="632">
     <p>
      请求响应的类型
     </p>
    </td>
   </tr>
   <tr>
    <td width="178">
     <p align="center">
      Process
     </p>
    </td>
    <td width="632">
     <p>
      发送此请求的进程：进程ID
     </p>
    </td>
   </tr>
   <tr>
    <td width="178">
     <p align="center">
      Comments
     </p>
    </td>
    <td width="632">
     <p>
      允许用户为此回话添加备注
     </p>
    </td>
   </tr>
   <tr>
    <td width="178">
     <p align="center">
      Custom
     </p>
    </td>
    <td width="632">
     <p>
      允许用户设置自定义值
     </p>
    </td>
   </tr>
   <tr>
    <td width="178">
     <p align="center">
      图标
     </p>
    </td>
    <td width="632">
     <p>
      含义
     </p>
    </td>
   </tr>
   <tr>
    <td width="178">
     <p align="center">
      <img alt="clip_image001[13]" border="0" height="17" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118234159468-1047137951.gif" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="clip_image001[13]" width="13"/>
     </p>
    </td>
    <td width="632">
     <p>
      请求已经发往服务器
     </p>
    </td>
   </tr>
   <tr>
    <td width="178">
     <p align="center">
      <img alt="clip_image002[4]" border="0" height="17" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118234200047-1757509080.gif" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="clip_image002[4]" width="13"/>
     </p>
    </td>
    <td width="632">
     <p>
      已从服务器下载响应结果
     </p>
    </td>
   </tr>
   <tr>
    <td width="178">
     <p align="center">
      <img alt="clip_image003[4]" border="0" height="17" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118234201406-1416873112.gif" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="clip_image003[4]" width="15"/>
     </p>
    </td>
    <td width="632">
     <p>
      请求从断点处暂停
     </p>
    </td>
   </tr>
   <tr>
    <td width="178">
     <p align="center">
      <img alt="clip_image004[4]" border="0" height="17" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118234202375-1737717316.gif" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="clip_image004[4]" width="15"/>
     </p>
    </td>
    <td width="632">
     <p>
      响应从断点处暂停
     </p>
    </td>
   </tr>
   <tr>
    <td width="178">
     <p align="center">
      <img alt="clip_image005[4]" border="0" height="16" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118234202812-1354392122.gif" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="clip_image005[4]" width="16"/>
     </p>
    </td>
    <td width="632">
     <p>
      请求使用 HTTP 的 HEAD 方法，即响应没有内容（Body）
     </p>
    </td>
   </tr>
   <tr>
    <td width="178">
     <p align="center">
      <img alt="clip_image006[4]" border="0" height="17" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118234203515-1304170577.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="clip_image006[4]" width="16"/>
     </p>
    </td>
    <td width="632">
     <p>
      请求使用 HTTP 的 POST 方法
     </p>
    </td>
   </tr>
   <tr>
    <td width="178">
     <p align="center">
      <img alt="clip_image007[4]" border="0" height="15" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118234204531-965189067.gif" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="clip_image007[4]" width="14"/>
     </p>
    </td>
    <td width="632">
     <p>
      请求使用 HTTP 的 CONNECT 方法，使用 HTTPS 协议建立连接隧道
     </p>
    </td>
   </tr>
   <tr>
    <td width="178">
     <p align="center">
      <img alt="clip_image008[4]" border="0" height="17" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118234205547-1927498766.gif" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="clip_image008[4]" width="15"/>
     </p>
    </td>
    <td width="632">
     <p>
      响应是 HTML 格式
     </p>
    </td>
   </tr>
   <tr>
    <td width="178">
     <p align="center">
      <img alt="clip_image009[4]" border="0" height="17" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118234206203-722749081.gif" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="clip_image009[4]" width="15"/>
     </p>
    </td>
    <td width="632">
     <p>
      响应是一张图片
     </p>
    </td>
   </tr>
   <tr>
    <td width="178">
     <p align="center">
      <img alt="clip_image010[4]" border="0" height="16" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118234207000-575730385.gif" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="clip_image010[4]" width="16"/>
     </p>
    </td>
    <td width="632">
     <p>
      响应是脚本格式
     </p>
    </td>
   </tr>
   <tr>
    <td width="178">
     <p align="center">
      <img alt="clip_image011[4]" border="0" height="17" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118234207625-740567358.gif" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="clip_image011[4]" width="16"/>
     </p>
    </td>
    <td width="632">
     <p>
      响应是 CSS 格式
     </p>
    </td>
   </tr>
   <tr>
    <td width="178">
     <p align="center">
      <img alt="clip_image012[4]" border="0" height="17" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118234208297-916097140.gif" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="clip_image012[4]" width="17"/>
     </p>
    </td>
    <td width="632">
     <p>
      响应是 XML 格式
     </p>
    </td>
   </tr>
   <tr>
    <td width="178">
     <p align="center">
      <img alt="clip_image013[4]" border="0" height="17" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118234209640-1298497869.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="clip_image013[4]" width="16"/>
     </p>
    </td>
    <td width="632">
     <p>
      响应是 JSON 格式
     </p>
    </td>
   </tr>
   <tr>
    <td width="178">
     <p align="center">
      <img alt="clip_image014[4]" border="0" height="16" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118234210172-1709733575.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="clip_image014[4]" width="14"/>
     </p>
    </td>
    <td width="632">
     <p>
      响应是一个音频文件
     </p>
    </td>
   </tr>
   <tr>
    <td width="178">
     <p align="center">
      <img alt="clip_image015[4]" border="0" height="16" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118234210703-1810906238.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="clip_image015[4]" width="15"/>
     </p>
    </td>
    <td width="632">
     <p>
      响应是一个视频文件
     </p>
    </td>
   </tr>
   <tr>
    <td width="178">
     <p align="center">
      <img alt="clip_image016[4]" border="0" height="15" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118234211297-1181901939.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="clip_image016[4]" width="16"/>
     </p>
    </td>
    <td width="632">
     <p>
      响应是一个 SilverLight
     </p>
    </td>
   </tr>
   <tr>
    <td width="178">
     <p align="center">
      <img alt="clip_image017[4]" border="0" height="16" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118234213515-1617989240.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="clip_image017[4]" width="13"/>
     </p>
    </td>
    <td width="632">
     <p>
      响应是一个 FLASH
     </p>
    </td>
   </tr>
   <tr>
    <td width="178">
     <p align="center">
      <img alt="clip_image018[4]" border="0" height="16" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118234214140-838447913.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="clip_image018[4]" width="14"/>
     </p>
    </td>
    <td width="632">
     <p>
      响应是一个字体
     </p>
    </td>
   </tr>
   <tr>
    <td width="178">
     <p align="center">
      <img alt="clip_image019[4]" border="0" height="15" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118234214828-810550242.gif" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="clip_image019[4]" width="13"/>
     </p>
    </td>
    <td width="632">
     <p>
      普通响应成功
     </p>
    </td>
   </tr>
   <tr>
    <td width="178">
     <p align="center">
      <img alt="clip_image020[4]" border="0" height="14" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118234215406-1088186512.gif" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="clip_image020[4]" width="14"/>
     </p>
    </td>
    <td width="632">
     <p>
      响应是 HTTP/300、301、302、303 或 307 重定向
     </p>
    </td>
   </tr>
   <tr>
    <td width="178">
     <p align="center">
      <img alt="clip_image021[4]" border="0" height="16" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118234216015-2008519780.gif" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="clip_image021[4]" width="17"/>
     </p>
    </td>
    <td width="632">
     <p>
      响应是 HTTP/304（无变更）：使用缓存文件
     </p>
    </td>
   </tr>
   <tr>
    <td width="178">
     <p align="center">
      <img alt="clip_image022[4]" border="0" height="18" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118234216531-1803780843.gif" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="clip_image022[4]" width="12"/>
     </p>
    </td>
    <td width="632">
     <p>
      响应需要客户端证书验证
     </p>
    </td>
   </tr>
   <tr>
    <td width="178">
     <p align="center">
      <img alt="clip_image023[4]" border="0" height="14" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118234217078-1617370921.gif" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="clip_image023[4]" width="14"/>
     </p>
    </td>
    <td width="632">
     <p>
      服务端错误
     </p>
    </td>
   </tr>
   <tr>
    <td width="178">
     <p align="center">
      <img alt="clip_image0244" border="0" height="17" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160119000324093-1538967179.gif" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="clip_image0244" width="16"/>
     </p>
    </td>
    <td width="632">
     <p>
      会话被客户端、Fiddler 或者服务端终止
     </p>
    </td>
   </tr>
  </tbody>
 </table>
 <p>
 </p>
 <h5>
 </h5>
 <h3>
  2）. Statistics 请求的性能数据分析
 </h3>
 <p>
  好了。左边看完了，现在可以看右边了
 </p>
 <p>
  随意点击一个请求，就可以看到Statistics关于HTTP请求的性能以及数据分析了（不可能安装好了Fiddler一条请求都没有…）：
 </p>
 <p>
  <img alt="image" border="0" height="736" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118234218890-2133347180.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="723"/>
 </p>
 <h5>
 </h5>
 <h3>
  3）. Inspectors 查看数据内容
 </h3>
 <p>
  Inspectors是用于查看会话的内容，上半部分是请求的内容，下半部分是响应的内容：
 </p>
 <p>
  <img alt="image" border="0" height="547" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160120130545953-2034481316.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="757"/>
 </p>
 <h5>
 </h5>
 <h3>
  4）. AutoResponder 允许拦截指定规则的请求
 </h3>
 <p>
  AutoResponder允许你拦截指定规则的求情，并返回本地资源或Fiddler资源，从而代替服务器响应。
 </p>
 <p>
  看下图5步，我将“baidu”这个关键字与我电脑“f:\Users\YukiO\Pictures\boy.jpeg”这张图片绑定了，点击Save保存后勾选Enable rules，再访问baidu，就会被劫持。
 </p>
 <blockquote>
  <p>
   这个玩意有很多匹配规则，如：
  </p>
  <p>
   1. 字符串匹配（默认）：只要包含指定字符串（不区分大小写），全部认为是匹配
  </p>
  <table border="0" cellpadding="2" cellspacing="0" style="width: 445px">
   <tbody>
    <tr>
     <th valign="top" width="362">
      字符串匹配（baidu）
     </th>
     <th valign="top" width="81">
      是否匹配
     </th>
    </tr>
    <tr>
     <td valign="top" width="362">
      http://www.baidu.com
     </td>
     <td valign="top" width="81">
      匹配
     </td>
    </tr>
    <tr>
     <td valign="top" width="362">
      http://pan.baidu.com
     </td>
     <td valign="top" width="81">
      匹配
     </td>
    </tr>
    <tr>
     <td valign="top" width="362">
      http://tieba.baidu.com
     </td>
     <td valign="top" width="81">
      匹配
     </td>
    </tr>
   </tbody>
  </table>
  <p>
  </p>
  <p>
   2. 正则表达式匹配：以“regex:”开头，使用正则表达式来匹配，这个是区分大小写的
  </p>
  <table border="0" cellpadding="2" cellspacing="0" style="width: 448px">
   <tbody>
    <tr>
     <th valign="top" width="364">
      字符串匹配（regex:.+.(
      <span style="color: rgba(224, 108, 117, 1)">
       jpg
      </span>
      |
      <span style="color: rgba(224, 108, 117, 1)">
       gif
      </span>
      |
      <span style="color: rgba(224, 108, 117, 1)">
       bmp
      </span>
      ) $）
     </th>
     <th valign="top" width="82">
      是否匹配
     </th>
    </tr>
    <tr>
     <td valign="top" width="364">
      http://bbs.fishc.com/Path1/query=foo.
      <span style="color: rgba(75, 172, 198, 1)">
       bmp
      </span>
      &amp;bar
     </td>
     <td valign="top" width="82">
      不匹配
     </td>
    </tr>
    <tr>
     <td valign="top" width="364">
      http://bbs.fishc.com/Path1/query=example.
      <span style="color: rgba(75, 172, 198, 1)">
       gif
      </span>
     </td>
     <td valign="top" width="82">
      匹配
     </td>
    </tr>
    <tr>
     <td valign="top" width="364">
      http://bbs.fishc.com/Path1/query=example.
      <span style="color: rgba(75, 172, 198, 1)">
       bmp
      </span>
     </td>
     <td valign="top" width="82">
      匹配
     </td>
    </tr>
    <tr>
     <td valign="top" width="364">
      http://bbs.fishc.com/Path1/query=example.
      <span style="color: rgba(75, 172, 198, 1)">
       Gif
      </span>
     </td>
     <td valign="top" width="82">
      不匹配
     </td>
    </tr>
   </tbody>
  </table>
 </blockquote>
 <p>
  <img alt="image" border="0" height="617" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118234219765-703426619.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="896"/>
 </p>
 <p>
  <img alt="image" border="0" height="1020" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118234224843-907043204.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="1077"/>
 </p>
 <p>
 </p>
 <h3>
  4）. Composer 自定义请求发送服务器
 </h3>
 <p>
  Composer允许自定义请求发送到服务器，可以手动创建一个新的请求，也可以在会话表中，拖拽一个现有的请求
 </p>
 <p>
  Parsed模式下你只需要提供简单的URLS地址即可（如下图，也可以在RequestBody定制一些属性，如模拟浏览器User-Agent）
 </p>
 <p>
  <img alt="image" border="0" height="833" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118234227062-846408602.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="894"/>
 </p>
 <p>
 </p>
 <h5>
 </h5>
 <h3>
  5）. Filters 请求过滤规则
 </h3>
 <p>
  Fiters 是过滤请求用的，左边的窗口不断的更新，当你想看你系统的请求的时候，你刷新一下浏览器，一大片不知道哪来请求，看着碍眼，它还一直刷新你的屏幕。这个时候通过过滤规则来过滤掉那些不想看到的请求。
 </p>
 <p>
  <img alt="image" border="0" height="563" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160120125401968-22426265.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="758"/>
 </p>
 <p>
  勾选左上角的Use Filters开启过滤器，这里有两个最常用的过滤条件：Zone和Host
 </p>
 <blockquote>
  <p>
   1、Zone 指定只显示内网（Intranet）或互联网（Internet）的内容：
  </p>
  <p>
   <img alt="image" border="0" height="175" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118235316718-1553324600.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="626"/>
  </p>
  <p>
  </p>
  <p>
   2、Host 指定显示某个域名下的会话：
  </p>
  <p>
   <img alt="image" border="0" height="180" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118235317328-711964625.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="627"/>
  </p>
  <p>
   如果框框为黄色（如图），表示修改未生效，点击红圈里的文字即可
  </p>
 </blockquote>
 <p>
 </p>
 <h5>
 </h5>
 <h4>
  6）. Timeline 请求响应时间
 </h4>
 <p>
  在左侧会话窗口点击一个或多个（同时按下 Ctrl 键），Timeline 便会显示指定内容从服务端传输到客户端的时间：
 </p>
 <p>
  <img alt="image" border="0" height="199" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118235318172-1052872585.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="726"/>
 </p>
 <p>
 </p>
 <h5>
 </h5>
 <h2>
  2. Fiddler 设置解密HTTPS的网络数据
 </h2>
 <p>
  Fiddler可以通过伪造CA证书来欺骗浏览器和服务器。Fiddler是个很会装逼的好东西，大概原理就是在浏览器面前Fiddler伪装成一个HTTPS服务器，而在真正的HTTPS服务器面前Fiddler又装成浏览器，从而实现解密HTTPS数据包的目的。
 </p>
 <p>
  解密HTTPS需要手动开启，依次点击：
 </p>
 <p>
  1. Tools –&gt; Fiddler Options –&gt;  HTTPS
 </p>
 <p>
  <img alt="image" border="0" height="514" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118234228140-2037050814.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="896"/>
 </p>
 <p>
  2. 勾选Decrypt HTTPS Traffic
 </p>
 <p>
  <img alt="image" border="0" height="628" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118234229250-1993071078.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="888"/>
 </p>
 <p>
  3. 点击OK
 </p>
 <p>
  <img alt="image" border="0" height="625" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160118234230343-471116797.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="893"/>
 </p>
 <p>
 </p>
 <h2>
  3. Fiddler 抓取Iphone / Android数据包
 </h2>
 <p>
  想要Fiddler抓取移动端设备的数据包，其实很简单，先来说说移动设备怎么去访问网络，看了下面这张图，就明白了。
 </p>
 <p>
  <img alt="image" border="0" height="830" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160120124738422-909023754.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="1139"/>
 </p>
 <p>
  可以看得出，移动端的数据包，都是要走wifi出去，所以我们可以设置代理或者开启热点，将手机连上电脑，Fiddler开启代理后，让这些数据通过Fiddler，Fiddler就可以抓到这些包，然后发给路由器（如图）：
 </p>
 <p>
  <img alt="" loading="lazy" src="https://img2022.cnblogs.com/blog/626593/202210/626593-20221019124220065-1898451866.png"/>
 </p>
 <p>
 </p>
 <p>
 </p>
 <p>
 </p>
 <p>
  1. 打开Fidder，点击菜单栏中的 [Tools] –&gt; [Fiddler Options]
 </p>
 <p>
  <img alt="image" border="0" height="726" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160120124747047-421831359.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="1050"/>
 </p>
 <p>
  2. 点击 [Connections] ，设置代理端口是8888， 勾选 Allow remote computers to connect， 点击OK
 </p>
 <p>
  <img alt="image" border="0" height="726" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160120124843828-142667262.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="1051"/>
 </p>
 <p>
  4. 这时在 Fiddler 可以看到自己本机无线网卡的IP了（要是没有的话，重启Fiddler，或者可以在cmd中ipconfig找到自己的网卡IP）
 </p>
 <p>
  <img alt="image" border="0" height="730" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160120124848922-1087943477.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="1009"/>
 </p>
 <p>
  <img alt="image" border="0" height="583" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160120124849640-39807059.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="981"/>
 </p>
 <p>
  5. 在手机端连接PC的wifi，并且设置代理IP与端口（代理IP就是上图的IP，端口是Fiddler的代理端口8888）
 </p>
 <p>
  <img alt="image" border="0" height="789" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160120124855281-1725826056.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="932"/>
 </p>
 <p>
 </p>
 <p>
  6. 访问网页输入代理IP和端口，下载Fiddler的证书，点击下图FiddlerRoot certificate
 </p>
 <p>
  <img alt="image" border="0" height="797" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160120124905156-91772621.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="932"/>
 </p>
 <p>
  【注意】：如果打开浏览器碰到类似下面的报错，请打开Fiddler的证书解密模式（Fiddler 设置解密HTTPS的网络数据）
 </p>
 <div class="cnblogs_code" style="background-color: rgba(245, 245, 245, 1); border: 1px solid rgba(204, 204, 204, 1); padding: 5px">
  <pre>No root certificate was found. Have you enabled HTTPS traffic decryption <span style="color: rgba(0, 0, 255, 1)">in</span> Fiddler yet?</pre>
 </div>
 <p>
  <img alt="208B4A022896FE5008CFDBD54105185D" border="0" height="768" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160120124911547-1662798136.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="208B4A022896FE5008CFDBD54105185D" width="432"/>
  <img alt="13D99A1D77D5528F3EFBA0C3DEA3BD28" border="0" height="768" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160120125000187-1387164060.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="13D99A1D77D5528F3EFBA0C3DEA3BD28" width="432"/>
 </p>
 <p>
  <img alt="FDE79CDC9CB62CC6CF68F98C33CB281A" border="0" height="768" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160120125000843-2060195202.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="FDE79CDC9CB62CC6CF68F98C33CB281A" width="432"/>
  <img alt="8F268C0A1192E2DF41BD0F5DEFD525D9" border="0" height="768" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160120125004609-1600396322.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="8F268C0A1192E2DF41BD0F5DEFD525D9" width="432"/>
 </p>
 <p>
 </p>
 <p>
  7. 安装完了证书，可以用手机访问应用，就可以看到截取到的数据包了。（下图选中是布卡漫画的数据包，下面还有QQ邮箱的）
 </p>
 <p>
  <img alt="image" border="0" height="730" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160120125406187-1394564312.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="1189"/>
 </p>
 <p>
 </p>
 <h2>
  4. Fiddler 内置命令与断点
 </h2>
 <p>
  Fiddler还有一个藏的很深的命令框，就是眼前，我用了几年的Fiddler都没有发现它，偶尔在别人的文章发现还有这个小功能，还蛮好用的，整理下记录在这里。
 </p>
 <p>
  FIddler断点功能就是将请求截获下来，但是不发送，这个时候你可以干很多事情，比如说，把包改了，再发送给服务器君。还有balabala一大堆的事情可以做，就不举例子了。
 </p>
 <p>
  <img alt="image" border="0" height="730" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160120125408672-279510487.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="1189"/>
 </p>
 <table border="0" cellpadding="2" cellspacing="0" style="width: 985px">
  <tbody>
   <tr>
    <th valign="top" width="73">
     <p align="center">
      <strong>
       命令
      </strong>
     </p>
    </th>
    <th valign="top" width="93">
     <p align="center">
      <strong>
       对应请求项
      </strong>
     </p>
    </th>
    <th valign="top" width="554">
     <p align="center">
      <strong>
       介绍
      </strong>
     </p>
    </th>
    <th valign="top" width="263">
     <p align="center">
      <strong>
       示例
      </strong>
     </p>
    </th>
   </tr>
   <tr>
    <td width="73">
     <p align="center">
      ?
     </p>
    </td>
    <td width="93">
     <p align="center">
      All
     </p>
    </td>
    <td width="554">
     问号后边跟一个字符串，可以匹配出包含这个字符串的请求
    </td>
    <td width="263">
     <p align="center">
      ?google
     </p>
    </td>
   </tr>
   <tr>
    <td valign="top" width="73">
     <p align="center">
      &gt;
     </p>
    </td>
    <td valign="top" width="93">
     <p align="center">
      Body
     </p>
    </td>
    <td valign="top" width="554">
     大于号后面跟一个数字，可以匹配出请求大小，大于这个数字请求
    </td>
    <td valign="top" width="263">
     <p align="center">
      &gt;1000
     </p>
    </td>
   </tr>
   <tr>
    <td width="73">
     <p align="center">
      &lt;
     </p>
    </td>
    <td width="93">
     <p align="center">
      Body
     </p>
    </td>
    <td width="554">
     小于号跟大于号相反，匹配出请求大小，小于这个数字的请求
    </td>
    <td width="263">
     <p align="center">
      &lt;100
     </p>
    </td>
   </tr>
   <tr>
    <td width="73">
     <p align="center">
      =
     </p>
    </td>
    <td width="93">
     <p align="center">
      Result
     </p>
    </td>
    <td width="554">
     等于号后面跟数字，可以匹配HTTP返回码
    </td>
    <td width="263">
     <p align="center">
      =200
     </p>
    </td>
   </tr>
   <tr>
    <td width="73">
     <p align="center">
      @
     </p>
    </td>
    <td width="93">
     <p align="center">
      Host
     </p>
    </td>
    <td width="554">
     @后面跟Host，可以匹配域名
    </td>
    <td width="263">
     <p align="center">
      @www.baidu.com
     </p>
    </td>
   </tr>
   <tr>
    <td width="73">
     <p align="center">
      select
     </p>
    </td>
    <td width="93">
     <p align="center">
      Content-Type
     </p>
    </td>
    <td width="554">
     select后面跟响应类型，可以匹配到相关的类型
    </td>
    <td width="263">
     <p align="center">
      select image
     </p>
    </td>
   </tr>
   <tr>
    <td width="73">
     <p align="center">
      cls
     </p>
    </td>
    <td width="93">
     <p align="center">
      All
     </p>
    </td>
    <td width="554">
     清空当前所有请求
    </td>
    <td width="263">
     <p align="center">
      cls
     </p>
    </td>
   </tr>
   <tr>
    <td width="73">
     <p align="center">
      dump
     </p>
    </td>
    <td width="93">
     <p align="center">
      All
     </p>
    </td>
    <td width="554">
     将所有请求打包成saz压缩包，保存到“我的文档\Fiddler2\Captures”目录下
    </td>
    <td width="263">
     <p align="center">
      dump
     </p>
    </td>
   </tr>
   <tr>
    <td width="73">
     <p align="center">
      start
     </p>
    </td>
    <td width="93">
     <p align="center">
      All
     </p>
    </td>
    <td width="554">
     开始监听请求
    </td>
    <td width="263">
     <p align="center">
      start
     </p>
    </td>
   </tr>
   <tr>
    <td width="73">
     <p align="center">
      stop
     </p>
    </td>
    <td width="93">
     <p align="center">
      All
     </p>
    </td>
    <td width="554">
     停止监听请求
    </td>
    <td width="263">
     <p align="center">
      stop
     </p>
    </td>
   </tr>
   <tr align="center" valign="middle">
    <th colspan="4" style="text-align: center" width="73">
     <strong>
      断点命令
     </strong>
    </th>
   </tr>
   <tr>
    <td width="73">
     <p align="center">
      bpafter
     </p>
    </td>
    <td width="93">
     <p align="center">
      All
     </p>
    </td>
    <td width="554">
     bpafter后边跟一个字符串，表示中断所有包含该字符串的请求
    </td>
    <td width="263">
     <p align="center">
      bpafter baidu（输入bpafter解除断点）
     </p>
    </td>
   </tr>
   <tr>
    <td width="73">
     <p align="center">
      bpu
     </p>
    </td>
    <td width="93">
     <p align="center">
      All
     </p>
    </td>
    <td width="554">
     跟bpafter差不多，只不过这个是收到请求了，中断响应
    </td>
    <td width="263">
     <p align="center">
      bpu baidu（输入bpu解除断点）
     </p>
    </td>
   </tr>
   <tr>
    <td width="73">
     <p align="center">
      bps
     </p>
    </td>
    <td width="93">
     <p align="center">
      Result
     </p>
    </td>
    <td width="554">
     后面跟状态吗，表示中断所有是这个状态码的请求
    </td>
    <td width="263">
     <p align="center">
      bps 200（输入bps解除断点）
     </p>
    </td>
   </tr>
   <tr>
    <td width="73">
     <p align="center">
      bpv / bpm
     </p>
    </td>
    <td width="93">
     <p align="center">
      HTTP方法
     </p>
    </td>
    <td width="554">
     只中断HTTP方法的命令，HTTP方法如POST、GET
    </td>
    <td width="263">
     <p align="center">
      bpv get（输入bpv解除断点）
     </p>
    </td>
   </tr>
   <tr>
    <td width="73">
     <p align="center">
      g / go
     </p>
    </td>
    <td width="93">
     <p align="center">
      All
     </p>
    </td>
    <td width="554">
     放行所有中断下来的请求
    </td>
    <td width="263">
     <p align="center">
      g
     </p>
    </td>
   </tr>
  </tbody>
 </table>
 <p>
 </p>
 <p>
  示例演示：
 </p>
 <p>
  <strong>
   ?
  </strong>
 </p>
 <p>
  <img alt="image" border="0" height="408" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160120125409703-1678932502.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="684"/>
 </p>
 <p>
  <strong>
   &gt;
  </strong>
 </p>
 <p>
  <img alt="image" border="0" height="408" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160120125414093-255856593.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="684"/>
 </p>
 <p>
  <strong>
   &lt;
  </strong>
 </p>
 <p>
  <img alt="image" border="0" height="408" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160120125414797-2077867027.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="684"/>
 </p>
 <p>
  <strong>
   =
  </strong>
 </p>
 <p>
  <img alt="image" border="0" height="408" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160120125415547-1825599853.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="684"/>
 </p>
 <p>
  <strong>
   @
  </strong>
 </p>
 <p>
  <img alt="image" border="0" height="408" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160120125416093-439467539.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="684"/>
 </p>
 <p>
  <strong>
   select
  </strong>
 </p>
 <p>
  <img alt="image" border="0" height="408" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160120125417734-817450905.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="684"/>
 </p>
 <p>
  <strong>
   cls
  </strong>
 </p>
 <p>
  <img alt="image" border="0" height="408" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160120125418343-1404670131.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="684"/>
 </p>
 <p>
  <strong>
   dump
  </strong>
 </p>
 <p>
  <img alt="image" border="0" height="408" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160120125418906-1712835498.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="718"/>
 </p>
 <p>
 </p>
 <p>
  断点命令：
 </p>
 <p>
  断点可以直接点击Fiddler下图的图标位置，就可以设置全部请求的断点，断点的命令可以精确设置需要截获那些请求。如下示例：
 </p>
 <p>
  <img alt="image" border="0" height="655" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160120125424047-1175695668.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="987"/>
 </p>
 <p>
  命令：
 </p>
 <p>
  <strong>
   bpafter
  </strong>
 </p>
 <p>
  <img alt="image" border="0" height="408" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160120125424797-1724110564.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="718"/>
  <img alt="image" border="0" height="408" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160120125425984-995334279.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="718"/>
 </p>
 <p>
  <strong>
   bps
  </strong>
 </p>
 <p>
  <img alt="image" border="0" height="408" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160120125426687-1642870815.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="681"/>
 </p>
 <p>
  <img alt="image" border="0" height="408" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160120125430750-1560884194.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="681"/>
 </p>
 <p>
 </p>
 <p>
  <strong>
   bpv
  </strong>
 </p>
 <p>
  <img alt="image" border="0" height="408" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160120125431687-881357645.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="987"/>
 </p>
 <p>
  <img alt="image" border="0" height="408" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160120125433422-1492238172.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="987"/>
 </p>
 <p>
 </p>
 <p>
  <strong>
   g / go
  </strong>
 </p>
 <p>
  <img alt="image" border="0" height="408" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160120125437359-2010010315.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="686"/>
 </p>
 <p>
  <img alt="image" border="0" height="408" src="https://images2015.cnblogs.com/blog/626593/201601/626593-20160120125438093-1008328282.png" style="background-image: none; padding-top: 0; padding-left: 0; margin: 20px 0; display: inline; padding-right: 0; border-width: 0" title="image" width="686"/>
 </p>
 <img alt="" loading="lazy" src="https://img2022.cnblogs.com/blog/626593/202210/626593-20221019124201037-434874129.png"/>
 <p>
 </p>
</div>
