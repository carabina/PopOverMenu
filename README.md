### PopOverMenu ![CocoaPods Version](https://img.shields.io/cocoapods/v/PageSheetForm.svg?style=flat) ![Platform](https://img.shields.io/cocoapods/p/PageSheetForm.svg?style=flat) ![License](https://img.shields.io/cocoapods/l/PageSheetForm.svg?style=flat)

PopOverMenu is a PopOver style menu.

### Image
#### iPhone
<img src="https://user-images.githubusercontent.com/43707/29021212-b8b8290c-7b9f-11e7-8c9d-8446327a324d.png" width="400px">

### Examples

#### Swift

```html
    public func openMenu(sender:UIBarButtonItem) {
        let titles:NSArray = ["Menu1", "Menu2", "Menu3"]
        let descriptions:NSArray = ["description1", "", "description3"]
        
        let popOverViewController = PopOverViewController.instantiate()
        popOverViewController.setTitles(titles: titles)
        popOverViewController.setDescriptions(descriptions: descriptions)
        popOverViewController.popoverPresentationController?.barButtonItem = sender
        popOverViewController.preferredContentSize = CGSize(width: 300, height:135)
        popOverViewController.presentationController?.delegate = self
        popOverViewController.completionHandler = { selectRow in
            switch (selectRow) {
            case 0:
                break
            case 1:
                break
            case 2:
                break
            default:
                break
            }
            
        };
        present(popOverViewController, animated: true, completion: nil)
    }
    
    func adaptivePresentationStyle(for controller: UIPresentationController) -> UIModalPresentationStyle {
        return UIModalPresentationStyle.none
    }
```

#### ObjectiveC

```
@import PopOverMenu;

-(IBAction)openMenu:(id)sender {
    
    NSArray *titles = @[@"Menu1", @"Menu2", @"Menu3"];
    NSArray *descriptions = @[@"description1", @"", @"description3"];
    
    PopOverViewController *popOverViewController = [PopOverViewController instantiate];
    
    [popOverViewController setTitlesWithTitles:titles];
    [popOverViewController setDescriptionsWithDescriptions:descriptions];
    
    popOverViewController.popoverPresentationController.barButtonItem = sender;
    popOverViewController.preferredContentSize = CGSizeMake(300, 135);
    popOverViewController.presentationController.delegate = self;
    
    [popOverViewController setCompletionHandler:^(NSInteger selectRow) {
        switch (selectRow) {
            case 0:
                break;
            case 1:
                break;
            case 2:
                break;
            default:
                break;
        }
    }];
    
    [self presentViewController:popOverViewController animated:YES completion:nil];
}

- (UIModalPresentationStyle)adaptivePresentationStyleForPresentationController:(UIPresentationController *)controller {
    return UIModalPresentationNone;
}

```

### Installation (CocoaPods)
`pod PopOverMenu`

or 

`pod 'PopOverMenu', :git => 'https://github.com/tichise/PopOverMenu.git'`

