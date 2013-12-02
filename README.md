Use an instance of AGMovingNode as a background layer node. All children of AGMovingNode will be moving left.

Example of using:

```Objective-C
@interface GameScene()

@property AGMovingNode *backgroundLayer;

@end

@implementation GameScene

- (void)loadNodes {
    self.backgroundLayer = [[AGMovingNode alloc] initWithPointsPerSecondSpeed:100.0];
    self.backgroundLayer.name = @"background";
    [backgroundLayer addChild:/* Add your background textures here... */ ];
    [self addChild:self.backgroundLayer];
}

-(void)update:(CFTimeInterval)currentTime {
    // Need to update AGMovingNode every frame
    [self.backgroundLayer update:currentTime paused:self.paused];
}

@end
```
