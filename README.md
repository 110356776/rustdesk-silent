# RustDesk 无感连接编译

这个仓库用 GitHub Actions 自动编译修改过的 RustDesk Windows 版本。

## 修改内容

去掉了连接成功后弹出的 CM（Connection Manager）窗口，实现"无感连接"。
- 授权前的 Accept/Cancel 弹窗：**保留**
- 密码验证、2FA：**保留**
- 授权成功后的 CM 窗口：**去掉**

## 使用方法

1. 在 GitHub 上创建一个新仓库（公开或私有都行）
2. 把这个仓库的所有文件推上去：
   ```bash
   git init
   git add .
   git commit -m "RustDesk silent connection build"
   git branch -M main
   git remote add origin https://github.com/你的用户名/你的仓库名.git
   git push -u origin main
   ```
3. 推上去后 GitHub Actions 会自动开始编译
4. 点仓库页面的 **Actions** 标签页查看进度
5. 编译完成后（大约 30-40 分钟），点进那次运行，在页面底部 **Artifacts** 区域下载 `RustDesk-Windows-x64-SilentConnection`

## 手动触发

在 Actions 页面选择 "Build RustDesk Windows (Silent Connection)" workflow，点 **Run workflow** 按钮即可重新编译。

## 产物

下载的 zip 解压后，`rustdesk.exe` 就是修改过的版本，直接运行即可。
