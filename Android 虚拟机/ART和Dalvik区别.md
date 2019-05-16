#### ART和Dalvik区别

##### 参考答案

什么是Dalvik：
Dalvik是Google公司自己设计用于Android平台的Java虚拟机。
它可以支持已转换为.dex(即Dalvik Executable)格式的Java应用程序的运行。
.dex格式是专为Dalvik应用设计的一种压缩格式，适合内存和处理器速度有限的系统。
Dalvik经过优化，允许在有限的内存中同时运行多个虚拟机的实例，并且每一个Dalvik应用作为独立的Linux进程执行。
独立的进程可以防止在虚拟机崩溃的时候所有程序都被关闭。

什么是ART：
与Dalvik不同，ART使用预编译（AOT,Ahead-Of-Time）。
也就是在APK运行之前，就对其包含的Dex字节码进行翻译，得到对应的本地机器指令，于是就可以在运行时直接执行了。
ART应用安装的时候把dex中的字节码将被编译成本地机器码，之后每次打开应用，执行的都是本地机器码。
去除了运行时的解释执行，效率更高，启动更快。

区别:

1. Dalvik每次都要编译再运行，Art只会首次启动编译
2. Art占用空间比Dalvik大（原生代码占用的存储空间更大），就是用“空间换时间”
3. Art减少编译，减少了CPU使用频率，使用明显改善电池续航
4. Art应用启动更快、运行更快、体验更流畅、触感反馈更及时

参考官方文档:
<https://source.android.com/devices/tech/dalvik/index.html>