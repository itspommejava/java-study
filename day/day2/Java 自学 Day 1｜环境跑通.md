
**记录：Java自学日记 Day 1 ｜安装与配置 JDK 的完整过程**

---

## 🧩 01｜最初的问题

在命令行输入：

```bash
javac -version
````

结果没有任何输出，Notepad++ 也无法生成 `.class` 文件。

> 这说明系统找不到 `javac`（Java Compiler 编译器）。
> 要么没有安装 JDK，要么环境变量没有配置。

---

## 🔍 02｜检查是否安装 JDK

检查目录：

```
C:\Program Files\
C:\Program Files (x86)\
```

没有任何 Java 相关文件夹。

**结论：电脑中没有安装 JDK。**

---

## 🌟 03｜下载并安装 JDK 17

到 Oracle 官方搜索：

```
Oracle JDK 17 download
```

选择：

* Windows x64 Installer（安装版）
* 安装路径保持默认（最稳定）：

```
C:\Program Files\Java\jdk-17
```

安装完成后，可看到如下结构：

```
jdk-17/
│
├── bin/
├── conf/
├── lib/
└── ...
```

其中 `bin` 目录包含 `java.exe` 和 `javac.exe`。

---

## ⚙️ 04｜配置环境变量（Environment Variables 环境变量）

### ① 新建系统变量：JAVA_HOME

```
变量名：JAVA_HOME
变量值：C:\Program Files\Java\jdk-17
```

### ② 编辑系统变量 Path

新增：

```
%JAVA_HOME%\bin
```

保存后关闭所有 CMD 窗口。

---

## 🔁 05｜验证环境是否成功

在新的 CMD 输入：

```bash
java -version
javac -version
```

预期输出：

```
java version "17.0.12"
javac 17.0.12
```

表示 JDK 和环境变量均已生效。

---

## 🚀 06｜第一次成功编译 Java 程序

新建文件：`HelloWorld.java`：

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello World");
    }
}
```

编译：

```bash
javac HelloWorld.java
```

运行：

```bash
java HelloWorld
```

输出：

```
Hello World
```

这是我第一次成功运行的 Java 程序。

---

## 🧩 07｜常见问题排查（可折叠）

<details>
<summary>点我展开</summary>

### ❗ javac 显示“不是内部或外部命令”

检查：

1. `JAVA_HOME` 是否指向 jdk-17
2. `Path` 是否添加 `%JAVA_HOME%\bin`
3. 是否重新打开了 CMD
4. 必要时重启系统

### ❗ 系统中存在旧版本 Java

删除 Path 中旧版本的 `Java\bin` 路径，只保留：

```
%JAVA_HOME%\bin
```

</details>

---

## ✨ 08｜写在最后

这次配置 JDK，让我理解了：

* JDK 是一整套开发工具
* 环境变量是系统的“指路标志”
* 遇到问题要从“有没有安装 → 系统能不能找到”两层排查

一个记录自学路的普通人。慢慢来，每天一点点，把坚持写成故事

<small style="color:#9aa0a6;">
写在夜色里，也写给未来的自己。
</small>


