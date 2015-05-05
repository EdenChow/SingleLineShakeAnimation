# SingleLineShakeAnimation
TLDR; Shake a view with a single line of code with a non-intrusive extension for UIView, with good support for accessability, written in Swift.

With this non-intrusive UIView extension, your UIView subclasses can get shaking with very little code. 
Shaking can be useful to indicate an important action your user needs to perform, for example filling out a form before submitting. Show the user it by gently shaking the needed view to get their attention.


[![Version](https://img.shields.io/cocoapods/v/SingleLineShakeAnimation.svg?style=flat)](http://cocoadocs.org/docsets/SingleLineShakeAnimation)
[![License](https://img.shields.io/cocoapods/l/SingleLineShakeAnimation.svg?style=flat)](http://cocoadocs.org/docsets/SingleLineShakeAnimation)
[![Carthage compatible](https://img.shields.io/badge/Carthage-compatible-4BC51D.svg?style=flat)](https://github.com/haaakon/SingleLineShakeAnimation)

## Installation
```ruby
pod "SingleLineShakeAnimation"
```

Usage
=====
#### import library 
```swift
import SingleLineShakeAnimation
```

##### Basic horizontal shake
```swift
button.shake(.Horizontal)
```
##### Basic vertical shake
```swift
button.shake(.Vertical)
```
Using the default values, 5 times back and forth, animating for 0.5 seconds.


##### Basic vertical shake with accessability
```swift
usernameTextField.shake(.Vertical)?.postAccessabilityNotification(text:"You need to write a username before tapping login button")
```
Checks if VoiceOver is activated, if it is, it reads the text instead of shaking.

### Example
![Resize Example](https://raw.githubusercontent.com/haaakon/SingleLineShakeAnimation/master/example.gif)


Customized usage
=====
Vertical shake with completion block.
```swift
button.shake(.Vertical, completion: { 
            // do something after animation finishes
        })
```

Stating number of times to go back and forth and total duration for the whole animation to take.
```swift
button.shake(.Horizontal, numberOfTimes: 10, totalDuration: 0.6, completion: {
            // do something after animation finishes
        })
```

## TODO
- Easing on animation

## Author

Håkon Bogen, hakon.bogen@gmail.com

## License

SingleLineShakeAnimation is available under the MIT license. See the LICENSE file for more info.

## Single Line APIs
Really good APIs should not need more than a single line of code to work and be as non intrusive as possible. This library is a part of my ongoing effort to build single line libraries for iOS. Check out the other ones on the list as well.
- [SingleLineShakeAnimation](https://github.com/haaakon/SingleLineShakeAnimation)
- [SingleLineKeyboardResize](https://github.com/haaakon/SingleLineKeyboardResize)
