# get_and_deal_good
第一步：获取商品的信息
第二步：然后解析存进数据库
第三步：并下载相应的图片 如果有必要可以压缩图片 
第四步：生成对应的excel

第一步:
      访问商品的主url以及输入对应的层数（这边用的是mechanize 或者selenium也可以）
      是商品页就保存源码
      将进度条和点过的url存进数据库
      
第二步：
      将保存的源码进行解析成需要的字段存进数据库
      
第三步：
      下载图片（访问图片的地址 将图片保存成jpg 或者 png格式 ）
      page = agent.get img_url
      page.body --就是图片的内容 直接存就ok
      
      压缩图片的话可以采用 
      require "mini_magick" 
      image = MiniMagick::Image.open("图片的路径")
      image.resize "100x100"
      image.write "名字.png"
      
第四步:
      生成excel
      require 'axlsx'可以使用这个库 
      这个不仅能够插入文字 还可以插入缩略图
      具体操作可以参考这个文档
      https://github.com/randym/axlsx/blob/master/examples/example.rb
      https://gist.github.com/randym/2371912
      
      
