## 1. 使用模拟类

#### 1.1 添加并设置类属性的流程

![](index_files/d2512633-7aca-40a8-b21f-7267107df59b.jpg)

主要涉及：指定类的所属关系，选定类并设置其属性

#### 1.2 定位 objects tree

![](index_files/6de0ad84-0286-45d3-b124-9ec7141cca4a.jpg)

想要对某一个类属性进行更改，或者想要为某一个类添加类属性，需要先定位到该类，思路跟MATLAB是一样的。一般生成的新类，其从属于 model 分析组。如果想将某类添加到制定的 group 中，需要使用 addtogroup 之类的函数。

改变 groupscope 的方法如下：

![](index_files/d695ab4e-f2f8-435b-b166-48aae5bf6812.jpg)

#### 1.3 添加类

![](index_files/b481f5e8-b483-4396-a74f-1410c2f45fc4.jpg)

#### 1.4 选择类

![](index_files/3a441166-3a7e-4da4-9975-7b9f8ed43c22.jpg)

#### 1.5 设置类属性

![](index_files/cbc46cc7-4960-46a5-ac83-fe63a169bb61.jpg)

## 2. 参数化扫描

#### 2.1 通过 for 循环加 run 进行参数化扫描

设置好模型后（无论是通过手动设置，还是通过code设置），点击工具栏的`run`按钮，或者在命令行窗口输入 `run`，都可以启动运行。运行之后，系统处于分析状态。此时多数类的属性无法设置，如需设置属性，则需要将状态切回layout状态：

![](index_files/95c9fabb-d5dc-46ae-9022-45ded47a832c.jpg)

下图是一个通过script进行参数化扫描的案例：

![](index_files/a14aeac3-429c-4d8f-a256-ae60ae2a92c3.jpg)

可见，为了更改参数设置，需要切回layout状态。

#### 2.3 通过 job manager（进行参数化扫描作业管理器）进行参数化扫描

job manager 可以同时运行多个添加的文件。添加文件的方法是 addjob 函数。通过 clearjobs 可以将序列中所有的 jobs 都清除掉，而 runjobs 则可以运行序列中的所有 jobs。下面演示通过 job manager 的方法进行参数化扫描：

![](index_files/243a337e-6960-4649-831e-db9de00ab08d.jpg)

其结果与前面通过 for 循环依次运行的参数化扫描操作是一样的。

#### 2.4 通过runsweep进行参数化扫描

runsweep 函数运行所有的任务，而 runsweep('taskname') 则运行指定的任务。没太听懂这个。

## 3. 访问运行结果并可视化

#### 3.1 访问运行结果

- getdate 和 getresult

![](index_files/7d7f581b-061e-42c0-bdfc-94ce56522759.jpg)

![](index_files/46445f7e-faa2-4ef9-8016-1187dabaa3bd.jpg)

- 特殊命令

![](index_files/91ef6437-5d4e-4fae-b942-69e093dbc104.jpg)

需要注意的是，透射方向为x、y、z正方向时，透射率为正，反之为负。

- 获得优化和参数扫描的结果

此时使用 getsweepdata 和 getsweepresult 两个命令，具体操作如上。需要注意的是，这两个命令具体能访问哪些参数，可以通过在命令前面加一个 ？ 来询问。

![](index_files/fb798d7a-9e10-4835-ad3e-01cfe79fa68f.jpg)

#### 3.2 可视化

- plot

![](index_files/0a919dbd-cdfe-422b-9cc3-a706b14c1bdc.jpg)

- plotxy

![](index_files/dd56b377-0195-4181-bcf4-c382f9365c60.jpg)

- polar

![](index_files/a3475614-f5a0-4124-88c9-c9f2cf5b14b2.jpg)

- polar2

![](index_files/fb0a0262-8ef0-4595-8487-53e55ea9ce98.jpg)

- image

![](index_files/31c5fe87-d177-491f-aa21-f04b9f7b338b.jpg)

- polarimage

![](index_files/1c7e26cd-a59a-4d21-b669-10544f18cfc6.jpg)

- plot options 

![](index_files/368e5e1e-9019-42fd-b55a-8160537ef58b.jpg)

- setplot

![](index_files/02324e6f-4a08-4a79-8f76-095073643b3b.jpg)

- 其他命令

![](index_files/336c9f8a-227d-4423-b45a-36ca61f83568.jpg)

## 4. 新建和保存文件

#### 4.1 创建和保存文件

- 新建文件：

使用 newproject 或者 newproject(option)，第二种方法是基于某一存在的模板创建一个新文件，而第一个则是创建一个全新文件。

- 保存文件

使用 save 和 save(filename) 保存文件，若不指明保存文件名和文件目录，则在此文件夹下保存此文件，一如 MATLAB。

- 加载文件

使用 load 函数加载文件，如 MATLAB。

#### 4.2 文本文件

使用 write 函数新建一个记事本并向其中写入文本。使用 num2str 函数将数字转换成字符格式。使用 readdate 函数从一个文本中读入文本内容。

#### 4.3 保存工作区的数据

- 保存为 .ldf 格式的数据

使用 savedata(filename) 保存工作区中所有数据，使用 savedata(filename, var1, var2, ...) 保存工作区部分数据。使用 loaddate(filename) 加载保存的数据。

- 保存为 .mat 格式的数据

方法如前，只不过函数使用 matlabsave 和 matlabload。





