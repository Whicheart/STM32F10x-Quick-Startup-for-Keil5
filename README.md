# STM32F10x-Quick-Startup
Used to quickly create STM32F10x projects in Keil5

---

[中文](#中文指南) | [English](#english-guide)

---

<a id="english-guide"></a>
# Quick Start Guide for STM32F10x Project (Keil5)

## Instructions

### Step 1: File Preparation
After downloading this project, place the three folders `Library`, `Startup`, `System`, and `User` into your project's root directory. The directory structure should look like this:

- Project Root/
  - Library/
  - Startup/
  - System/
  - User/


### Step 2: Keil Project Configuration
1. In the **Project** window on the left side of Keil5, right-click on `Target 1`
2. Create three new groups named `Library`, `Startup`, `System`, and `User`
3. Right-click on each newly created group and select the **Add Existing Files to Group...** option
4. Add all files from the corresponding physical directories to their respective groups

### Step 3: Target Options Setting
Click the magic wand icon (**Options for Target...**) and configure the following settings:

1. Select the `C/C++` tab:
   - In the `Define` field, add: `USE_STDPERIPH_DRIVER`
2. Still in the `C/C++` tab:
   - Click the button at the end of the `Include Paths` field and add the following paths:
     - `.\Startup`
     - `.\Startup\Core`
     - `.\Library`
     - `.\System`
     - `.\User`

### Step 4: Build Verification
Click the **Build** (F7) button to compile the project. If everything is configured correctly, the output window should display: `0 Error(s), 0 Warning(s)`

### Step 5: Start Development
Your project environment is now set up. You can begin your application development.

---

<a id="中文指南"></a>
# STM32F10x 项目快速构建指南 (Keil5)

## 方法步骤

### 一、文件准备
下载本项目后，将 `Library`、`Startup`、`User`、`System` 三个文件夹放置到您的项目根目录下。目录结构应如下所示：

- 项目根目录/
  - Library/
  - Startup/
  - System/
  - User/

### 二、Keil 工程配置
1. 在 Keil5 左侧的 **Project** 窗口中，右键单击 `Target 1`
2. 新建三个分组（Group），分别命名为 `Library`、`Startup`、`User`、`System`
3. 右键单击每个新建的分组，选择 **Add Existing Files to Group...** 选项
4. 根据你所使用的具体芯片型号，选用Startup文件中不同的`startup_stm32f10x_xx.s`文件，例如最常见的`stm32f103c8t6`芯片应选用`startup_stm32f10x_md.s`文件
5. 将对应物理目录中的其余全部文件添加到相应的分组中

### 三、目标选项设置
点击魔法棒图标（**Options for Target...**），进行以下设置：

1. 选择 `C/C++` 选项卡：
   - 在 `Define` 输入框中添加：`USE_STDPERIPH_DRIVER`
2. 仍在 `C/C++` 选项卡：
   - 点击 `Include Paths` 输入框末尾的按钮，添加以下路径：
     - `.\Startup`
     - `.\Startup\Core`
     - `.\Library`
     - `.\System`
     - `.\User`

### 四、编译验证
点击 **Build** (F7) 按钮编译项目。如果一切配置正确，输出窗口应显示：`0 Error(s), 0 Warning(s)`

### 五、开始开发
至此，项目环境已搭建完成，您可以开始进行您的应用程序开发。
