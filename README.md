# Brahms 4 · 跟着总谱听勃拉姆斯第四

[打开导览](https://melonwater0421.github.io/brahms-four/)

四乐章、93个总谱节点、16段真实管弦乐声部MIDI节选。桌面双栏，手机单栏；支持段落循环、声部静音/独奏、收藏、定位校准和连续乐章。页面打开时不会自动播放。

## 总谱与定位

- 印刷谱：Breitkopf & Härtel《Johannes Brahms Sämtliche Werke》第二卷。卡片直接链接PDF对应页。
- 数字音符：[OpenScore Orchestra / Hauptstimme](https://github.com/MarkGotham/Hauptstimme)，谱面CC0。未复用该项目的分析标注。
- 乐章小节数：440＋弱起、118、357、311。第一乐章弱起记0。
- 已针对扫描谱修正第二乐章41–46小节第二巴松重复录入。
- MIDI是固定速度、基础音色的选定声部节选。转换成实音、保留音高和时值，不模拟完整奏法、力度、颤音和装饰音；不是从唱片分离出的乐器音轨。
- 自动色度DTW定位是近似值；持续音、休止、重复音型等处可能偏移，可在网页逐段校准。
- 顶部“本小节有哪些声部”按数字谱的音符活动显示，表示整小节内有音符，并非当前瞬间的录音声源检测；数字合谱拆分仍可能含独奏/同奏误差。

## 录音

沿用原项目标注为 Carlos Kleiber / Wiener Philharmoniker (DG 1980) 的四条音轨。录音版权属于各自权利人，不纳入数字谱的CC0授权。网页允许替换为本机音轨；本机文件不会上传。

## 本地使用与维护

用任意静态服务器运行，例如 `python3 -m http.server 8081`。打开网页即可，无构建依赖。

`rebuild-tools.zip` 包含编译工具、已审核的中文节点、CC0数字谱及提取结果。解压到项目根目录，安装Python依赖 `music21 mido numpy scipy librosa`。`python tools/build_atlas.py` 重建data.js与节选MIDI；`python tools/verify_atlas.py` 检查小节、音符完整性、声部及MIDI时长。重新对齐可运行 `tools/score_pipeline.py`；删除对应alignment缓存后才会重算。

发布使用GitHub Pages的main分支根目录。没有分析统计或广告。
