# README #

Simple popover view to show any kind of content which is subclass of UIView

## How do I get set up? ##

* Just import NGSPopoverView .h and .m files

## Samples ##


### Rounded corners ###
![rounded_corner.png](https://bitbucket.org/repo/8yGqo8/images/3035014097-rounded_corner.png)

```
#!objective-c

- (IBAction)buttonPressed:(UIButton *)sender {
    UILabel *label = [[UILabel alloc] init];
    label.text = @"Some text\nAnd some more";
    label.numberOfLines = 0;
    
    NGSPopoverView *popover = [[NGSPopoverView alloc] initWithCornerRadius:10.f
                                                                 direction:NGSPopoverArrowPositionAnywhere
                                                                 arrowSize:CGSizeMake(20, 10)];
    popover.contentView = label;
    
    [popover showFromView:sender animated:YES];
}
```

### Fill screen ###
![fill_screen.png](https://bitbucket.org/repo/8yGqo8/images/3076218040-fill_screen.png)
```
#!objective-c

- (IBAction)buttonPressed:(UIButton *)sender {
    UILabel *label = [[UILabel alloc] init];
    label.text = @"Some text\nAnd some more";
    label.numberOfLines = 0;
    
    NGSPopoverView *popover = [[NGSPopoverView alloc] initWithCornerRadius:0.f
                                                                 direction:NGSPopoverArrowPositionAnywhere
                                                                 arrowSize:CGSizeMake(20, 10)];
    popover.contentView = label;
    popover.fillScreen = YES;
    
    [popover showFromView:sender animated:YES];
}
```
### Mask source view with transparency ###
![mask_view.png](https://bitbucket.org/repo/8yGqo8/images/3619268285-mask_view.png)
```
#!objective-c

- (IBAction)buttonPressed:(UIButton *)sender {
    UILabel *label = [[UILabel alloc] init];
    label.text = @"Some text\nAnd some more";
    label.numberOfLines = 0;
    
    NGSPopoverView *popover = [[NGSPopoverView alloc] initWithCornerRadius:10.f
                                                                 direction:NGSPopoverArrowPositionAnywhere
                                                                 arrowSize:CGSizeMake(20, 10)];
    popover.contentView = label;
    popover.shouldMaskSourceViewToVisible = YES;
    popover.maskedSourceViewCornerRadius = sender.frame.size.width/2.f;
    
    [popover showFromView:sender animated:YES];
}
```