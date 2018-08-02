---
published: true
layout: default
date: '2018-08-01 16:25:00 +0200'
categories: personal
---
# [My impressions using fastlane.swift]({{ site.url }}{% link _posts/2018-08-01-my-impressions-using-fastlane.swift.markdown %})

#### Written on {{ page.date | date: '%B %d, %Y' }} 

One of my tasks during my first weeks at [Wisk](https://www.wisksolutions.com) has been to be able to generate builds of our iOS app automatically, a first step for a future continuous integration scheme.

I used fastlane in the past so it was clear to me that it'll be my first option. But what I didn't know if that fastlane has now a beta project called [fastlane.swift](https://docs.fastlane.tools/getting-started/ios/fastlane-swift/). 
<!--more-->
Fastlane.swift is a wrapper over fastlane to allow developers write their fastlane configuration using Swift instead of Ruby scripts.

For me that was just perfect. The company uses Swift not only for their iOS app but also for the back-end services, so being able to configure fastlane using the same language would be a total win. The documentation on the fastlane page is not so extense regarding the Swift wrapper, but there are two things to have in mind: it's just a wrapper, so things are going to work the same way as with the Ruby scripts and names of the functions and parameters will be equivalent; and as you will be editing a Swift project with XCode, you'll have autocompletion to guide you.

## Getting started

First thing you will need is to install fastlane on your mac

```script
[sudo] gem install fastlane
```

Now, from your project's directory, run the following

```script
fastlane init swift
```

This will configure everything and at the end of the process you will be pointed to the location of a `FastlaneRunner.xcodeproj`, the new project where you will be able to configure your lanes in a `Fastlane.swift` file.

To use your lanes, you'll do it exactly the same way you'd do it without the Swift wrapper

```script
fastlane yourlane
```

## Configuring your lanes

Generating a build and uploading it to Testflight looks as simpler as this

![basiclane.png]({{site.url}}/assets/2018-08-01/basic_lane.png)

In our case, we are using [match](https://docs.fastlane.tools/actions/match/) to sign our app, but you can use your preferred way to do it.

Most of the methods of fastlane.swift have loads of optional parameters to represent the configuration arguments of each command. You can use autocompletion to take a look at them, altough there's no appledoc documentation so you still need to check with the fastlane docs if you don't know the meaning or usage of any of them.

If you want to accept command-line arguments, you can do it by receving a dictionary in your lane method like this

![lanewithoptions.png]({{site.url}}/assets/2018-08-01/lane_with_options.png)

## Conclusion

For me it's been easy to get everything working with fastlane Swift and of course everything is quite natural writing the configuration with the same language you are using to develop the app. However, I'm not sure if I would suggest to use the Swift version in complex projects, as there are much more documentation and developer Q&A for the standard version right now, so it's easier to get stuck if you find something problematic with the Swift wrapper. Also, in some companies where this type of automation work is done by DevOps people, they may prefer using a script language instead of Swift.

Anyway, it's great to be able to use a language like Swift also for this type of tasks and I think it's worth it to give it a try if you are developing a Swift app for iOS.
