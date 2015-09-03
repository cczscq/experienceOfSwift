# storyboard创建多个ViewController

在创建iOS项目时会自动给开发者创建一个默认的ViewController。之前一直都是在玩Single View Application,

今天搞定了多ViewController。

1. 拖动ViewController到storyboard中
2. 编辑storyboard中新ViewController的UI元素
3. 创建NewViewController.swift文件
4. storyboard中新ViewController的Custom class 指定NewViewController实现绑定



# ViewController关联

此时，ViewController与NewViewController未建立关联，我们可以通过segue把ViewController之间建立联系，实现切换。

1. 把ViewController的Button的action指向NewViewController，创建segue
2. 指定segue的Identifier
3. 在ViewController.swift中重写prepareForSegue方法

``` swift
    override func prepareForSegue(segue: UIStoryboardSegue, sender: AnyObject?) {
        if segue.identifier == "GoToGalley" {
            let index = beautyPick.selectedRowInComponent(0);
            
            var imageName : String?
            switch (index){
            case 0:
                imageName = "gaoyuanyuan"
                break
            case 1:
                imageName = "liushishi"
                break
            case 2:
                imageName = "liuyan"
                break
            case 3:
                imageName = "tangyan"
                break
            default:
                imageName = nil
            }
            
            var vc = segue.destinationViewController as! GalleyViewController
            vc.imageNmae = imageName
        }
    }
```

