# GoAgentXRules
Backup for my GoAgentXRules

GoAgentX的规则存储目录在`/Users/John/Library/Application Support/GoAgentX/Data`，使用SQLite格式。

导出规则后文件名为`GoAgentXRules.gxbundle`，规则文件实际存储在`GoAgentXRules.gxbundle/Contents/Resources/ArchivedRules`中。解压的方法是使用Objective-C的`NSKeyedUnarchiver`，代码如下：

```
NSData *data = [NSData dataWithContentsOfFile:@"/Users/John/Desktop/test/test/ArchivedRules"];
id obj = [NSKeyedUnarchiver unarchiveObjectWithData:data];
```

解压后得到数组，每一项是个字典/map，例如：

```
{
    domain = "*.cn";
    enabled = 1;
    listOrder = 0;
    profileIdentifier = DirectConnection;
}
```
