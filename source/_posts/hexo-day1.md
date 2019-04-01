title: hexo-day1  
date: 2019-02-28 09:59:46  
tags:  

---
## 第一篇文章
- 我列个大概
- 你么输安逸


### 号码
内容 | 标题 | 描述
--- | --- | ---
你好 | 角度看 | 的境况的

```swift
func createTagListView() {

      if tagListView == nil {

         tagListView = UIView()
         tagListView.backgroundColor = UIColor.white
         baseView.addSubview(tagListView)

         tagListView.snp.makeConstraints { (make) -> Void in

            make.top.equalTo(menuView.snp.bottom).offset(Constants.HDSpace)
            make.left.equalTo(baseView).offset(0)
            make.width.equalTo(Constants.HDSCREENWITH)
            make.height.equalTo((self.hdHM01Response?.result?.tagList?.count)! / 4 * TagHeight)

         }

      }

      /**
         *  几行4列
         */

      var index = 0
      for i in 0 ..< (self.hdHM01Response?.result?.tagList?.count)! / 4 {

         for j in 0 ..< 4 {

            let model: TagListModel = (self.hdHM01Response?.result?.tagList![index])!

            var btn: UIButton?

            btn = tagListView.viewWithTag(index) as? UIButton

            if btn == nil {

               btn = UIButton()
               btn!.backgroundColor = UIColor.white
               btn!.setTitleColor(Constants.HDMainTextColor, for: UIControl.State.normal)
               btn!.tag = index + 1000;
               btn!.titleLabel?.font = UIFont.systemFont(ofSize: 15)
               btn!.setTitle(model.name, for: UIControl.State())
               btn!.layer.borderWidth = 0.5
               btn!.layer.borderColor = Constants.HDBGViewColor.cgColor
               btn!.addTarget(self, action: #selector(tagBtnOnclick(_:)), for: UIControl.Event.touchUpInside)
               tagListView.addSubview(btn!)

               btn!.snp.makeConstraints( { (make) -> Void in

                  make.width.equalTo(Constants.HDSCREENWITH / 4)
                  make.height.equalTo(TagHeight)
                  make.left.equalTo(CGFloat(j) * Constants.HDSCREENWITH / 4)
                  make.top.equalTo(i * TagHeight)

               })

            }

            index += 1;
         }

      }

   }
   
```