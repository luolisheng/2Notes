---
title: PlistBuddy && sed
tags: iOS
notebook: iOS 
---

#### 参考

```bash
    sed -i ‘’ ‘s/ProvisioningStyle = Automatic;/ProvisioningStyle = Manual;/’ MyProj.xcodeproj/project.pbxproj
    sed -i ‘’ “s/DevelopmentTeam = ${DevelopmentTeamID};/DevelopmentTeam = \”\”;/” MyProj.xcodeproj/project.pbxproj
    sed -i ‘’ “s/DEVELOPMENT_TEAM = ${DevelopmentTeamID};/DEVELOPMENT_TEAM = \”${TEAM_ID}\”;/” MyProj.xcodeproj/project.pbxproj
```

```bash
    build=$(($build + 1))
    /usr/libexec/PlistBuddy -c "Set :CFBundleVersion $build" "$PRODUCT_SETTINGS_PATH"

    subversion=$build
    version=`echo $version | awk -F "." '{print $1 "." $2 ".'$subversion'" }'`
    /usr/libexec/PlistBuddy -c "Set :CFBundleShortVersionString $version" "$PRODUCT_SETTINGS_PATH"
```

1. [sed](https://www.cnblogs.com/wangqiguo/p/6718512.html)
2. [PlistBuddy](https://www.jianshu.com/p/535293a8492e)
