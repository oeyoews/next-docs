---
title: 参数化嵌入与范本
---

# Transclusion with Templates

## 示例

### 一个预先定义好的范本，可漂亮地呈现标签

您可以套用系统范本 ``$:/core/ui/TagTemplate`` 到一个标签，即可看到一个有下拉选菜单的标签丸：

```
{{Transclusion in WikiText||$:/core/ui/TagTemplate}}
```

显示为 {{Transclusion in WikiText||$:/core/ui/TagTemplate}}

## 用法

经由范本嵌入就像套用遮罩：假设来源条目包含通用的参照（如遮罩中的眼孔），这些将被替换为目标条目内容（像是戴面罩的人的眼睛）。

范本可以套用于任何条目，不一定是当前条目。完整标记语法为 `{{<目标>||<范本>}}`。缺省的 <目标> 是当前条目 （我们使用于上面的示例中）。

## TemplateTiddlers范本条目

范本条目实际上并非一个条目类型，它是一个可用于条目的角色。

范本是一种重复使用 WikiText 区块的方法。

借由嵌入范本结合两个条目扩充嵌入的基本功能：

* 包含要显示 WikiText 的范本条目。它可以包含嵌入的引用字段于当前条目
* 当解析参考的字段时，目标条目即标识为当前条目

范本化的最佳示例是 TiddlyWiki 的主要故事河。每个开启中的条目呈现，通过 ViewTemplate 指定如何呈现每个字段。