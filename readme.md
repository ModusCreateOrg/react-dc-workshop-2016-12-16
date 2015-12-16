#About
This project is designed to be used by the React DC hack night: http://www.meetup.com/React-DC/events/227361632/

The following steps are designed to get the project rolling.

##Preparing the project
### Configure React Native on your Mac
https://facebook.github.io/react-native/docs/getting-started.html

### Initiate the project
Clone this project:
```
git clone git@github.com:ModusCreateOrg/react-dc-workshop-2016-12-16.git
```

### Install modules
In terminal: 

```
cd react-dc-workshop-2016-12-16/
npm install
```

### Patch react-native-youtube

react-native-youtube is not currently compatible with v0.16.0 of React native, so we need to patch it. Don't worry, it's not that hard!

Open `node_modules/react-native-youtube/RCTYouTubeManager.m` in your favorite editor.

Find 

```
#import "RCTSparseArray.h"
```

replace with
```
#import "UIView+React.h"
```

Find
```
     [self.bridge.uiManager addUIBlock:
      ^(__unused RCTUIManager *uiManager, RCTSparseArray *viewRegistry){
```

replace with
```
    [self.bridge.uiManager addUIBlock:^(__unused RCTUIManager *uiManager, NSDictionary<NSNumber *, UIView *> *viewRegistry) {
```



