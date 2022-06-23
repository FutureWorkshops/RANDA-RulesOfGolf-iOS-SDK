# RANDA-RulesOfGolf-iOS-SDK

Rules of Golf SDK allows you to display some elements from the Rules of Golf official app.

##  Import using Cocoapods

For now the only way to integrate the framework is by using [CocoaPods](https://cocoapods.org/).

**You should first be invited to the Private Podspecs repo for the Rules of Golf SDK.**

Then add the repo to your podspecs repositories using the following:

```
pod repo add RANDA-RulesOfGolf-iOS-PodRepo git@github.com:FutureWorkshops/RANDA-RulesOfGolf-iOS-PodRepo.git
```

At the top of your `Podfile` you should have least those source:

```
source 'git@github.com:FutureWorkshops/RANDA-RulesOfGolf-iOS-PodRepo.git'
source 'https://cdn.cocoapods.org/'
```

Then add the following to your `Podfile`:

```
pod 'RANDARulesOfGolf'
```

Then add the following post install script, else the framework won't build. More info [here](https://github.com/CocoaPods/CocoaPods/issues/9232).

```
post_install do | installer |
    installer.pods_project.build_configurations.each do |config|
        config.build_settings['BUILD_LIBRARY_FOR_DISTRIBUTION'] = 'YES'
    end
end
```

And finally run the following command:

```
pod install
```


# Using the Rules of Golf framework

## Showing the Rules of Golf using Swift

Add the following at the top of your UIViewController file.

```
import RANDARulesOfGolf
```

Present the view controller using the following:

```
let rogBrowserNavigationController = ROGBrowserNavigationController()  
self.present(rogBrowserNavigationController, animated: true)
```

## Showing the Rules of Golf using Objective-C

Add the following at the top of your UIViewController file.

```
#import “RANDARulesOfGolf/RANDARulesOfGolf.h”
```

Present the view controller using the following:

```
ROGBrowserNavigationController *rogBrowserNavigationController = [[ROGBrowserNavigationController alloc] init];  
[self presentViewController:rogBrowserNavigationController animated:YES completion:nil];
```
