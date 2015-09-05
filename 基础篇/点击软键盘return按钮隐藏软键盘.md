# 软件盘返回按钮隐藏键盘

在应用开发中，用户输入操作后，隐藏软键盘一种方式是直接点击软键盘的返回(return)按钮，这里主要介绍如何支持点击返回按钮，隐藏软键盘

## 文本输入框

``` swift
@IBOutlet weak var name: UITextField!
```



## UITextFieldDelegate

我们来一个看看UITextFieldDelegate的源码。

我们可以看到UITextFieldDelegate的源码中存在textFieldShouldReturn这个方法，当点击return调用该方法，我们可以override这个方法，做一些需要的操作；

``` swift
class ViewController: UIViewController, UITextFieldDelegate {
	@IBOutlet weak var name: UITextField!
        
    override func viewDidLoad() {
        super.viewDidLoad()
        name.delegate = self
    }
    
   func textFieldShouldReturn(textField: UITextField) -> Bool {
        textField.resignFirstResponder()
        println("textFieldShouldReturn");
        return true
    }
}
```



















