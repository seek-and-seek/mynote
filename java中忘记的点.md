在 Java 中，**一个 `.java` 文件里只能有一个 `public` 类**，主要是因为 **Java 的文件名与公共类名的强制对应规则**。

线程的创建在Thread中  runnable中只有逻辑

~~~java
T1 t1  = new T1()
    new Thread(t1).start();
~~~

~~~java
package synchronizd;
/**
 * @author 田建硕
 * @version 1.0
 */
public class syn {
    public static void main(String[] args) {

        T1 t1  = new T1();
        T1 t2  = new T1();
        T1 t3  = new T1();
        t1.start();
        t2.start();
        t3.start();
    }
}
class T1 extends Thread{
    public static int ticknum = 100;
    public static synchronized void sell(){
        if(ticknum<=0){
            return;
        }
        try {
            Thread.sleep(50);
        } catch (InterruptedException e) {
            throw new RuntimeException(e);
        }
        System.out.println(Thread.currentThread().getName()+"卖出了一张票，剩余的票数为"+(--ticknum));
    }
    @Override
    public  void run() {  //同步方法，在同一时刻，只能有一个线程
        while(true){
            if(ticknum<=0){
                break;
            }
            sell();
        }
    }
}

~~~

太神奇了

~~~JAVA
//直接将方法变为同步的方法 在调用同步方法时只能一个一个的调用，一个一个的判断当前票数即可结束循环
注意的点：继承Thread为了它是一个方法，方法是静态的，runnable 本来就一个。
~~~

