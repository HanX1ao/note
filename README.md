# note
踩坑记录
- FlexLayout 与 Snapkit
  
  子视图使用 FlexLayout，父视图使用 Snapkit，注意子视图中需要实现
  
  ```swift
    override var intrinsicContentSize: CGSize {
        frame = CGRect(x: 0, y: 0, width: CGFloat.greatestFiniteMagnitude, height: 14)
        flex.layout(mode: .adjustWidth)
        return bounds.size
    }
  ```
  
 子视图 configure 中调用 
  
  ```swift
     invalidateIntrinsicContentSize()
  ```
