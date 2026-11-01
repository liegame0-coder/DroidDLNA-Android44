DroidDLNA Android 4.4 云端构建配置

本项目已加入 GitHub Actions 工作流：
.github/workflows/build-android44.yml

它会在 GitHub Actions 云端执行：
1. 使用 JDK 8
2. 安装 Android SDK Platform 22 和 Build Tools 22.0.1
3. 使用 Gradle 2.2.1 构建旧版 Android 工程
4. 将 app/build/outputs/apk 下生成的 APK 上传为 Actions Artifact

重要：此配置只是自动化构建脚本，不代表 APK 已经构建或通过设备测试。
要实际运行云端构建，必须把整个项目提交到一个 GitHub 仓库并启用 Actions。当前 ChatGPT 执行环境没有 GitHub 仓库授权/推送凭据，也无法直接替用户创建仓库或推送代码；因此本次无法替用户触发 GitHub 构建。

兼容性目标：minSdkVersion 15，面向 Android 4.4 / ARM 32 位设备。
设备播放能力仍取决于盒子系统媒体解码器及网页投送 URL 类型；DRM、部分 HLS/DASH/特殊网页流不保证支持。
