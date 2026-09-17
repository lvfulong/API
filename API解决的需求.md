# 基础 API

本 API 集合对标支付宝小游戏 API，覆盖小游戏开发中常见的系统、渲染、交互、网络、存储、授权、支付等通用能力，可视为小游戏行业的基础能力标准。

开发者可基于这些 API 实现游戏生命周期管理、触摸与键盘输入、画面和音频播放、资源与本地存档管理、服务端通信、用户授权及商业化等通用需求，而无需针对每项宿主能力重复自行实现。

## 基础

| 函数名 | 链接地址 | 用途说明 | 实例应用案例 |
| --- | --- | --- | --- |
| `my.canIUse` | [链接](https://opendocs.alipay.com/mini-game/a7e1af7b_my.canIUse?pathHash=1e43471e) | 在调用能力前判断当前宿主是否支持，避免旧版本或不同平台直接调用报错。 | 例如：在小游戏的实际功能中使用它来完成“在调用能力前判断当前宿主是否支持，避免旧版本或不同平台直接调用报错”。 |
| `my.getAccountInfoSync` | [链接](https://opendocs.alipay.com/mini-game/d310584a_my.getAccountInfoSync?pathHash=7d14f744) | 读取小游戏的账号、版本等运行信息，用于区分开发、体验和正式环境及定位问题。 | 例如：在小游戏的实际功能中使用它来完成“读取小游戏的账号、版本等运行信息，用于区分开发、体验和正式环境及定位问题”。 |
| `my.arrayBufferToBase64` | [链接](https://opendocs.alipay.com/mini-game/2a611dd4_my.arrayBufferToBase64?pathHash=48cfaf51) | 将二进制资源转换为可放入 JSON、文本协议或 Data URL 的字符串，便于上传和传输。 | 例如：在小游戏的实际功能中使用它来完成“将二进制资源转换为可放入 JSON、文本协议或 Data URL 的字符串，便于上传和传输”。 |
| `my.base64ToArrayBuffer` | [链接](https://opendocs.alipay.com/mini-game/617e43b0_my.base64ToArrayBuffer?pathHash=a1416003) | 将网络或存储中的 Base64 字符串还原为二进制，供图片、音频和文件处理使用。 | 例如：在小游戏的实际功能中使用它来完成“将网络或存储中的 Base64 字符串还原为二进制，供图片、音频和文件处理使用”。 |
| `my.isCollected` | [链接](https://opendocs.alipay.com/mini-game/6d0b314f_my.isCollected?pathHash=756d2dfa) | 查询用户是否已收藏小游戏，以便展示恰当的引导或避免重复提醒。 | 例如：在小游戏的实际功能中使用它来完成“查询用户是否已收藏小游戏，以便展示恰当的引导或避免重复提醒”。 |
| `my.isIDE` | [链接](https://opendocs.alipay.com/mini-game/b2b4ee2a_my.isIDE?pathHash=d6dddb68) | 判断是否运行在 IDE，便于启用调试逻辑并避免将测试行为带入正式环境。 | 例如：在小游戏的实际功能中使用它来完成“判断是否运行在 IDE，便于启用调试逻辑并避免将测试行为带入正式环境”。 |
## 系统
## 生命周期

| 函数名 | 链接地址 | 用途说明 | 实例应用案例 |
| --- | --- | --- | --- |
| `my.onShow` | [链接](https://opendocs.alipay.com/mini-game/08ug7f?pathHash=094834ad) | 在小游戏回到前台时恢复渲染、音频、网络或刷新数据。 | 例如：在小游戏的实际功能中使用它来完成“在小游戏回到前台时恢复渲染、音频、网络或刷新数据”。 |
| `my.onHide` | [链接](https://opendocs.alipay.com/mini-game/08v47y?pathHash=920eb47e) | 在小游戏进入后台时暂停计时、动画和音频，降低资源消耗并保存状态。 | 例如：在小游戏的实际功能中使用它来完成“在小游戏进入后台时暂停计时、动画和音频，降低资源消耗并保存状态”。 |
| `my.offShow` | [链接](https://opendocs.alipay.com/mini-game/08ug7g?pathHash=115b4537) | 解除前台事件监听，防止多次进入页面后重复恢复逻辑。 | 例如：离开对应游戏页面或完成一次关键操作后，及时停止“my.offShow”相关处理。 |
| `my.offHide` | [链接](https://opendocs.alipay.com/mini-game/08v6wb?pathHash=96884371) | 解除后台事件监听，防止退出页面后仍错误暂停业务。 | 例如：离开对应游戏页面或完成一次关键操作后，及时停止“my.offHide”相关处理。 |

## 应用级事件

| 函数名 | 链接地址 | 用途说明 | 实例应用案例 |
| --- | --- | --- | --- |
| `my.onError` | [链接](https://opendocs.alipay.com/mini-game/098k8n?pathHash=a32773c0) | 集中捕获未处理错误，解决线上异常难以发现和上报的问题。 | 例如：在小游戏的实际功能中使用它来完成“集中捕获未处理错误，解决线上异常难以发现和上报的问题”。 |
| `my.onUnhandledRejection` | [链接](https://opendocs.alipay.com/mini-game/88918e2b_my.onUnhandledRejection?pathHash=b1bfb3ef) | 捕获未处理的 Promise 拒绝，帮助定位异步请求、资源加载等失败。 | 例如：在小游戏的实际功能中使用它来完成“捕获未处理的 Promise 拒绝，帮助定位异步请求、资源加载等失败”。 |
| `my.offUnhandledRejection` | [链接](https://opendocs.alipay.com/mini-game/c302f268_my.offUnhandledRejection?pathHash=a41360c0) | 在不再需要时移除 Promise 异常监听，避免重复告警。 | 例如：离开对应游戏页面或完成一次关键操作后，及时停止“my.offUnhandledRejection”相关处理。 |
## 跳转

| 函数名 | 链接地址 | 用途说明 | 实例应用案例 |
| --- | --- | --- | --- |
| `my.navigateToMiniProgram` | [链接](https://opendocs.alipay.com/mini-game/08ux3x?pathHash=d4a32a2a) | 从当前游戏跳转到关联小程序，支持活动页、服务页或生态导流。 | 例如：在小游戏的实际功能中使用它来完成“从当前游戏跳转到关联小程序，支持活动页、服务页或生态导流”。 |

## 触摸

| 函数名 | 链接地址 | 用途说明 | 实例应用案例 |
| --- | --- | --- | --- |
| `my.onTouchStart` | [链接](https://opendocs.alipay.com/mini-game/08urvd?pathHash=f1a08050) | 获取触摸开始位置，用于按钮按下、拖拽和手势识别。 | 例如：按下屏幕虚拟摇杆时记录初始坐标。 |
| `my.onTouchMove` | [链接](https://opendocs.alipay.com/mini/api/my.onTouchMove) | 持续获取触摸轨迹，用于摇杆、滑动、拖动物体等实时交互。 | 例如：拖动虚拟摇杆控制角色移动方向。 |
| `my.onTouchEnd` | [链接](https://opendocs.alipay.com/mini/api/my.onTouchEnd) | 获得触摸结束事件，用于确认点击、结算拖拽或结束手势。 | 例如：松开攻击按钮后结束蓄力。 |
| `my.onTouchCancel` | [链接](https://opendocs.alipay.com/mini/api/my.onTouchCancel) | 处理被系统中断的触摸，避免按键或拖拽状态卡住。 | 例如：动作游戏中用它实现点击按钮、拖拽和虚拟摇杆操作。 |
| `my.offTouchStart` | [链接](https://opendocs.alipay.com/mini/api/my.offTouchStart) | 取消触摸开始监听，避免页面切换后继续响应。 | 例如：离开对应游戏页面或完成一次关键操作后，及时停止“my.offTouchStart”相关处理。 |
| `my.offTouchMove` | [链接](https://opendocs.alipay.com/mini/api/my.offTouchMove) | 取消移动监听，避免重复计算和无效渲染。 | 例如：离开对应游戏页面或完成一次关键操作后，及时停止“my.offTouchMove”相关处理。 |
| `my.offTouchEnd` | [链接](https://opendocs.alipay.com/mini/api/my.offTouchEnd) | 取消结束监听，避免一次操作触发多个旧逻辑。 | 例如：离开对应游戏页面或完成一次关键操作后，及时停止“my.offTouchEnd”相关处理。 |
| `my.offTouchCancel` | [链接](https://opendocs.alipay.com/mini/api/my.offTouchCancel) | 取消中断监听，保持事件生命周期可控。 | 例如：离开对应游戏页面或完成一次关键操作后，及时停止“my.offTouchCancel”相关处理。 |
| `Touch` | [链接](https://opendocs.alipay.com/mini/api/Touch) | 提供标准触点数据结构，使多指手势和坐标处理有统一数据格式。 | 例如：动作游戏中用它实现点击按钮、拖拽和虚拟摇杆操作。 |
## 设备
### 键盘

| 函数名 | 链接地址 | 用途说明 | 实例应用案例 |
| --- | --- | --- | --- |
| `my.showKeyboard` | [链接](https://opendocs.alipay.com/mini-game/08ug7d?pathHash=eae21012) | 在 Canvas 游戏中主动调起系统键盘，满足昵称、聊天和兑换码输入。 | 例如：在角色命名页点击自绘输入框后调起软键盘。 |
| `my.onKeyboardInput` | [链接](https://opendocs.alipay.com/mini/api/my.onKeyboardInput) | 实时取得输入内容，用于同步更新自绘输入框。 | 例如：将键盘输入实时绘制到昵称输入框中。 |
| `my.onKeyboardConfirm` | [链接](https://opendocs.alipay.com/mini/api/my.onKeyboardConfirm) | 监听用户确认键，用于提交聊天、搜索或表单。 | 例如：用户点击“完成”后提交兑换码。 |
| `my.onKeyboardComplete` | [链接](https://opendocs.alipay.com/mini/api/my.onKeyboardComplete) | 在键盘输入结束时统一处理提交或收起后的状态。 | 例如：聊天输入结束后收起输入面板并恢复游戏操作。 |
| `my.offKeyboardInput` | [链接](https://opendocs.alipay.com/mini/api/my.offKeyboardInput) | 移除输入监听，避免离开输入界面后仍修改数据。 | 例如：离开对应游戏页面或完成一次关键操作后，及时停止“my.offKeyboardInput”相关处理。 |
| `my.offKeyboardConfirm` | [链接](https://opendocs.alipay.com/mini/api/my.offKeyboardConfirm) | 移除确认监听，避免重复提交。 | 例如：离开对应游戏页面或完成一次关键操作后，及时停止“my.offKeyboardConfirm”相关处理。 |
| `my.offKeyboardComplete` | [链接](https://opendocs.alipay.com/mini/api/my.offKeyboardComplete) | 移除完成监听，避免旧页面收到回调。 | 例如：离开对应游戏页面或完成一次关键操作后，及时停止“my.offKeyboardComplete”相关处理。 |
| `my.hideKeyboard` | [链接](https://opendocs.alipay.com/mini/api/my.hideKeyboard) | 主动收起键盘，为返回游戏操作或切换界面腾出屏幕。 | 例如：提交角色名后主动关闭软键盘。 |

### 内存不足警告

| 函数名 | 链接地址 | 用途说明 | 实例应用案例 |
| --- | --- | --- | --- |
| `my.onMemoryWarning` | [链接](https://opendocs.alipay.com/mini-game/2b435749_my.onMemoryWarning?pathHash=51ce35c1) | 在内存紧张时释放缓存、纹理或音频，降低被系统终止的风险。 | 例如：内存告警后清除未使用的角色纹理缓存。 |
| `my.offMemoryWarning` | [链接](https://opendocs.alipay.com/mini/api/my.offMemoryWarning) | 在资源管理器销毁时取消内存告警监听。 | 例如：离开对应游戏页面或完成一次关键操作后，及时停止“my.offMemoryWarning”相关处理。 |

## 定时器

| 函数名 | 链接地址 | 用途说明 | 实例应用案例 |
| --- | --- | --- | --- |
| `clearInterval` | [链接](https://opendocs.alipay.com/mini-game/08urve?pathHash=189afa3d) | 停止周期任务，避免后台持续耗电或重复执行。 | 例如：在小游戏的实际功能中使用它来完成“停止周期任务，避免后台持续耗电或重复执行”。 |
| `clearTimeout` | [链接](https://opendocs.alipay.com/mini-game/08upey?pathHash=46fec91c) | 取消未执行的延时任务，避免界面退出后仍更新。 | 例如：在小游戏的实际功能中使用它来完成“取消未执行的延时任务，避免界面退出后仍更新”。 |
| `setInterval` | [链接](https://opendocs.alipay.com/mini-game/08v38r?pathHash=d29e7653) | 周期执行任务，适合倒计时、轮询和循环效果。 | 例如：在小游戏的实际功能中使用它来完成“周期执行任务，适合倒计时、轮询和循环效果”。 |
| `setTimeout` | [链接](https://opendocs.alipay.com/mini-game/08uo7u?pathHash=5ed2888c) | 延后执行一次任务，适合延迟提示、技能冷却和重试。 | 例如：在小游戏的实际功能中使用它来完成“延后执行一次任务，适合延迟提示、技能冷却和重试”。 |

## 渲染

| 函数名 | 链接地址 | 用途说明 | 实例应用案例 |
| --- | --- | --- | --- |
| `Canvas 概览` | [链接](https://opendocs.alipay.com/mini-game/0gkuic?pathHash=ba991885) | 说明游戏绘制载体，帮助开发者承载自定义游戏画面。 | 例如：在主战斗场景中用它绘制角色、地图和特效。 |
| `Canvas.getContext` | [链接](https://opendocs.alipay.com/mini/api/Canvas.getContext) | 获取绘图上下文，以执行 2D 或图形渲染操作。 | 例如：在主战斗场景中用它绘制角色、地图和特效。 |
| `Image` | [链接](https://opendocs.alipay.com/mini/api/Image) | 提供图像对象，解决纹理、角色和 UI 图片的加载与绘制需求。 | 例如：在主战斗场景中用它绘制角色、地图和特效。 |
| `requestAnimationFrame` | [链接](https://opendocs.alipay.com/mini/api/requestAnimationFrame) | 按屏幕刷新节奏驱动动画，减少卡顿和无效绘制。 | 例如：按屏幕刷新频率驱动角色跑动动画。 |
| `RenderingContext` | [链接](https://opendocs.alipay.com/mini/api/RenderingContext) | 提供统一渲染上下文能力，便于绘制 API 协作。 | 例如：在主战斗场景中用它绘制角色、地图和特效。 |
| `my.createCanvas` | [链接](https://opendocs.alipay.com/mini/api/my.createCanvas) | 创建离屏或额外画布，用于缓存画面、截图和分层渲染。 | 例如：创建离屏画布缓存复杂的地图图层。 |
| `my.createImage` | [链接](https://opendocs.alipay.com/mini/api/my.createImage) | 创建可加载资源的图片实例，供 Canvas 绘制使用。 | 例如：在小游戏的实际功能中使用它来完成“创建可加载资源的图片实例，供 Canvas 绘制使用”。 |
| `my.loadFont` | [链接](https://opendocs.alipay.com/mini/api/my.loadFont) | 加载自定义字体，保证品牌字形、数字或多语言文本的视觉一致性。 | 例如：加载像素字体来绘制关卡得分。 |
| `my.setPreferredFramesPerSecond` | [链接](https://opendocs.alipay.com/mini/api/my.setPreferredFramesPerSecond) | 设置目标帧率，在流畅度、耗电和发热之间按游戏类型取舍。 | 例如：在小游戏的实际功能中使用它来完成“设置目标帧率，在流畅度、耗电和发热之间按游戏类型取舍”。 |

## 性能

| 函数名 | 链接地址 | 用途说明 | 实例应用案例 |
| --- | --- | --- | --- |
| `my.triggerGC` | [链接](https://opendocs.alipay.com/mini/api/my.triggerGC) | 在资源大量释放后请求垃圾回收，帮助缓解短时内存压力。 | 例如：在小游戏的实际功能中使用它来完成“在资源大量释放后请求垃圾回收，帮助缓解短时内存压力”。 |

## 交互

| 函数名 | 链接地址 | 用途说明 | 实例应用案例 |
| --- | --- | --- | --- |
| `my.showLoading` | [链接](https://opendocs.alipay.com/mini-game/08uqnz?pathHash=60ce23a6) | 在请求或资源加载期间给用户明确反馈，减少“卡住了”的误解。 | 例如：在小游戏的实际功能中使用它来完成“在请求或资源加载期间给用户明确反馈，减少“卡住了”的误解”。 |
| `my.alert` | [链接](https://opendocs.alipay.com/mini/api/my.alert) | 告知必须确认的重要信息，如版本提示或不可恢复的错误。 | 例如：在小游戏的实际功能中使用它来完成“告知必须确认的重要信息，如版本提示或不可恢复的错误”。 |
| `my.confirm` | [链接](https://opendocs.alipay.com/mini/api/my.confirm) | 让用户二次确认高影响操作，如退出关卡或删除存档。 | 例如：在小游戏的实际功能中使用它来完成“让用户二次确认高影响操作，如退出关卡或删除存档”。 |
| `my.hideLoading` | [链接](https://opendocs.alipay.com/mini/api/my.hideLoading) | 在任务完成后关闭加载提示，恢复正常操作。 | 例如：在小游戏的实际功能中使用它来完成“在任务完成后关闭加载提示，恢复正常操作”。 |
| `my.hideToast` | [链接](https://opendocs.alipay.com/mini/api/my.hideToast) | 提前关闭不再适用的提示，避免遮挡关键操作。 | 例如：在小游戏的实际功能中使用它来完成“提前关闭不再适用的提示，避免遮挡关键操作”。 |
| `my.prompt` | [链接](https://opendocs.alipay.com/mini/api/my.prompt) | 获取一段简短文本，满足命名、输入房间号等需求。 | 例如：在小游戏的实际功能中使用它来完成“获取一段简短文本，满足命名、输入房间号等需求”。 |
| `my.showActionSheet` | [链接](https://opendocs.alipay.com/mini/api/my.showActionSheet) | 在多个操作中让用户选择，如分享、保存或装备操作。 | 例如：在小游戏的实际功能中使用它来完成“在多个操作中让用户选择，如分享、保存或装备操作”。 |
| `my.showToast` | [链接](https://opendocs.alipay.com/mini/api/my.showToast) | 显示轻量、短暂的结果提示，如“领取成功”或“网络异常”。 | 例如：在小游戏的实际功能中使用它来完成“显示轻量、短暂的结果提示，如“领取成功”或“网络异常””。 |
| `my.showModal` | [链接](https://opendocs.alipay.com/mini/api/my.showModal) | 展示自定义标题与操作的模态对话，承载公告、确认和引导。 | 例如：在小游戏的实际功能中使用它来完成“展示自定义标题与操作的模态对话，承载公告、确认和引导”。 |

## 网络

| 函数名 | 链接地址 | 用途说明 | 实例应用案例 |
| --- | --- | --- | --- |
| `my.request` | [链接](https://opendocs.alipay.com/mini-game/08uy1c?pathHash=79945623) | 发起 HTTP 请求，解决登录、配置拉取、排行榜和业务数据访问。 | 例如：进入排行榜页时请求服务端排名数据。 |

## WebSocket

| 函数名 | 链接地址 | 用途说明 | 实例应用案例 |
| --- | --- | --- | --- |
| `my.closeSocket` | [链接](https://opendocs.alipay.com/mini-game/08uqo1?pathHash=ef8f4cbd) | 主动关闭长连接，节省后台资源并完成退出清理。 | 例如：多人对战房间中使用它维护实时连接和消息状态。 |
| `my.connectSocket` | [链接](https://opendocs.alipay.com/mini/api/my.connectSocket) | 建立长连接，满足多人对战、聊天室和实时状态同步。 | 例如：进入多人房间后建立实时对战连接。 |
| `my.offSocketClose` | [链接](https://opendocs.alipay.com/mini/api/my.offSocketClose) | 解除关闭监听，避免销毁后误触发重连。 | 例如：离开对应游戏页面或完成一次关键操作后，及时停止“my.offSocketClose”相关处理。 |
| `my.offSocketError` | [链接](https://opendocs.alipay.com/mini/api/my.offSocketError) | 解除错误监听，避免重复错误提示。 | 例如：离开对应游戏页面或完成一次关键操作后，及时停止“my.offSocketError”相关处理。 |
| `my.offSocketMessage` | [链接](https://opendocs.alipay.com/mini/api/my.offSocketMessage) | 解除消息监听，避免退出房间后仍处理旧消息。 | 例如：离开对应游戏页面或完成一次关键操作后，及时停止“my.offSocketMessage”相关处理。 |
| `my.offSocketOpen` | [链接](https://opendocs.alipay.com/mini/api/my.offSocketOpen) | 解除连接成功监听，避免重复鉴权。 | 例如：离开对应游戏页面或完成一次关键操作后，及时停止“my.offSocketOpen”相关处理。 |
| `my.onSocketClose` | [链接](https://opendocs.alipay.com/mini/api/my.onSocketClose) | 感知连接关闭，以便释放状态或执行断线重连。 | 例如：多人对战房间中使用它维护实时连接和消息状态。 |
| `my.onSocketError` | [链接](https://opendocs.alipay.com/mini/api/my.onSocketError) | 感知连接异常，以便提示用户、记录日志或安排重连。 | 例如：多人对战房间中使用它维护实时连接和消息状态。 |
| `my.onSocketMessage` | [链接](https://opendocs.alipay.com/mini/api/my.onSocketMessage) | 接收服务端实时消息，驱动对局状态或聊天内容更新。 | 例如：收到对手操作后同步战场画面。 |
| `my.onSocketOpen` | [链接](https://opendocs.alipay.com/mini/api/my.onSocketOpen) | 在连接就绪后发送鉴权或首批同步消息。 | 例如：多人对战房间中使用它维护实时连接和消息状态。 |
| `my.sendSocketMessage` | [链接](https://opendocs.alipay.com/mini/api/my.sendSocketMessage) | 向服务端发送操作、聊天或心跳数据。 | 例如：将玩家的移动指令发送给对战服务器。 |

## 音频

| 函数名 | 链接地址 | 用途说明 | 实例应用案例 |
| --- | --- | --- | --- |
| `my.createInnerAudioContext` | [链接](https://opendocs.alipay.com/mini-game/08uug1?pathHash=a6eb7ef5) | 创建独立音频播放器，满足背景音乐、音效与语音播放控制。 | 例如：创建并播放关卡背景音乐。 |
| `my.getRecorderManager` | [链接](https://opendocs.alipay.com/mini/api/my.getRecorderManager)（未支持） | 提供录音管理入口，服务语音聊天或语音投稿等需求（当前未支持）。 | 例如：在小游戏的实际功能中使用它来完成“提供录音管理入口，服务语音聊天或语音投稿等需求（当前未支持）”。 |
| `my.getAvailableAudioSources` | [链接](https://opendocs.alipay.com/mini/api/my.getAvailableAudioSources)（未支持） | 查询可用音频输入源，支持录音设备选择（当前未支持）。 | 例如：在小游戏的实际功能中使用它来完成“查询可用音频输入源，支持录音设备选择（当前未支持）”。 |

## 存储

| 函数名 | 链接地址 | 用途说明 | 实例应用案例 |
| --- | --- | --- | --- |
| `my.setStorageSync` | [链接](https://opendocs.alipay.com/mini-game/08upew?pathHash=34661fde) | 同步保存小量关键数据，如设置或最近一次状态。 | 例如：保存玩家的音效开关设置。 |
| `my.setStorage` | [链接](https://opendocs.alipay.com/mini/api/my.setStorage) | 异步保存数据，避免较大写入阻塞游戏主线程。 | 例如：在设置页或账号切换时用它管理本地游戏配置与存档。 |
| `my.removeStorageSync` | [链接](https://opendocs.alipay.com/mini/api/my.removeStorageSync) | 同步删除指定缓存，完成退出登录或重置某项设置。 | 例如：在设置页或账号切换时用它管理本地游戏配置与存档。 |
| `my.removeStorage` | [链接](https://opendocs.alipay.com/mini/api/my.removeStorage) | 异步删除指定缓存，避免清理时阻塞界面。 | 例如：在设置页或账号切换时用它管理本地游戏配置与存档。 |
| `my.getStorageInfoSync` | [链接](https://opendocs.alipay.com/mini/api/my.getStorageInfoSync) | 读取本地存储用量和键列表，用于容量管理。 | 例如：在设置页或账号切换时用它管理本地游戏配置与存档。 |
| `my.getStorageInfo` | [链接](https://opendocs.alipay.com/mini/api/my.getStorageInfo) | 异步读取存储信息，用于后台检查和清理策略。 | 例如：在设置页或账号切换时用它管理本地游戏配置与存档。 |
| `my.getStorageSync` | [链接](https://opendocs.alipay.com/mini/api/my.getStorageSync) | 同步读取启动即需的数据，如语言和画质设置。 | 例如：启动时读取上次选择的画质档位。 |
| `my.getStorage` | [链接](https://opendocs.alipay.com/mini/api/my.getStorage) | 异步读取数据，适合不要求立即返回的存档或缓存。 | 例如：在设置页或账号切换时用它管理本地游戏配置与存档。 |
| `my.clearStorageSync` | [链接](https://opendocs.alipay.com/mini/api/my.clearStorageSync) | 立即清空本地数据，适合彻底重置或账号切换。 | 例如：在设置页或账号切换时用它管理本地游戏配置与存档。 |
| `my.clearStorage` | [链接](https://opendocs.alipay.com/mini/api/my.clearStorage) | 异步清空本地数据，降低大量清理对交互的影响。 | 例如：在设置页或账号切换时用它管理本地游戏配置与存档。 |

## 图片

| 函数名 | 链接地址 | 用途说明 | 实例应用案例 |
| --- | --- | --- | --- |
| `my.previewImage` | [链接](https://opendocs.alipay.com/mini-game/08unfy?pathHash=957bc8d6) | 全屏预览图片，满足查看海报、截图和奖励图片。 | 例如：在小游戏的实际功能中使用它来完成“全屏预览图片，满足查看海报、截图和奖励图片”。 |
| `my.saveImageToPhotosAlbum` | [链接](https://opendocs.alipay.com/mini/api/my.saveImageToPhotosAlbum) | 将图片保存到系统相册，便于用户留存战绩或宣传图。 | 例如：将通关海报保存到用户相册。 |
| `my.chooseImage` | [链接](https://opendocs.alipay.com/mini/api/my.chooseImage) | 让用户选择图片，支持头像上传、反馈和内容创作。 | 例如：让玩家选择图片作为自定义头像。 |

## 文件

| 函数名 | 链接地址 | 用途说明 | 实例应用案例 |
| --- | --- | --- | --- |
| `my.getFileSystemManager` | [链接](https://opendocs.alipay.com/mini-game/08ujw2?pathHash=70d47ebb) | 获取文件系统能力，用于管理下载资源、离线包和大文件存档。 | 例如：在小游戏的实际功能中使用它来完成“获取文件系统能力，用于管理下载资源、离线包和大文件存档”。 |
| `Stats` | [链接](https://opendocs.alipay.com/mini/api/Stats) | 表示文件状态信息，让开发者判断文件大小、类型和修改时间。 | 例如：在小游戏的实际功能中使用它来完成“表示文件状态信息，让开发者判断文件大小、类型和修改时间”。 |
| `FileSystemManager.access` | [链接](https://opendocs.alipay.com/mini/api/FileSystemManager.access) | 异步检查文件或目录是否可访问，避免后续操作失败。 | 例如：资源热更新模块中使用它管理已下载的关卡资源文件。 |
| `FileSystemManager.accessSync` | [链接](https://opendocs.alipay.com/mini/api/FileSystemManager.accessSync) | 同步检查关键文件是否存在，适合启动前快速判断。 | 例如：离开对应游戏页面或完成一次关键操作后，及时停止“FileSystemManager.accessSync”相关处理。 |
| `FileSystemManager.appendFile` | [链接](https://opendocs.alipay.com/mini/api/FileSystemManager.appendFile) | 异步追加内容，适合日志或分段下载数据。 | 例如：资源热更新模块中使用它管理已下载的关卡资源文件。 |
| `FileSystemManager.appendFileSync` | [链接](https://opendocs.alipay.com/mini/api/FileSystemManager.appendFileSync) | 同步追加关键小数据。 | 例如：离开对应游戏页面或完成一次关键操作后，及时停止“FileSystemManager.appendFileSync”相关处理。 |
| `FileSystemManager.copyFile` | [链接](https://opendocs.alipay.com/mini/api/FileSystemManager.copyFile) | 异步复制文件，用于备份、资源迁移和生成副本。 | 例如：资源热更新模块中使用它管理已下载的关卡资源文件。 |
| `FileSystemManager.copyFileSync` | [链接](https://opendocs.alipay.com/mini/api/FileSystemManager.copyFileSync) | 同步复制启动流程所需的小文件。 | 例如：离开对应游戏页面或完成一次关键操作后，及时停止“FileSystemManager.copyFileSync”相关处理。 |
| `FileSystemManager.getFileInfo` | [链接](https://opendocs.alipay.com/mini/api/FileSystemManager.getFileInfo) | 异步读取文件大小、摘要等信息，用于校验下载资源。 | 例如：资源热更新模块中使用它管理已下载的关卡资源文件。 |
| `FileSystemManager.getFileInfoSync` | [链接](https://opendocs.alipay.com/mini/api/FileSystemManager.getFileInfoSync) | 同步读取关键文件信息。 | 例如：离开对应游戏页面或完成一次关键操作后，及时停止“FileSystemManager.getFileInfoSync”相关处理。 |
| `FileSystemManager.getSavedFileList` | [链接](https://opendocs.alipay.com/mini/api/FileSystemManager.getSavedFileList) | 列出持久保存的文件，便于实现下载管理和清理界面。 | 例如：资源热更新模块中使用它管理已下载的关卡资源文件。 |
| `FileSystemManager.mkdir` | [链接](https://opendocs.alipay.com/mini/api/FileSystemManager.mkdir) | 异步创建目录，组织存档、缓存和资源分类。 | 例如：资源热更新模块中使用它管理已下载的关卡资源文件。 |
| `FileSystemManager.mkdirSync` | [链接](https://opendocs.alipay.com/mini/api/FileSystemManager.mkdirSync) | 同步创建启动时必需目录。 | 例如：离开对应游戏页面或完成一次关键操作后，及时停止“FileSystemManager.mkdirSync”相关处理。 |
| `FileSystemManager.readFile` | [链接](https://opendocs.alipay.com/mini/api/FileSystemManager.readFile) | 异步读取文件内容，加载配置、存档或资源数据。 | 例如：资源热更新模块中使用它管理已下载的关卡资源文件。 |
| `FileSystemManager.readFileSync` | [链接](https://opendocs.alipay.com/mini/api/FileSystemManager.readFileSync) | 同步读取必须立即使用的小文件。 | 例如：离开对应游戏页面或完成一次关键操作后，及时停止“FileSystemManager.readFileSync”相关处理。 |
| `FileSystemManager.readdir` | [链接](https://opendocs.alipay.com/mini/api/FileSystemManager.readdir) | 异步读取目录列表，用于扫描资源或存档。 | 例如：资源热更新模块中使用它管理已下载的关卡资源文件。 |
| `FileSystemManager.readdirSync` | [链接](https://opendocs.alipay.com/mini/api/FileSystemManager.readdirSync) | 同步读取关键目录列表。 | 例如：离开对应游戏页面或完成一次关键操作后，及时停止“FileSystemManager.readdirSync”相关处理。 |
| `FileSystemManager.removeSavedFile` | [链接](https://opendocs.alipay.com/mini/api/FileSystemManager.removeSavedFile) | 移除持久保存文件，释放用户设备空间。 | 例如：资源热更新模块中使用它管理已下载的关卡资源文件。 |
| `FileSystemManager.removeSavedFileSync` | [链接](https://opendocs.alipay.com/mini/api/FileSystemManager.removeSavedFileSync) | 同步移除需立即清理的保存文件。 | 例如：离开对应游戏页面或完成一次关键操作后，及时停止“FileSystemManager.removeSavedFileSync”相关处理。 |
| `FileSystemManager.rename` | [链接](https://opendocs.alipay.com/mini/api/FileSystemManager.rename) | 异步重命名或移动文件，用于下载完成后的原子替换。 | 例如：资源热更新模块中使用它管理已下载的关卡资源文件。 |
| `FileSystemManager.renameSync` | [链接](https://opendocs.alipay.com/mini/api/FileSystemManager.renameSync) | 同步重命名关键小文件。 | 例如：离开对应游戏页面或完成一次关键操作后，及时停止“FileSystemManager.renameSync”相关处理。 |
| `FileSystemManager.rmdir` | [链接](https://opendocs.alipay.com/mini/api/FileSystemManager.rmdir) | 异步删除空目录，完成资源或存档分类清理。 | 例如：资源热更新模块中使用它管理已下载的关卡资源文件。 |
| `FileSystemManager.rmdirSync` | [链接](https://opendocs.alipay.com/mini/api/FileSystemManager.rmdirSync) | 同步删除空目录。 | 例如：离开对应游戏页面或完成一次关键操作后，及时停止“FileSystemManager.rmdirSync”相关处理。 |
| `FileSystemManager.saveFile` | [链接](https://opendocs.alipay.com/mini/api/FileSystemManager.saveFile) | 将临时文件转为持久文件，防止资源或存档被系统清理。 | 例如：资源热更新模块中使用它管理已下载的关卡资源文件。 |
| `FileSystemManager.stat` | [链接](https://opendocs.alipay.com/mini/api/FileSystemManager.stat) | 异步获取文件/目录状态，用于判断类型、大小和更新时间。 | 例如：资源热更新模块中使用它管理已下载的关卡资源文件。 |
| `FileSystemManager.statSync` | [链接](https://opendocs.alipay.com/mini/api/FileSystemManager.statSync) | 同步获取关键路径状态。 | 例如：离开对应游戏页面或完成一次关键操作后，及时停止“FileSystemManager.statSync”相关处理。 |
| `FileSystemManager.unlink` | [链接](https://opendocs.alipay.com/mini/api/FileSystemManager.unlink) | 异步删除文件，释放过期缓存和下载包空间。 | 例如：资源热更新模块中使用它管理已下载的关卡资源文件。 |
| `FileSystemManager.unlinkSync` | [链接](https://opendocs.alipay.com/mini/api/FileSystemManager.unlinkSync) | 同步删除需立即失效的文件。 | 例如：离开对应游戏页面或完成一次关键操作后，及时停止“FileSystemManager.unlinkSync”相关处理。 |
| `FileSystemManager.unzip` | [链接](https://opendocs.alipay.com/mini/api/FileSystemManager.unzip) | 解压资源包，支持热更新、分包下载与离线资源。 | 例如：下载资源包后解压新的关卡素材。 |
| `FileSystemManager.writeFile` | [链接](https://opendocs.alipay.com/mini/api/FileSystemManager.writeFile) | 异步写入文件，用于落盘存档、配置和下载内容。 | 例如：资源热更新模块中使用它管理已下载的关卡资源文件。 |
| `FileSystemManager.writeFileSync` | [链接](https://opendocs.alipay.com/mini/api/FileSystemManager.writeFileSync) | 同步写入必须立即持久化的小数据。 | 例如：离开对应游戏页面或完成一次关键操作后，及时停止“FileSystemManager.writeFileSync”相关处理。 |
| `my.detectFileType` | [链接](https://opendocs.alipay.com/mini/api/my.detectFileType)（微信没有，未支持） | 识别文件类型，便于安全处理不同格式文件（当前未支持）。 | 例如：在小游戏的实际功能中使用它来完成“识别文件类型，便于安全处理不同格式文件（当前未支持）”。 |
| `my.saveFileToDisk` | [链接](https://opendocs.alipay.com/mini/api/my.saveFileToDisk)（微信没有，未支持） | 将文件保存到设备磁盘，满足用户导出需求（当前未支持）。 | 例如：在小游戏的实际功能中使用它来完成“将文件保存到设备磁盘，满足用户导出需求（当前未支持）”。 |
| `my.openDocument` | [链接](https://opendocs.alipay.com/mini/api/my.openDocument)（微信没有，未支持） | 调起文档查看，满足打开规则、协议或报告的需求（当前未支持）。 | 例如：在小游戏的实际功能中使用它来完成“调起文档查看，满足打开规则、协议或报告的需求（当前未支持）”。 |
## 订阅
## 更新管理
## 小游戏广告
### banner广告

| 函数名 | 链接地址 | 用途说明 | 实例应用案例 |
| --- | --- | --- | --- |
| `my.createBannerAd` | [链接](https://opendocs.alipay.com/mini-game/7334c5e7_my.createBannerAd?pathHash=cf342c4d) | 创建常驻横幅广告，为免费游戏提供低打扰的变现方式。 | 例如：在大厅底部展示常驻横幅广告。 |
| `BannerAd` | [链接](https://opendocs.alipay.com/mini/api/BannerAd) | 提供横幅广告的展示、隐藏、销毁和事件控制能力。 | 例如：在大厅或结算页中用它接入广告展示与奖励发放。 |

### 激励广告

| 函数名 | 链接地址 | 用途说明 | 实例应用案例 |
| --- | --- | --- | --- |
| `my.createRewardedAd` | [链接](https://opendocs.alipay.com/mini-game/cef940a9_my.createRewardedAd?pathHash=5b968313) | 创建激励视频广告，让用户以观看广告换取复活、奖励或次数。 | 例如：观看激励视频后给玩家发放复活机会。 |
| `RewardedAd` | [链接](https://opendocs.alipay.com/mini/api/RewardedAd) | 提供激励广告的加载、展示和奖励结果处理能力。 | 例如：在大厅或结算页中用它接入广告展示与奖励发放。 |

## 自定义通用菜单
## 分享
## 界面
## 多媒体
## 数据安全
## 位置
## 调试
## Worker

| 函数名 | 链接地址 | 用途说明 | 实例应用案例 |
| --- | --- | --- | --- |
| `my.createWorker` | [链接](https://opendocs.alipay.com/mini-game/eb19ec9b_my.createWorker?pathHash=19e3b770) | 创建 Worker 执行耗时计算，避免寻路、解码等任务卡住主画面。 | 例如：将大地图寻路计算放到 Worker，避免主画面卡顿。 |
| `Worker` | [链接](https://opendocs.alipay.com/mini/api/Worker) | 提供主线程与 Worker 的消息通信和终止能力。 | 例如：在小游戏的实际功能中使用它来完成“提供主线程与 Worker 的消息通信和终止能力”。 |

## 分包加载
# 开放能力 API
## 用户授权

| 函数名 | 链接地址 | 用途说明 | 实例应用案例 |
| --- | --- | --- | --- |
| `my.getAuthCode` | [链接](https://opendocs.alipay.com/mini/api/my.getAuthCode) | 获取可交由服务端换取身份或权限的授权码，完成登录与业务鉴权。 | 例如：登录时获取授权码并交给业务服务端换取会话。 |
| `my.getAuthUserInfo` | [链接](https://opendocs.alipay.com/mini-game/08vab1?pathHash=7f335aa9) | 在用户授权后读取用户资料，满足个人资料展示和账号绑定。 | 例如：授权后在个人主页展示玩家头像和昵称。 |

> [!IMPORTANT]
> `my.getAuthCode` 入参扩展增加了 `scene`、`clientid`、`authclientid`、`appId` 和 `extraData`。
>
> `my.getAuthUserInfo` 返回值扩展增加了 `userId` 和 `mobilePhone`。

### `my.getAuthCode`

获取授权码。该接口为异步接口，除支付宝标准的 `scopes` 参数外，支持向宿主透传场景值、客户端及应用标识和扩展数据。

**提供理由：** 用于在小游戏与业务服务建立可信的用户身份关联。它解决了服务端无法仅凭客户端判断当前用户及其已授权能力的问题，也让不同登录来源可通过 `scene`、客户端标识和扩展数据完成归因。

#### 调用方式

```javascript
my.getAuthCode({
  scopes: ["auth_base", "auth_user"],
  scene: "auth-code-test",
  clientid: "demo-client-id",
  authclientid: "demo-auth-client-id",
  appId: "2026081300000001",
  extraData: {
    scene: "auth-code",
    nested: {
      enabled: true
    }
  },
  success: function (result) {
    console.log("获取授权码成功", result.authCode);
  },
  fail: function (error) {
    console.error("获取授权码失败", error);
  },
  complete: function (result) {
    console.log("获取授权码完成", result);
  }
});
```

#### 属性

| 属性 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| `scopes` | `String \| String[]` | 否 | 授权范围；未传时默认为 `auth_base`。 |
| `scene` | `String` | 否 | 授权场景值，原样传递给宿主。 |
| `clientid` | `String` | 否 | 客户端标识，原样传递给宿主。 |
| `authclientid` | `String` | 否 | 授权客户端标识，原样传递给宿主。 |
| `appId` | `String` | 否 | 应用标识，原样传递给宿主。 |
| `extraData` | `Object` | 否 | 扩展数据，支持嵌套对象并原样传递给宿主。 |
| `success` | `Function` | 否 | 调用成功回调。 |
| `fail` | `Function` | 否 | 调用失败回调。 |
| `complete` | `Function` | 否 | 调用完成回调，无论成功或失败都会执行。 |

#### success 返回值

```json
{
  "authCode": "0b9a9c214b55447986a6af2d8a0bUC09",
  "authSuccessScopes": [
    "auth_base"
  ],
  "authErrorScopes": {}
}
```

| 属性 | 类型 | 说明 |
| --- | --- | --- |
| `authCode` | `String` | 授权码。 |
| `authSuccessScopes` | `Array` | 本次授权成功的 scope 列表。 |
| `authErrorScopes` | `Object` | 失败的授权类型，key 是授权失败的 scope，value 是对应的错误码。 |

## 分享

| 函数名 | 链接地址 | 用途说明 | 实例应用案例 |
| --- | --- | --- | --- |
| `my.onShareAppMessage` | [链接](https://opendocs.alipay.com/mini-game/08vab2?pathHash=24ae6fef) | 配置用户主动分享时的内容，支持传播关卡、邀请和活动。 | 例如：将通关成绩配置为可分享的挑战卡片。 |
| `my.showSharePanel` | [链接](https://opendocs.alipay.com/mini/api/my.showSharePanel) | 主动展示分享面板，缩短邀请好友或传播战绩的路径。 | 例如：通关后主动打开分享面板邀请好友。 |
## 虚拟支付

| 函数名 | 链接地址 | 用途说明 | 实例应用案例 |
| --- | --- | --- | --- |
| `my.requestGamePayment` | [链接](https://opendocs.alipay.com/mini-game/0an78p?pathHash=3f1be7cb) | 发起游戏支付流程，支持购买游戏内商品或权益。 | 例如：购买游戏内金币礼包时发起支付。 |
| `my.tradePay` | | 通过宿主支付能力完成订单支付，支持统一支付渠道接入。 | 例如：购买月卡或道具礼包时，将订单串交由宿主支付渠道处理。 |
### `my.tradePay`

发起交易支付。该接口为异步接口，由 Android 宿主侧的 `LBPayHandler.tradePay` 实现具体支付逻辑。

**提供理由：** 用于在游戏内完成购买道具、会员或虚拟权益等交易，解决开发者需要自行跳出游戏、拼接支付流程的问题；宿主可在统一的支付通道中处理订单与支付结果。

> [!IMPORTANT]
> `my.tradePay` 为扩展接口。

#### 调用方式

```javascript
my.tradePay({
  paymentAmount: {
    currency: "CNY",
    value: "12.50"
  },
  extendedInfo: {},
  paymentString: "complete-order-string",
  type: 3,
  success: function (result) {
    if (result.resultCode === "9000") {
      console.log("支付成功", result);
    } else {
      console.log("支付结果异常", result);
    }
  },
  fail: function (error) {
    console.error("支付调用失败", error);
  },
  complete: function (result) {
    console.log("支付调用完成", result);
  }
});
```

#### 参数

| 参数 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| `paymentAmount` | `Object` | 否 | 支付金额信息。 |
| `paymentAmount.currency` | `String` | 否 | 币种，例如 `CNY`。 |
| `paymentAmount.value` | `String \| Number` | 否 | 金额；运行时传给宿主时转换为字符串。 |
| `extendedInfo` | `Object` | 否 | 透传扩展信息；各字段值传给宿主时转换为字符串。 |
| `paymentString` | `String` | 否 | 与支付类型对应的支付标识、收银台地址或完整订单串。测试示例中为完整订单串。 |
| `type` | `Number \| String` | 否 | 支付类型，映射见下表。 |
| `success` | `Function` | 否 | 接口成功回调。注意仍应检查 `resultCode` 判断业务支付结果。 |
| `fail` | `Function` | 否 | 接口调用失败回调，例如宿主未实现支付或宿主返回错误。 |
| `complete` | `Function` | 否 | 调用结束回调，无论成功或失败都会执行。 |

#### `type` 类型映射

| 数值 | 枚举名 | 兼容字符串 | 含义 |
| --- | --- | --- | --- |
| `0` | `ORDER_ID` | `ORDER_ID`、`orderId` | 订单 ID。 |
| `1` | `PAYMENT_ID` | `PAYMENT_ID`、`paymentId` | 支付 ID。 |
| `2` | `CASHIER_URL` | `CASHIER_URL`、`cashierUrl` | 收银台 URL。 |
| `3` | `ORDER_STRING` | `ORDER_STRING`、`orderString` | 完整订单串。 |

#### success 返回值

| 字段 | 类型 | 说明 |
| --- | --- | --- |
| `resultCode` | `String` | 支付结果码；当前测试以 `"9000"` 表示支付成功。 |
| `resultMessage` | `String` | 可选的支付结果描述，由宿主返回。 |

> [!IMPORTANT]
> `success` 表示宿主支付调用正常返回，不等同于业务支付一定成功。调用方应继续检查 `resultCode`；当前测试用例仅将字符串 `"9000"` 判定为成功。

> [!NOTE]
> Android 宿主需要在 `LBPayHandler.tradePay(params, callback)` 中接入真实支付渠道并调用回调。默认实现会返回 `tradePay is not implemented`，小游戏侧进入 `fail`。

## 渠道码

### `my.getChannelCode`

同步获取宿主提供的渠道码。

**提供理由：** 用于识别用户进入游戏的分发或投放渠道，解决运营统计、渠道归因及按渠道配置活动时缺少来源信息的问题。

**实例应用案例：** 例如：玩家从不同广告投放链接进入游戏时，根据渠道码统计新增用户并发放对应渠道礼包。

> [!IMPORTANT]
> `my.getChannelCode` 为扩展接口。

#### 调用方式

```javascript
const channelCode = my.getChannelCode();
```

#### 参数

无。

#### 返回值

| 类型 | 说明 |
| --- | --- |
| `String` | 宿主返回的渠道码。 |
