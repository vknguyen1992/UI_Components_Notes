# UI Components Notes
Some UI components notes

## UILabel
### Automatically sink font size to a minimum font size
```
titleLabel.lineBreakMode = .byTruncatingTail
titleLabel.adjustsFontSizeToFitWidth = true
titleLabel.minimumScaleFactor = 8/titleLabel.font.pointSize
```

## Adjust view size to wrap around text
```
// setContentHuggingPriority: make view size less than or equal to text size
myLabel.setContentHuggingPriority(UILayoutPriorityRequired, for: UILayoutConstraintAxis.horizontal)
// setContentCompressionResistancePriority: make view size greater than or equal to text size
myLabel.setContentCompressionResistancePriority(UILayoutPriorityRequired, for: UILayoutConstraintAxis.horizontal)
```
