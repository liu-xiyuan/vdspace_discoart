![image-20221103172026614](https://mofish-1307188483.cos.ap-chengdu.myqcloud.com/202211031720311.png)

✨ **获取灵感**：加入Disco Diffusion 的 [Discord频道](https://discord.gg/BT8um4WGcC) 获取灵感并分享你的作品。

📒 **了解Discoart**：访问 Discoart 的 [GitHub主页](https://github.com/jina-ai/discoart) 了解更多相关知识。

🎨 **其他的AI创作工具**：[Midjourney](https://discord.gg/midjourney)，

💡 **更多参数细节**：在`docs/`目录下存放有一些关于 Disco Diffusion 的文档资源。



# 部署

**关于将 Discoart 部署至服务器的更多细节请查看由 [@AydenLi](https://github.com/AydenLii) 编写的[文档](https://github.com/liuxiyuan-2022/vdspace_discoart/blob/main/EnvironmentConfig.md)。** 

# 使用

将库拉取到本地

```sh
git clone https://github.com/liuxiyuan-2022/vdspace_discoart.git
```

你可以使用 [Jupyter notebook](##在 Jupyter NoteBook 上使用) 或者 [VS Code](##在 VS Code 上使用) 运行 Discoart 。

## 在 VS Code 上使用

> Visual Studio Code  是一个轻量级但功能强大的源代码编辑器，可在您的桌面上运行，适用于 Windows、macOS 和 Linux。   它内置了对  JavaScript、TypeScript 和 Node.js 的支持，并为其他语言和运行时（如  C++、C#、Java、Python、PHP、Go、.NET）提供了丰富的扩展生态系统。

### 安装 VS Code

- 安装 [VS Code](https://code.visualstudio.com/) 的最新版本

### 安装 VS Code 扩展

1. 打开 VS Code
2. 按下 `Ctrl+Shift+x`  或在左侧边栏点击对应图标，打开扩展列表
3. 在扩展搜索框中输入「**Jupyter**」，然后在扩展预览界面点击 **Install** 安装
4. 点击 **Reload to Activate** 以重新启动 VS Code

### 连接 Jupyter 服务器  

1. 使用 VS Code 打开 `discoart.ipynb` 文件。

2. 在下方的状态栏中点击 **Jupyter 服务器：本地** ，来连接至远程 Jupyter 服务器。

   ![image-20221103135717947](https://mofish-1307188483.cos.ap-chengdu.myqcloud.com/202211031357200.png)

3. 在上方弹出的选项框中，选择 **指定现有的服务器** 选项。并输入**正在运行服务器的 URL** 并按下 `Enter` 进行连接。

   ![image-20221103140010689](https://mofish-1307188483.cos.ap-chengdu.myqcloud.com/202211031400792.png)

   ![image-20221103140154991](https://mofish-1307188483.cos.ap-chengdu.myqcloud.com/202211031401062.png)

### 开始创作！

选中 **Specify parameters** 代码块并点击左侧 **开始运行** 按钮。

![image-20221103140918633](https://mofish-1307188483.cos.ap-chengdu.myqcloud.com/202211031409729.png)

在下方的**单元格输出栏**中，可以预览当前图片的渲染进度。

![image-20221103141951893](https://mofish-1307188483.cos.ap-chengdu.myqcloud.com/202211031419992.png)

## 在 Jupyter NoteBook 上使用

> Jupyter Notebook 的详细操作请自行查阅文档，这里不再赘述。

### 在浏览器中访问 **Docker** 生成的链接

> 注意：每次重启 Docker 服务后，**Token**值都会改变。

![image-20221103162434874](https://mofish-1307188483.cos.ap-chengdu.myqcloud.com/202211031625252.png)

> 如果**笔记本列表中**没有 **discoart.ipynb** 文件，则需要自行上传

### 开始创作！

- 单击列表中的 **discoart.ipynb** 文件，会自动跳转至对应页面。

- 选中 **Specify parameters** 代码块并点击上方**运行**按钮。

![image-20221103163329763](https://mofish-1307188483.cos.ap-chengdu.myqcloud.com/202211031633858.png)

> **边框绿色**代表选中状态

##关于参数设置的更多细节

**关于全部参数更深入的解释请查看[这里]()，在那里你将看到更多的例子。**

# 资源链接

- 