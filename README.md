# UI Components Notes
Some UI components notes

## UIView
### Force view using left to right language
```
[view].semanticContentAttribute = .forceLeftToRight
```

## UILabel
### General
```
label.baselineAdjustment = .none
```

### Automatically sink font size to a minimum font size
```
titleLabel.lineBreakMode = .byTruncatingTail
titleLabel.adjustsFontSizeToFitWidth = true
titleLabel.minimumScaleFactor = minimumFontSize/titleLabel.font.pointSize
titleLabel.numberOfLines = (any value)
```

### Adjust view size to wrap around text
```
// setContentHuggingPriority: make view size less than or equal to text size
myLabel.setContentHuggingPriority(UILayoutPriorityRequired, for: UILayoutConstraintAxis.horizontal)
// setContentCompressionResistancePriority: make view size greater than or equal to text size
myLabel.setContentCompressionResistancePriority(UILayoutPriorityRequired, for: UILayoutConstraintAxis.horizontal)
```

## UIScrollview
### Position in UIViewController
```
[UIViewController].automaticallyAdjustsScrollViewInsets = false
[UIViewController].extendedLayoutIncludesOpaqueBars = true
```
### Layout views in UIScrollView
```
scrollView.addSubview(contentView)
contentView.addSubview(subView1)
contentView.addSubview(subView2)
contentView.addSubview(subView3)

layout contentView to scrollView by top, leading, bottom, trailing
layout subView1: top to contentView; leading, trailing to scrollView
layout subView2: top to subView1.bottom; leading, trailing to scrollView
layout subView3: top to subView2.bottom; bottom to contentView; leading, trailing to scrollView
```
```
o
I: vertial constraint
o
o~o: horizontal constraint
cntView: content view
+-----scrollView--o----+
|                 I    |
| +---o--cntView--o--+ |
| |   I              | |
| | +-o------------+ | |
| | |              | | |
o~~~o   subView1   o~~~o
| | |              | | |
| | +-------o------+ | |
| |         I        | |
o~o         I        o~o
| | +-------o------+ | |
| | |              | | |
o~~~o   subView3   o~~~o
| | |              | | |
| | +-------o------+ | |
| |         I        | |
| +---------o----o---+ |
|                I     |
+----------------o-----+
```

## ViewController
```
func viewDidLayoutSubview() // in UIViewController: called when all current view controller's subviews layouted
func layoutSubView() // in UIView: called when current view layouted
```

## UITabBar
```
pushedViewController.hidesBottomBarWhenPushed = true // hide bottom tab bar when pushing to pushedViewController
```
