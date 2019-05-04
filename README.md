# ViewControllerLIfeCycle_CreatingStateLab
ViewControllerLIfeCycle_CreatingStateLab

``` objective-c
//
//  AppDelegate.m
//  CreatingStateLab
//
//  Created by Carlos Santiago Cruz on 5/4/19.
//  Copyright © 2019 Carlos Santiago Cruz. All rights reserved.
//

#import "AppDelegate.h"
#import "ViewController.h"

@interface AppDelegate ()
{
    ViewController *viewController;
}
@end

@implementation AppDelegate


- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    NSLog(@"%@", NSStringFromSelector(_cmd));
    self.window = [[UIWindow alloc] initWithFrame:[[UIScreen mainScreen] bounds]];
    viewController = [[ViewController alloc] initWithNibName:@"ViewController" bundle:nil];
    self.window.rootViewController = viewController;
    [self.window makeKeyAndVisible];
    return YES;
}


- (void)applicationWillResignActive:(UIApplication *)application {
    // Sent when the application is about to move from active to inactive state. This can occur for certain types of temporary interruptions (such as an incoming phone call or SMS message) or when the user quits the application and it begins the transition to the background state.
    // Use this method to pause ongoing tasks, disable timers, and invalidate graphics rendering callbacks. Games should use this method to pause the game.
     NSLog(@"%@", NSStringFromSelector(_cmd));
}


- (void)applicationDidEnterBackground:(UIApplication *)application {
    // Use this method to release shared resources, save user data, invalidate timers, and store enough application state information to restore your application to its current state in case it is terminated later.
    // If your application supports background execution, this method is called instead of applicationWillTerminate: when the user quits.
     NSLog(@"%@", NSStringFromSelector(_cmd));
}


- (void)applicationWillEnterForeground:(UIApplication *)application {
    // Called as part of the transition from the background to the active state; here you can undo many of the changes made on entering the background.
     NSLog(@"%@", NSStringFromSelector(_cmd));
}


- (void)applicationDidBecomeActive:(UIApplication *)application {
    // Restart any tasks that were paused (or not yet started) while the application was inactive. If the application was previously in the background, optionally refresh the user interface.
     NSLog(@"%@", NSStringFromSelector(_cmd));
}


- (void)applicationWillTerminate:(UIApplication *)application {
    // Called when the application is about to terminate. Save data if appropriate. See also applicationDidEnterBackground:.
     NSLog(@"%@", NSStringFromSelector(_cmd));
}


@end
```

# Compile and run, then you will get the following output:

``` console
2019-05-04 11:04:58.026352-0500 CreatingStateLab[11129:1710050] application:didFinishLaunchingWithOptions:
2019-05-04 11:04:58.065434-0500 CreatingStateLab[11129:1710050] applicationDidBecomeActive:
```

### Press the buton Home on your iphone, in this case I have an Iphone 7, see what happens on the console. Watch the sequence

``` console
2019-05-04 11:05:19.833951-0500 CreatingStateLab[11129:1710050] applicationWillResignActive:
2019-05-04 11:05:20.446834-0500 CreatingStateLab[11129:1710050] applicationDidEnterBackground:
```

- what you can´t see is a notification about a third state Suspeded. Note that the app is still alive in some sense, and Xcode is still connected to it., even though it is not actually getting any CPU time.

### tap the icon app to restore the application. See what happens now.

``` console 
2019-05-04 11:05:47.815724-0500 CreatingStateLab[11129:1710050] applicationWillEnterForeground:
2019-05-04 11:05:48.061262-0500 CreatingStateLab[11129:1710050] applicationDidBecomeActive:
```

### Now double-tap the home button. In this appears all the apps to scroll them.

``` console
2019-05-04 11:06:21.612345-0500 CreatingStateLab[11129:1710050] applicationWillResignActive:
```

### Press the home buton, it will return to the app

``` console
2019-05-04 11:06:52.799302-0500 CreatingStateLab[11129:1710050] applicationDidBecomeActive:
```

### Press HOme and hold the State Lab Icon until the "kill" icon (the minus in the red circle) comes up.

``` console
2019-05-04 11:07:44.790147-0500 CreatingStateLab[11129:1710050] applicationWillResignActive:
2019-05-04 11:07:45.390779-0500 CreatingStateLab[11129:1710050] applicationDidEnterBackground:

```
### then click to delete the app.
``` console
Message from debugger: Terminated due to signal 9
```

![Captura de Pantalla 2019-05-04 a la(s) 11 22 34](https://user-images.githubusercontent.com/24994818/57181897-90608c00-6e56-11e9-857e-52e6132ed3a0.png)

![Captura de Pantalla 2019-05-04 a la(s) 11 45 39](https://user-images.githubusercontent.com/24994818/57182209-cc492080-6e59-11e9-8154-8a1a415abbbe.png)
