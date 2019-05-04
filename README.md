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
2019-05-04 10:46:18.564743-0500 CreatingStateLab[11053:1702596] application:didFinishLaunchingWithOptions:
2019-05-04 10:46:18.596204-0500 CreatingStateLab[11053:1702596] applicationDidBecomeActive:
```

### Press the buton Home on your iphone, in this case I have an Iphone 7, see what happens on the console. Watch the sequence

``` console
2019-05-04 10:46:18.564743-0500 CreatingStateLab[11053:1702596] application:didFinishLaunchingWithOptions:
2019-05-04 10:46:18.596204-0500 CreatingStateLab[11053:1702596] applicationDidBecomeActive:
2019-05-04 10:46:42.555854-0500 CreatingStateLab[11053:1702596] applicationWillResignActive:
2019-05-04 10:46:43.162695-0500 CreatingStateLab[11053:1702596] applicationDidEnterBackground:
```

### tap the icon app

``` console 
2019-05-04 10:46:18.564743-0500 CreatingStateLab[11053:1702596] application:didFinishLaunchingWithOptions:
2019-05-04 10:46:18.596204-0500 CreatingStateLab[11053:1702596] applicationDidBecomeActive:
2019-05-04 10:46:42.555854-0500 CreatingStateLab[11053:1702596] applicationWillResignActive:
2019-05-04 10:46:43.162695-0500 CreatingStateLab[11053:1702596] applicationDidEnterBackground:
2019-05-04 10:48:49.480696-0500 CreatingStateLab[11053:1702596] applicationWillEnterForeground:
2019-05-04 10:48:49.747136-0500 CreatingStateLab[11053:1702596] applicationDidBecomeActive:
```

# Now double-tap the home button.

``` console
2019-05-04 10:46:18.564743-0500 CreatingStateLab[11053:1702596] application:didFinishLaunchingWithOptions:
2019-05-04 10:46:18.596204-0500 CreatingStateLab[11053:1702596] applicationDidBecomeActive:
2019-05-04 10:46:42.555854-0500 CreatingStateLab[11053:1702596] applicationWillResignActive:
2019-05-04 10:46:43.162695-0500 CreatingStateLab[11053:1702596] applicationDidEnterBackground:
2019-05-04 10:48:49.480696-0500 CreatingStateLab[11053:1702596] applicationWillEnterForeground:
2019-05-04 10:48:49.747136-0500 CreatingStateLab[11053:1702596] applicationDidBecomeActive:
2019-05-04 10:50:26.559311-0500 CreatingStateLab[11053:1702596] applicationWillResignActive:
```




