# Java I/O 常见面试题

- NIO这个库是在JDK1.4中才引入的。NIO和IO有相同的作用和目的，但实现方式不同，NIO主要用到的是块，所以NIO的效率要比IO高很多。在Java API中提供了两套NIO，一套是针对标准输入输出NIO，另一套就是网络编程NIO。
- NIO中的N可以理解为Non-blocking，不单纯是New。

## 什么是IO流

    它是一种数据的流从源头流到目的地。比如文件拷贝，输入流和输出流都包括了。输入流从文件中读取数据存储到进程(process)中，输出流从进程中读取数据然后写入到目标文件。

## 字节流和字符流的区别

字节流在JDK1.0中就被引进了，用于操作包含ASCII字符的文件。JAVA也支持其他的字符如Unicode，为了读取包含Unicode字符的文件，JAVA语言设计者在JDK1.1中引入了字符流。ASCII作为Unicode的子集，对于英语字符的文件，可以可以使用字节流也可以使用字符流。

## Java中流类的超类主要由那些

- java.io.InputStream
- java.io.OutputStream
- java.io.Reader
- java.io.Writer

## FileInputStream和FileOutputStream是什么

这是在拷贝文件操作的时候，经常用到的两个类。在处理小文件的时候，它们性能表现还不错，在大文件的时候，最好使用BufferedInputStream (或 BufferedReader) 和 BufferedOutputStream (或 BufferedWriter)

## 字节流和字符流，你更喜欢使用哪一个

个人来说，更喜欢使用字符流，因为他们更新一些。许多在字符流中存在的特性，字节流中不存在。比如使用BufferedReader而不是BufferedInputStreams或DataInputStream，使用newLine()方法来读取下一行，但是在字节流中我们需要做额外的操作。

## 什么是Filter流

Filter Stream是一种IO流主要作用是用来对存在的流增加一些额外的功能，像给目标文件增加源文件中不存在的行数，或者增加拷贝的性能。

## 有哪些可用的Filter流

在java.io包中主要由4个可用的filter Stream。两个字节filter stream，两个字符filter stream. 分别是FilterInputStream, FilterOutputStream, FilterReader and FilterWriter.这些类是抽象类，不能被实例化的。

**有些Filter流的子类:**

- LineNumberInputStream 给目标文件增加行号
- DataInputStream 有些特殊的方法如readInt(), readDouble()和readLine() 等可以读取一个 int, double和一个string一次性的,
- BufferedInputStream 增加性能
- PushbackInputStream 推送要求的字节到系统中

## SequenceInputStream的作用

这个类的作用是将多个输入流合并成一个输入流，通过SequenceInputStream类包装后形成新的一个总的输入流。在拷贝多个文件到一个目标文件的时候是非常有用的。可用使用很少的代码实现

##  在文件拷贝的时候，那一种流可用提升更多的性能

在字节流的时候，使用BufferedInputStream和BufferedOutputStream。
在字符流的时候，使用BufferedReader 和 BufferedWriter

## 管道流(Piped Stream)

有四种管道流， PipedInputStream, PipedOutputStream, PipedReader 和 PipedWriter.在多个线程或进程中传递数据的时候管道流非常有用。


## RandomAccessFile

它在java.io包中是一个特殊的类，既不是输入流也不是输出流，它两者都可以做到。他是Object的直接子类。通常来说，一个流只有一个功能，要么读，要么写。但是RandomAccessFile既可以读文件，也可以写文件。 DataInputStream 和 DataOutStream有的方法，在RandomAccessFile中都存在。

## BIO NIO AIO

### 同步阻塞IO (BIO)

**用户进程发起一个IO操作以后，必须等待IO操作的真正完成后，才能继续运行；**

### 同步非阻塞IO（NIO）

**用户进程发起一个IO操作以后，可做其它事情，但用户进程需要经常询问IO操作是否完成，这样造成不必要的CPU资源浪费；**

### 异步非阻塞IO（AIO）

**用户进程发起一个IO操作然后，立即返回，等IO操作真正的完成以后，应用程序会得到IO操作完成的通知。类比Future模式。**

- **同步** ： 自己亲自出马持银行卡到银行取钱（使用同步IO时，Java自己处理IO读写）。
- **异步** ： 委托一小弟拿银行卡到银行取钱，然后给你（使用异步IO时，Java将IO读写委托给OS处理，需要将数据缓冲区地址和大小传给OS(银行卡和密码)，OS需要支持异步IO操作API）。
- **阻塞** ： ATM排队取款，你只能等待（使用阻塞IO时，Java调用会一直阻塞到读写完成才返回）。
- **非阻塞** ： 柜台取款，取个号，然后坐在椅子上做其它事，等号广播会通知你办理，没到号你就不能去，你可以不断问大堂经理排到了没有，大堂经理如果说还没到你就不能去（使用非阻塞IO时，如果不能读写Java调用会马上返回，当IO事件分发器会通知可读写时再继续进行读写，不断循环直到读写完成）。

</br>
<table>
<thead>
<tr><th style="padding: 8px; line-height: 20px; vertical-align: top; border-top-width: 0px">.</th><th style="padding: 8px; line-height: 20px; vertical-align: top; border-top-width: 0px">同步阻塞IO</th><th style="padding: 8px; line-height: 20px; vertical-align: top; border-top-width: 0px">伪异步IO</th><th style="padding: 8px; line-height: 20px; vertical-align: top; border-top-width: 0px">NIO</th><th style="padding: 8px; line-height: 20px; vertical-align: top; border-top-width: 0px">AIO</th></tr>
</thead>
<tbody>
<tr>
<td style="padding: 8px; line-height: 20px; vertical-align: top">客户端数目 ：IO线程</td>
<td style="padding: 8px; line-height: 20px; vertical-align: top">1 : 1</td>
<td style="padding: 8px; line-height: 20px; vertical-align: top">m : n</td>
<td style="padding: 8px; line-height: 20px; vertical-align: top">m : 1</td>
<td style="padding: 8px; line-height: 20px; vertical-align: top">m : 0</td>
</tr>
<tr>
<td style="padding: 8px; line-height: 20px; vertical-align: top">IO模型</td>
<td style="padding: 8px; line-height: 20px; vertical-align: top">同步阻塞IO</td>
<td style="padding: 8px; line-height: 20px; vertical-align: top">同步阻塞IO</td>
<td style="padding: 8px; line-height: 20px; vertical-align: top">同步非阻塞IO</td>
<td style="padding: 8px; line-height: 20px; vertical-align: top">异步非阻塞IO</td>
</tr>
<tr>
<td style="padding: 8px; line-height: 20px; vertical-align: top">吞吐量</td>
<td style="padding: 8px; line-height: 20px; vertical-align: top">低</td>
<td style="padding: 8px; line-height: 20px; vertical-align: top">中</td>
<td style="padding: 8px; line-height: 20px; vertical-align: top">高</td>
<td style="padding: 8px; line-height: 20px; vertical-align: top">高</td>
</tr>
<tr>
<td style="padding: 8px; line-height: 20px; vertical-align: top">编程复杂度</td>
<td style="padding: 8px; line-height: 20px; vertical-align: top">简单</td>
<td style="padding: 8px; line-height: 20px; vertical-align: top">简单</td>
<td style="padding: 8px; line-height: 20px; vertical-align: top">非常复杂</td>
<td style="padding: 8px; line-height: 20px; vertical-align: top">复杂</td>
</tr>
</tbody>
</table>

## 什么是Socket

Socket是进程通讯的一种方式，即调用这个网络库的一些API函数实现分布在不同主机的相关进程之间的数据交换。

socket是网络编程的基础，本文用打电话来类比socket通信中建立TCP连接的过程。

socket函数：表示你买了或者借了一部手机。 bind函数：告诉别人你的手机号码，让他们给你打电话。 listen函数：打开手机的铃声，而不是静音，这样有电话时可以立马反应。listen函数的第二个参数，最大连接数，表示最多有几个人可以同时拨打你的号码。不过我们的手机，最多只能有一个人打进来，要不然就提示占线。 connect函数：你的朋友知道了你的号码，通过这个号码来联系你。在他等待你回应的时候，不能做其他事情，所以connect函数是阻塞的。 accept函数：你听到了电话铃声，接电话，accept it！然后“喂”一声，你的朋友听到你的回应，知道电话已经打进去了。至此，一个TCP连接建立了。 read/write函数：连接建立后，TCP的两端可以互相收发消息，这时候的连接是全双工的。对应打电话中的电话煲。 close函数：通话完毕，一方说“我挂了”，另一方回应"你挂吧"，然后将连接终止。实际的close(sockfd)有些不同，它不止是终止连接，还把手机也归还，不在占有这部手机，就当是公用电话吧。

注意到，上述连接是阻塞的，你一次只能响应一个用户的连接请求，但在实际网络编程中，一个服务器服务于多个客户，上述方案也就行不通了，怎么办？想一想10086，移动的声讯服务台，也是只有一个号码，它怎么能同时服务那么多人呢？可以这样理解，在你打电话到10086时，总服务台会让一个接线员来为你服务，而它自己却继续监听有没有新的电话接入。在网络编程中，这个过程类似于fork一个子进程，建立实际的通信连接，而主进程继续监听。10086的接线员是有限的，所以当连接的人数达到上线时，它会放首歌给你听，忙等待，直到有新的空闲接线员为止。 实际网络编程中，处理并发的方式还有select/poll/epoll等。


## Socket的特点

- Socket基于TCP链接，数据传输有保障
- Socket适用于建立长时间链接
- Socket编程通常应用于即时通讯








