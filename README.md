# 🎙️ 声音魔法师 - 让文字开口说话的神器

一个基于 Microsoft Edge TTS 的免费在线语音合成服务，支持 20+ 种中文声音，一键将文字转换为自然流畅的语音。

## ✨ 特性

- 🎵 **20+ 种中文声音** - 支持多种音色和风格，包括男声、女声等
- ⚡ **秒速生成** - 快速生成高质量语音文件
- 🆓 **完全免费** - 无需注册，无使用限制
- 📱 **响应式设计** - 完美适配桌面端和移动端
- 🎛️ **丰富参数** - 支持语速、音调、语音风格等多种调节
- 📥 **支持下载** - 生成的音频可直接下载为 MP3 格式
- 🔗 **API 兼容** - 兼容 OpenAI TTS API 格式

## 🚀 一键部署

### 点击按钮，一键部署到 CloudFlare Workers,

[![Deploy to Cloudflare Workers](https://deploy.workers.cloudflare.com/button)](https://deploy.workers.cloudflare.com/?url=https://github.com/wangwangit/tts)



## 🎯 使用方法

### 网页界面使用

1. 访问部署后的 Worker 域名
2. 在文本框中输入要转换的文字
3. 选择喜欢的语音、语速、音调等参数
4. 点击"开始生成语音"按钮
5. 播放生成的音频或下载 MP3 文件

### API 调用

```javascript
// 基本调用
const response = await fetch('https://your-worker.workers.dev/v1/audio/speech', {
    method: 'POST',
    headers: {
        'Content-Type': 'application/json',
    },
    body: JSON.stringify({
        input: "你好，这是一个测试",
        voice: "zh-CN-XiaoxiaoNeural",
        speed: 1.0,
        pitch: "0",
        style: "general"
    })
});

const audioBlob = await response.blob();
```

```bash
# cURL 调用
curl -X POST "https://your-worker.workers.dev/v1/audio/speech" \
  -H "Content-Type: application/json" \
  -d '{
    "input": "你好，这是一个测试",
    "voice": "zh-CN-XiaoxiaoNeural",
    "speed": 1.0,
    "pitch": "0",
    "style": "general"
  }' \
  --output speech.mp3
```

## 🎨 支持的语音

### 女声
- `zh-CN-XiaoxiaoNeural` - 晓晓 (温柔)
- `zh-CN-XiaoyiNeural` - 晓伊 (甜美)
- `zh-CN-XiaochenNeural` - 晓辰 (知性)
- `zh-CN-XiaohanNeural` - 晓涵 (优雅)
- `zh-CN-XiaomengNeural` - 晓梦 (梦幻)
- `zh-CN-XiaomoNeural` - 晓墨 (文艺)
- `zh-CN-XiaoqiuNeural` - 晓秋 (成熟)
- `zh-CN-XiaoruiNeural` - 晓睿 (智慧)
- `zh-CN-XiaoshuangNeural` - 晓双 (活泼)
- `zh-CN-XiaoxuanNeural` - 晓萱 (清新)
- `zh-CN-XiaoyanNeural` - 晓颜 (柔美)
- `zh-CN-XiaoyouNeural` - 晓悠 (悠扬)
- `zh-CN-XiaozhenNeural` - 晓甄 (端庄)

### 男声
- `zh-CN-YunxiNeural` - 云希 (清朗)
- `zh-CN-YunyangNeural` - 云扬 (阳光)
- `zh-CN-YunjianNeural` - 云健 (稳重)
- `zh-CN-YunfengNeural` - 云枫 (磁性)
- `zh-CN-YunhaoNeural` - 云皓 (豪迈)
- `zh-CN-YunxiaNeural` - 云夏 (热情)
- `zh-CN-YunyeNeural` - 云野 (野性)
- `zh-CN-YunzeNeural` - 云泽 (深沉)

## ⚙️ API 参数

| 参数 | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| `input` | string | - | 要转换的文本内容（必填） |
| `voice` | string | `zh-CN-XiaoxiaoNeural` | 语音选择 |
| `speed` | number | `1.0` | 语速 (0.5-2.0) |
| `pitch` | string | `"0"` | 音调 (-50 到 50) |
| `style` | string | `"general"` | 语音风格 |
| `volume` | string | `"0"` | 音量调节 |

### 支持的语音风格

- `general` - 通用风格
- `assistant` - 智能助手
- `chat` - 聊天对话
- `customerservice` - 客服专业
- `newscast` - 新闻播报
- `affectionate` - 亲切温暖
- `calm` - 平静舒缓
- `cheerful` - 愉快欢乐
- `gentle` - 温和柔美
- `lyrical` - 抒情诗意
- `serious` - 严肃正式

## 🛠️ 技术架构

- **前端**: 现代化 HTML5 + CSS3 + JavaScript
- **后端**: Cloudflare Workers
- **语音引擎**: Microsoft Edge TTS
- **设计系统**: CSS 变量 + 响应式布局
- **API**: RESTful API，兼容 OpenAI TTS 格式

## 🎨 设计特色

- **现代化 UI**: 采用简洁的卡片式设计
- **响应式布局**: 完美适配各种设备尺寸
- **无渐变设计**: 使用纯色设计，更加专业
- **微交互**: 丰富的悬停效果和动画
- **可访问性**: 支持键盘导航和屏幕阅读器

## 📱 移动端优化

- 触摸友好的按钮尺寸
- 移动端专用布局适配
- 手势支持
- 性能优化

## 🔧 开发

### 本地开发

```bash
# 克隆项目
git clone <your-repo>

# 安装 Wrangler CLI
npm install -g wrangler

# 本地开发
wrangler dev
```

### 项目结构

```
├── index.js          # 主要代码文件
├── README.md         # 项目文档
└── wrangler.toml     # Cloudflare Workers 配置
```

## 🤝 贡献

欢迎提交 Issue 和 Pull Request！

## 📄 许可证

MIT License

## 🙏 致谢

- Microsoft Edge TTS 提供语音合成服务
- Cloudflare Workers 提供无服务器计算平台
- 参考项目: https://github.com/pyvideotrans/tts-pyvideotrans2

## 📞 联系我们

关注公众号「一只会飞的旺旺」获取更多 AI 工具和技术分享：

- 最新 AI 工具推荐和使用教程
- 前沿技术解析和实战案例  
- 独家资源和工具源码分享
- 技术问题答疑和交流社群

---


**让文字开口说话，让创意更有声音！** 🎵

