# Switch
基于hoshino的全局开关(伪)，不重启就一直生效

## 原理
获得指令后主动拉黑该群聊，以达到“关闭”hoshinobot服务的功能，**实际上并没有关，只是不响应了而已**。

## 部署
1. 下载源码
2. 将`switch.py`以及两张图片放入`botmanage`文件夹中
3. 在hoshino/priv.py 里添加以下代码：
```
def remove_block_group(group_id):
    if group_id in _black_group:
        del _black_group[group_id]  #在黑名单中移除群
        return False
    return bool(group_id in _black_group)
```    
4. 重启hoshino

## 使用
@Bot或点名Bot+休息+休息的时间（分钟，分，小时，天）<br>
**例：**<br>
`派蒙休息` 　　 Bot会默认拉黑本群8小时<br>
`派蒙休息5分钟`  Bot会拉黑本群5分钟<br>
`派蒙休息1小时`  Bot会拉黑本群1小时<br>
`派蒙起床`  　　Bot会提前解除拉黑，恢复在本群的响应<br>
## 自定义
可手动更换`on.png`与`switch.png`

***更多操作见代码***

----[项目原地址](https://github.com/Jacosnow/switch)
