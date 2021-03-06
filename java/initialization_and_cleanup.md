# Initialization and Cleanup
# Initialization and Cleanup

# 5. 初始化和清理

## 5.7 构造器初始化

### 5.7.1 初始化顺序

类内部变量定义的先后顺序决定了其初始化的顺序，并且会在任何方法（包括构造器，与顺序无关）被调用之前也会得到初始化。对于静态对象与非静态对象：先初始化静态对象，然后是非静态对象。

### 5.7.2 静态数据的初始化

静态数据只占用一份存储区域，static 关键字不能用于局部变量，因为它只能作用于域。如果一个域是静态的基本类型域且未对其初始化，那么它就会获得基本类型的标准初值；如果是一个对象引用，则初始化为 null.

静态初始化只有在必要时才会进行，且只被初始化一次，即如果不创建相应的对象或是引用相应的静态对象，那么则不会被初始化。

对象创建过程：

1. 构造器实际上也是静态方法。Java 解释器首先查找类路径定位相应 class 文件。
2. 载入 class 文件，执行静态初始化，静态初始化只在类对象首次加载的适合进行一次。
3. 使用 new 创建对象时首先将在堆上为对象分配足够的存储空间。
4. 存储空间清零，故其所有基本类型数据置为默认值。
5. 执行所有定义处的初始化动作。
6. 执行构造器。
