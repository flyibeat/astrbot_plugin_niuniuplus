# 牛牛插件使用说明

## 一、插件简介
安装后自动启用 群内发送 牛牛菜单 查看详情

## 二、功能与玩法

- **指令**：`注册牛牛`
- **玩法说明**：在群聊中发送“注册牛牛”指令，系统会为你的牛牛随机分配一个初始长度，长度范围在 1 - 10cm 之间（可在配置文件中调整）。

- **指令**：`打胶`
- **玩法说明**：打胶是改变牛牛长度的重要操作。不过打胶有冷却时间限制：
    - **10 分钟内**：不允许打胶，若尝试会收到类似“[用户昵称]，你的牛牛还在疲惫状态呢，至少再歇 10 分钟呀！”的提示。
    - **10 - 30 分钟**：越接近 10 分钟，打胶失败（牛牛长度缩短）的概率越高。打胶结果可能是增长、缩短或无变化。
    - **30 分钟后**：正常判定打胶结果，牛牛长度可能增加、减少或保持不变。
    - 
- **指令**：`我的牛牛`
- **玩法说明**：发送该指令可查看你当前牛牛的长度，并获得相应评价。

- **指令**：`比划比划 @目标用户` 或 `比划比划 目标用户名关键词`
- **玩法说明**：
    - 可以 @ 一名已注册牛牛的用户，或者输入用户名关键词进行牛牛长度的较量。
    - **邀请限制**：10 分钟内主动邀请超过 3 人比划，会收到提示让牛牛休息。对同一用户 10 分钟内只能发起一次比划。
    - **结果判定**：
        - **两败俱伤（5% 概率）**：双方牛牛长度都减半。例如“[用户昵称] 和 [目标用户昵称]，发生了意外！双方的牛牛都折断了，长度都减半啦！”
        - ~~**长度相近（差距 ≤ 10）**：有 30% 概率发起者凭借硬度取胜，长度增加；否则提示双方长度差距不大。~~ 目前废弃了这个设定 全部改为概率胜利由长度以及硬度（隐藏）决定
        - ~~**一方长度占优**：长度较长者获胜，获胜方长度可能增加（增加范围可在配置文件中调整）。~~ 挑战设定 胜率动态设定由长度以及硬度（隐藏）决定 短牛牛挑战成长牛牛时有额外奖励

- **指令**：`牛牛排行`
- **玩法说明**：发送该指令可查看当前群内牛牛长度的排行榜，展示排名、用户昵称和牛牛长度。

## 三、修复

- 2.0
- 支持模糊比划,比划时模糊匹配
- 2.1
- 修复2.0由于if缩进问题导致的插件崩溃
- 2.2
- 修复2.0版本后 比划比划 模糊搜索可以填自己名字的情况
- 添加事件监听器，应对AstrBot v3.4.24 版本后 指令需要唤醒词的问题
- 3.0
- 增加插件开关 通过 `牛牛开 / 关` 可开启/关闭插件（但没设置权限所有人皆可开关）
- 更新隐藏数值硬度，不显示在游戏内，但会影响比划时的胜率
- 增加挑战设定
- 修改部分数值
- 更改yml位置，防止再次出现更新时数据丢失的情况
- 提取代码内文本内容结构调整等
- 3.1
- 修复 当用户在多个群时 `打胶/比划` 冷却时间共享的遗留问题
- 修复比划时主人公显示错误的问题
- 修复比划时长度未正常变化的问题
- 3.2修复 补充yml文件，新增特殊事件
- 3.3修复 遍历词典时数据错误的问题（可能还会有其他地方出现相同问题 有bug提交issues（**建议**）或加群@长安某）
- 修复yml中部分文本无法被正确触发的问题
- 调整胜率判断 现在除特殊事件外 胜率为      **50%（基础） +  （-30% ~ 30%）[长度影响]+ （-20% ~ 20%）[硬度影响]** 最终胜率在 20% -80% 之间
- 修复比划时出现占位符的问题（可能会有其他地方出错）
- 修复 `我的牛牛` yml文件与py中不一致导致的报错
- 3.4修改
- 新增30分钟后（正常）打胶失败的文本,以免正常打胶失败依旧触发为 过度 的问题
- 给开关指令加了权限（管理员同机器人管理员），群默认为关（我实在受不了二群想测一下bug四五个机器人识别命令了）
- 把特殊事件触发概率减半
- 修复冷却功能没正确用的问题,感谢@•ᴗ•
- 真的修复比划上限导致冷却无法重置的问题，主角优势时进行判定，不再显示差距极大
## 四、更新计划
- 1.0 这是~~基础功能：注册、打胶、比划、查看、排行榜~~
- 2.0 ~~完善文档描述，修改游戏中文案等~~
- 3.0 ~~对硬度设定进行完善，使硬度能干预部分胜率~~
- 4.0 ~~对打胶、比划，成功率或胜率进行调整使牛牛成长曲线呈略微上涨~~可能后续还需调整
- 5.0 ~~比划中增加**挑战**判定~~
- 6.0 观望
