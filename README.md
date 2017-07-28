# Newlife

public class Newlife {
  public static void main(String[] args)
    {
        HelloWorld h = new HelloWorld();
        System.out.println("HelloWorld!");
        h.main(args);
    }
}

/****************************下面是注释*******************************/
运行结果为

    HelloWorld!

    HelloWorld!

    HelloWorld!

    ... ...
    HelloWorld!
    Exception in thread "main" java.lang.StackOverflowError
    at sun.nio.cs.ext.DoubleByteEncoder.encodeLoop(Unknown Source)
    at java.nio.charset.CharsetEncoder.encode(Unknown Source)
    at sun.nio.cs.StreamEncoder.implWrite(Unknown Source)
    at sun.nio.cs.StreamEncoder.write(Unknown Source)
    at java.io.OutputStreamWriter.write(Unknown Source)
    at java.io.BufferedWriter.flushBuffer(Unknown Source)
    at java.io.PrintStream.write(Unknown Source)
    at java.io.PrintStream.print(Unknown Source)
    at java.io.PrintStream.println(Unknown Source)
    at main.HelloWorld.main(HelloWorld.java:15)
    at main.HelloWorld.main(HelloWorld.java:16)
    at main.HelloWorld.main(HelloWorld.java:16)
    at main.HelloWorld.main(HelloWorld.java:16)
    ... ...

　　可见HelloWorld被玩坏了，这个无限递归创建对象的过程导致了内存溢出。
  
/*******************************************************************/
