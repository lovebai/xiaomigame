## i7-8750h Sur Big专用，需解锁cfg

### 当前已知的问题
* 有线网络不可用

### 默认跑马模式后期自行修改


### 修改BIOS教程     

#### 我对你的笔记本电脑可能发生的事情不负责任  

- OpenCore引导启动
- 点击键盘上的空格键。
- 选择partition Mod Grub Shell
- 编写一个命令方法，例如解锁cfg lock:setup_var 0x3C 0x00
- 其他示例，要启用的SpeedShift:setup_var 0xB 0x01

### 说明:  
setup_var 是调用方法函数 
0x3C 是bios上可变CFG 锁的内存位置    
0x00 是关闭 0x01 是打开. 
(default) is how the variable is when you install a BIOS, that is, by the manufacturer.  

One Of: CFG Lock, VarStoreInfo (VarOffset/VarName): 0x3C, VarStore: 0x3, QuestionId: 0x146, Size: 1, Min:   0x0, Max 0x1, Step: 0x0 {05 91 8A 02 8B 02 46 01 03 00 3C 00 10 10 00 01 00}  
0x149413 			One Of Option: Disabled, Value (8 bit): 0x0 {09 07 04 00 00 00 00}  
0x14941A 			One Of Option: Enabled, Value (8 bit): 0x1 (default) {09 07 03 00 30 00 01}  
0x149421 		End One Of {29 02}  

5- 你可以设置更多的变量来修改Bios。如果你想退出，你必须写重新启动并点击键盘上的回车键。 

6- 你可以验证CFG是否已解锁，在hackintool、section Utilities中启用了SpeedShift等其他参数，然后点击Get appleintelinfo即可

