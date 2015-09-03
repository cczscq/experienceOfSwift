# UIPickView简单实现



## StoryBroad

在storyBroad中的ViewController中创建UIPickView,同时绑定到ViewController中



## 为ViewController创建扩展

新建ViewControllerExtension.swift文件		



## 实现UIPickerViewDelegate

``` swift
extension ViewController : UIPickerViewDelegate {
    
    func pickerView(pickerView: UIPickerView, titleForRow row: Int, forComponent component: Int) -> String! {
        return beautys[row];
    }
}
```

## 

## 实现UIPickerViewDataSource	

``` swift
extension ViewController : UIPickerViewDataSource {

    func numberOfComponentsInPickerView(pickerView: UIPickerView) -> Int {
        return 1;
    }
    
    func pickerView(pickerView: UIPickerView, numberOfRowsInComponent component: Int) -> Int {
        return beautys.count;
    }
}
```



## 绑定数据源以及代理

``` swift
    override func viewDidLoad() {
        super.viewDidLoad()
        beautyPick.dataSource = self;
        beautyPick.delegate = self;
    }
```









## 