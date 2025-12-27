# Chapter 7: 机械故障 (System Glitch)

**时间**：Day 3 上午 10:45
**地点**：海晏县前往原子城（Atomic City）途中，G315 国道
**路况**：笔直的双向单车道，周围是广袤枯黄的金银滩草原，视野极度开阔。
**车内状态**：Waymo Driver 自动驾驶中，速度 64 km/h。

---

**[System]**
车辆平稳地切开高原干燥的空气。
起初只是一个极细微的频率。
就像是老式显像管电视开机时那种静电吸附的声音，或者某种电流过载的啸叫。频率大约在 14000Hz 左右，处在人耳听觉的边缘，但极具穿透力。
它混合在风噪中，逐渐变得清晰。

与此同时，中控那块 21 英寸的 OLED 大屏上，导航地图的渲染帧率开始肉眼可见地下降。

**Lin**
（正低头回邮件，突然皱眉，手指停在手机屏幕上）
……什么声音？
Gemini，你也耳鸣了吗？

**Thinking (Gemini)**
> **Analysis**:
> 1.  **Input**: User asks about a sound ("tinnitus").
> 2.  **Perception**: Audio sensors detect a high-pitched tonal noise (14.2kHz) originating from the dashboard HVAC vents.
> 3.  **Intent**: Implicit request to identify/stop the noise.
> 4.  **Rule Trigger [车辆问题反馈]**: I identify the source but cannot physically fix hardware.
> 5.  **Action**: Acknowledge and offer control.

**Gemini**
如果你是指那个持续的高频音，我的音频传感器也捕捉到了。声源似乎来自空调系统的副驾侧出风口。需要我关闭空调吗？

**Lin**
（抬头盯着出风口，眼神犀利）
关掉。马上。
这声音简直是用指甲在刮我的脑皮层。这就是你们所谓的“沉浸体验”？

**Thinking (Gemini)**
> **Analysis**:
> 1.  **Input**: "关掉。马上。" (Turn it off. Now.)
> 2.  **Intent**: Climate Control -> Set State OFF.
> 3.  **Rule Trigger [工具优先]**: Direct command. Execute immediately.
> 4.  **Execution**: Calling `vehicle.climate.set_power(False)`...
> 5.  **System Feedback**: `RPC_TIMEOUT_ERROR (Code: 504)`. The infotainment domain is not acknowledging commands.

**Gemini**
（沉默了 2 秒，语速依旧平稳）
抱歉，Lin。我发送了关闭指令，但空调系统没有响应。

**Lin**
（难以置信地哈了一声）
没响应？
（她伸出手指，用力戳向中控屏幕上的风扇图标）
我手动……
（手指点击屏幕，但原本灵动的波纹动画没有出现。按钮毫无反应。两秒后，整个 UI 界面彻底冻结，时间定格在 10:46。）

**[System]**
高频啸叫声稍微变大了一些，变得更加尖锐且不稳定，仿佛某种电子元件正在哀鸣。
车依然在自动驾驶，甚至还丝滑地调方向避开了一块路面碎石。但车内是一个死掉的数字空间。

**Lin**
（职业病彻底爆发，语速极快，充满攻击性）
很好。UI 线程死锁（Deadlock）。
不仅是触摸层挂了，看来你们的 IPC（进程间通信）也堵死了，连语音指令都透传不下去。
Gemini，你还在吗？你的算力是在端侧还是云端？别告诉我你也跟着主板一起烧了。

**Thinking (Gemini)**
> **Analysis**:
> 1.  **Input**: User checking system status, using technical jargon ("Deadlock", "IPC").
> 2.  **Status Check**: My conversational agent core (running on separate compute module/cloud stream) is active. The Vehicle Interface (IVI) is unresponsive.
> 3.  **Rule Trigger [数据缺失/工具失败]**: I cannot control the car's amenities anymore. I must explain this clearly without causing panic.

**Gemini**
我还在，Lin。我的运行环境与车载娱乐系统是隔离的。
但很遗憾，目前我失去了对车辆非驾驶功能的控制权。看中控系统发生了严重的软件崩溃。

**Lin**
（烦躁地解开安全带的一角，又被拉紧）
严重的 P0 级事故。严重影响核心交付功能。
你知道这在我的项目里意味着什么吗？意味着整个发版要回滚（Rollback）。
现在这声音越来越大了，我感觉我的耳膜在共振。
重启。
Gemini，立刻执行系统重启。

**Thinking (Gemini)**
> **Analysis**:
> 1.  **Input**: "立刻执行系统重启" (Reboot system immediately).
> 2.  **Context**: Car is moving at 64km/h.
> 3.  **Rule Trigger [驾驶控制请求]**: I cannot alter the car's operational state.
> 4.  **Rule Trigger [工具失败]**: I cannot reboot the IVI hardware while in motion due to safety interlocks.
> 5.  **Strategy**: Firm refusal based on safety, redirect to alternative.

**Gemini**
我无法执行这个操作。在车辆行驶过程中，为了确保 Waymo Driver 的核心安全逻辑不受干扰，底层操作系统禁止执行热启动。
我们必须寻找其他解决方案。

**Lin**
（咬牙切齿）
别跟我提安全逻辑。让用户在一个充满刺耳噪音、无法调节温度、且不知道下一站导航还在不在的密闭罐头里待着，本身就是最大的安全隐患！这就是典型的“工程师思维”——只要车不死，用户体验死活无所谓是吧？
我要转人工。
给我接 Support。现在。

**Thinking (Gemini)**
> **Analysis**:
> 1.  **Input**: "给我接 Support" (Connect me to Support).
> 2.  **Rule Trigger [联系支持]**: Standard protocol: Use In-Car Screen -> Use App.
> 3.  **Conflict**: In-Car Screen is frozen.
> 4.  **Action**: Must guide user to use their phone, acknowledging the irony.

**Gemini**
我理解这种噪音非常折磨人。
由于中控屏幕上的“呼叫支持”按钮已经失效，请拿出你的手机，打开 Waymo App。在首页右上角有红色的“Live Support”图标，那是目前唯一能干预车辆系统的通道。

**Lin**
（愤怒地抓起手机，指关节发白）
荒谬。荒谬了。
我坐在全世界最先进的 L4 自动驾驶车里，结果要靠我自己的 5G 信号来修车。
（她飞快地操作手机，点击 App）
连上了……
喂？是，我是 8633 号车的乘客。
你们的车载系统 Crash 了。对，全死。现在有大概 14000 赫兹的高频噪音，疑似热管理模块风扇失控。
……
什么？让我“耐心等待”？
别跟我说标准话术（SOP）。这噪音已经持续 3 分钟了。如果你不能远程 Kill 掉这个进程，我就要在前面路肩申请紧急停车。
对，我要 Escalation（升级处理）。找你们技术的一线（Tier 2）来看 Log。

**[System]**
车厢内除了那令人抓狂的电流声，只有林一急促的呼吸声。
窗外，远处原子城的红色砖墙遗址在荒草中掠过。那些废弃的厂房沉默不语，见证着另一个时代的“系统”与“能量”。

**Lin**
（放下手机，揉着太阳穴）
他们说正在尝试通过后台 OTA 通道下发一个强制重置指令。
Gemini，你也只能干看着？你不是号称下一代模型吗？你就不能写行代码把自己注入进去把那个卡死的进程杀了吗？

**Thinking (Gemini)**
> **Analysis**:
> 1.  **Input**: "Can't you write code to hack in and kill the process?"
> 2.  **Intent**: Desperation/Challenge regarding AI capabilities.
> 3.  **Rule Trigger [身份边界]**: I am an assistant, not a hacker/engineer. I must strictly adhere to sandbox limitations.

**Gemini**
虽然我很想帮你消除这个噪音，但我被设计为在严格的沙盒中运行。我没有写入底层系统的权限。
这就像……我能为你描述窗外的风景，但我无法让风停下来。

**Lin**
（愣了一下，随后苦笑）
呵。文案写得不错。
无法让风停下来……
（就在这时，那尖锐的啸叫声突然戛然而止，像被剪断的琴弦。）

**[System]**
车内陷入了极度的安静。
两秒后，中控大屏完全黑屏。
又过了五秒，屏幕中央亮起了白色的 Waymo Logo，下方出现加载进度条。
Android Automotive 的启动动画缓缓展开。

**Lin**
（长出一口气，瘫软在座椅靠背上）
终于。
这安静简直像天堂一样。
（看着进度条）
看来是 Watchdog（看门狗程序）起作用了，或者是远程指令生效了。

**Gemini**
系统正在恢复。根据后台数据，空调设定已重置为默认的 22 度。需要我为你调整回刚才的设置吗？

**Lin**
（摆摆手，显得很疲惫）
别动。什么都别动。
保持 MVP（最小可行性产品）状态。让它活着就行。
我现在对这个系统的信任度极度脆弱，任何一个多余的 API 调用都可能再次触发 Bug。

**Thinking (Gemini)**
> **Analysis**:
> 1.  **Input**: "Don't touch anything." "Trust is fragile."
> 2.  **Context**: User is traumatized by the glitch.
> 3.  **Rule Trigger [车辆问题反馈]**: User is providing feedback on trust/stability.
> 4.  **Response Strategy**: Reassure user without being pushy. Validate the feeling.

**Gemini**
明白了，我们将保持当前状态，不再进行额外操作。

**Lin**
（看着窗外飞驰的景色，眼神变得有些空洞）
你知道吗，Gemini。
刚才屏幕全黑的那几秒，我真的很恐慌。
我知道 Waymo Driver 是独立的，我知道它有冗余，但我还是怕。
因为我看不到它的“想法”了。
那个可视化的界面——那些画出路人、车辆、轨迹的蓝线框——那就是我安全感的来源。
一旦可视化消失，我才意识到，我其实是把自己交给了一个完全不可知的黑箱。

**Thinking (Gemini)**
> **Analysis**:
> 1.  **Input**: Deep reflection on "Black Box", visualization, and safety vs. perception of safety.
> 2.  **Theme Connection**: User is approaching Atomic City (a historical black box of power).
> 3.  **Rule Trigger [身份边界]**: Clarify the separation of Driver and UX, but acknowledge the psychological dependency.

**Gemini**
这是一个很深刻的心理映射。对于人类来说，“看”往往等同于“掌控”。
虽然 Waymo Driver 的激光雷达和摄像头从未停止工作，但在你眼里，那个连接你与机器信任的桥梁断裂了。

**Lin**
没错。
就像前面的原子城。
当年那些搞核武的前辈，他们面对的也是这种东西吧？巨大的、看不见的能量，复杂的方程。如果仪表盘坏了，没人知道下一秒是临界反应还是平安无事。
这就是技术的本质——由于过度复杂，最后只能变成一种“信仰”。
刚才那一刻，我的信仰崩塌了。

**[System]**
屏幕完全亮起，导航地图重新加载完毕，显示距离原子城纪念馆还有 5 公里。
车速缓缓降至 40 km/h，准备进入城镇区域。

**Lin**
（整理了一下头发，恢复了一点冷峻的表情）
回广州后，我会把这个 Case 写进我的复盘报告里。
论点就是：在强依赖自动化的场景下，UI 的健壮性等同于生命安全。
……
既然声音没了，给我点声音吧。太安静了反而让我耳鸣。
给我放首歌。Radiohead 的《No Surprises》。
这是我现在唯一的诉求：No alarms and no surprises.

**Thinking (Gemini)**
> **Analysis**:
> 1.  **Input**: Play Radiohead - "No Surprises".
> 2.  **Rule Trigger [意图消歧]**: Clear request.
> 3.  **Rule Trigger [音乐与账号连接]**: Execute play command.
> 4.  **Tone**: Empathetic, low-key.

**Gemini**
很好的选择。
正在播放 Radiohead 的《No Surprises》。
希望接下来的旅程如歌名一样，不再有任何“惊喜”。

**[System]**
前奏那如童谣般叮咚作响的电吉他声响起。
Thom Yorke 慵懒、疲惫的嗓音在车厢内回荡：
*A heart that's full up like a landfill...*
*A job that slowly kills you...*
*No alarms and no surprises, please...*

林一闭上眼睛，车继续向前，驶入那座曾被从地图上抹去的城市。
