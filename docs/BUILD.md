# 构建方式

环境：JDK 17 + Android SDK (platforms;android-34, build-tools;34.0.0)

```bash
./build.sh
# 输出：Cici-1.0.apk
```

步骤：aapt2 compile → aapt2 link（含 assets）→ javac → d8 → zip classes.dex → zipalign → apksigner 签名。

源码包 Cici-source-v1.0.zip 内包含 app/src/main（Manifest、Java、assets/index.html、图标）与 build.sh。
