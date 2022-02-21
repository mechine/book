# 注解

Annontation是Java5开始引入的新特征，中文名称叫注解。它提供了一种安全的类似注释的机制，用来将任何的信息或元数据（metadata）与程序元素（类、方法、成员变量等）进行关联。为程序的元素（类、方法、成员变量）加上更直观更明了的说明，这些说明信息是与程序的业务逻辑无关，并且供指定的工具或框架使用。Annontation像一种修饰符一样，应用于包、类型、构造方法、方法、成员变量、参数及本地变量的声明语句中。 Java注解是附加在代码中的一些元信息，用于一些工具在编译、运行时进行解析和使用，起到说明、配置的功能。注解不会也不能影响代码的实际逻辑，仅仅起到辅助性的作用。包含在 java.lang.annotation 包中。 注解的作用： 1、生成文档。这是最常见的，也是java 最早提供的注解。常用的有@param @return 等 2、跟踪代码依赖性，实现替代配置文件功能。比如Dagger 2依赖注入，未来java开发，将大量注解配置，具有很大用处; SPRING IOC 中，可以用来检索所有 标注了某个注解的bean ； spring aop 中可以用来做point cut 识别 3、在编译时进行格式检查。如@override 放在方法前，如果你这个方法并不是覆盖了超类方法，则编译时就能检查出。 注解的原理： 注解本质是一个继承了Annotation的特殊接口，其具体实现类是Java运行时生成的动态代理类。而我们通过反射获取注解时，返回的是Java运行时生成的动态代理对象$Proxy1。通过代理对象调用自定义注解（接口）的方法，会最终调用AnnotationInvocationHandler的invoke方法。该方法会从memberValues这个Map中索引出对应的值。而memberValues的来源是Java常量池。 元注解： java.lang.annotation提供了四种元注解，专门注解其他的注解（在自定义注解的时候，需要使用到元注解）： @Documented –注解是否将包含在JavaDoc中 @Retention –什么时候使用该注解 @Target –注解用于什么地方 @Inherited – 是否允许子类继承该注解

1.）@Retention– 定义该注解的生命周期&#x20;

● RetentionPolicy.SOURCE : 在编译阶段丢弃。这些注解在编译结束之后就不再有任何意义，所以它们不会写入字节码。@Override, @SuppressWarnings都属于这类注解。&#x20;

● RetentionPolicy.CLASS : 在类加载的时候丢弃。在字节码文件的处理中有用。注解默认使用这种方式 ● RetentionPolicy.RUNTIME : 始终不会丢弃，运行期也保留该注解，因此可以使用反射机制读取该注解的信息。我们自定义的注解通常使用这种方式。

2.）Target – 表示该注解用于什么地方。默认值为任何元素，表示该注解用于什么地方。可用的ElementType参数包括&#x20;

● ElementType.CONSTRUCTOR:用于描述构造器&#x20;

● ElementType.FIELD:成员变量、对象、属性（包括enum实例）

&#x20;● ElementType.LOCAL\_VARIABLE:用于描述局部变量&#x20;

● ElementType.METHOD:用于描述方法&#x20;

● ElementType.PACKAGE:用于描述包&#x20;

● ElementType.PARAMETER:用于描述参数&#x20;

● ElementType.TYPE:用于描述类、接口(包括注解类型) 或enum声明

3.)@Documented–一个简单的Annotations标记注解，表示是否将注解信息添加在java文档中。

4.)@Inherited – 定义该注释和子类的关系 @Inherited 元注解是一个标记注解，@Inherited阐述了某个被标注的类型是被继承的。如果一个使用了@Inherited修饰的annotation类型被用于一个class，则这个annotation将被用于该class的子类。 自定义注解类编写的一些规则:

1. Annotation型定义为@interface, 所有的Annotation会自动继承java.lang.Annotation这一接口,并且不能再去继承别的类或是接口.
2. 参数成员只能用public或默认(default)这两个访问权修饰
3. 参数成员只能用基本类型byte,short,char,int,long,float,double,boolean八种基本数据类型和String、Enum、Class、annotations等数据类型,以及这一些类型的数组.
4. 要获取类方法和字段的注解信息，必须通过Java的反射技术来获取 Annotation对象,因为你除此之外没有别的获取注解对象的方法
5. 注解也可以没有定义成员, 不过这样注解就没啥用了

@Target(ElementType.FIELD) // 注解用于字段上 @Retention(RetentionPolicy.RUNTIME) // 保留到运行时，可通过注解获取 public @interface MyField { String description(); int length(); }
