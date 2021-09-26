<a name="index">**Index**</a>
<a href="#0">C++ 类 & 对象</a>  
&emsp;&emsp;<a href="#1">一、C++类的定义</a>  
&emsp;&emsp;<a href="#2">二、C++定义对象（类似于python中的类的实例化）</a>  
&emsp;&emsp;&emsp;<a href="#3">访问数据成员</a>  
&emsp;&emsp;<a href="#4">三、类 & 对象详解</a>  
&emsp;&emsp;&emsp;<a href="#5">1、类的成员函数</a>  
&emsp;&emsp;&emsp;<a href="#6">2、类访问修饰符</a>  
&emsp;&emsp;&emsp;<a href="#7"># 3、构造函数与析构函数</a>  
&emsp;&emsp;&emsp;<a href="#8"># 3、C++拷贝构造函数</a>  
&emsp;&emsp;&emsp;<a href="#9"># 4、C++友元函数(相当于给开后门，给某些函数特定权利可以访问私有资源)</a>  
&emsp;&emsp;&emsp;<a href="#10"># 5、内联函数</a>  
&emsp;&emsp;&emsp;<a href="#11"># 6、C++ this指针</a>  
&emsp;&emsp;&emsp;<a href="#12"># 7、指向类的指针</a>  
&emsp;&emsp;&emsp;<a href="#13"># 8、C++类的静态成员</a>  
&emsp;&emsp;&emsp;<a href="#14"># 9、静态函数成员</a>  
&emsp;&emsp;<a href="#15">四、C++继承</a>  
&emsp;&emsp;&emsp;<a href="#16">1、基类&派生类</a>  
&emsp;&emsp;&emsp;<a href="#17">2、访问控制和继承</a>  
&emsp;&emsp;&emsp;<a href="#18">3、多继承</a>  
&emsp;&emsp;<a href="#19">五、C++重载运算符和重载函数</a>  
&emsp;&emsp;&emsp;<a href="#20">1、函数的重载</a>  
&emsp;&emsp;&emsp;<a href="#21">2、运算符重载</a>  
&emsp;&emsp;<a href="#22">六、重载运算符实例</a>  
&emsp;&emsp;&emsp;<a href="#23">**1、一元运算符重载**（也就是只有一个数字参与运算的情况）</a>  
&emsp;&emsp;&emsp;<a href="#24">2、二元运算符重载</a>  
&emsp;&emsp;&emsp;<a href="#25">3、关系运算符重载</a>  
&emsp;&emsp;&emsp;<a href="#26">4、输入/输出运算符重载</a>  
&emsp;&emsp;&emsp;<a href="#27">4、赋值运算符重载</a>  
&emsp;&emsp;&emsp;<a href="#28">5、函数调用运算符 () 重载</a>  
&emsp;&emsp;<a href="#29">七、C++类的多态</a>  
# <a name="0">C++ 类 & 对象</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

C++ 在 C 语言的基础上增加了面向对象编程，C++ 支持面向对象程序设计。类是 C++ 的核心特性，通常被称为用户定义的类型。

类用于指定对象的形式，它包含了数据表示法和用于处理数据的方法。类中的数据和方法称为类的成员。函数在一个类被称为类的成员。

### <a name="1">一、C++类的定义</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

类定义是以关键字 **class** 开头，后跟类的名称。类的主体是包含在一对花括号中。类定义后必须跟着一个分号或一个声明列表。例如，我们使用关键字 **class** 定义 Box 数据类型，如下所示：

```C++
class Box
{
   public:
      double length;   // Length of a box
      double breadth;  // Breadth of a box
      double height;   // Height of a box
};
```

关键字 **public** 确定了类成员的访问属性。在类对象作用域内，公共成员在类的外部是可访问的。您也可以指定类的成员为 **private** 或 **protected**，这个后面会展开介绍。

### <a name="2">二、C++定义对象（类似于python中的类的实例化）</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

类提供了对象的蓝图，所以基本上，对象是根据类来创建的。声明类的对象，就像声明基本类型的变量一样。下面的语句声明了类 Box 的两个对象：

```C++
Box Box1;          // 声明 Box1，类型为 Box
Box Box2;          // 声明 Box2，类型为 Box
```

Box1和Box2都有属于他们各自的数据成员

#### <a name="3">访问数据成员</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

类的对象的公共数据成员可以使用**直接成员访问运算符 (.)** 来访问。为了更好地理解这些概念，让我们尝试一下下面的实例：

```C++
#include <iostream>

using namespace std;

class Box
{
   public:
      double length;   // 长度
      double breadth;  // 宽度
      double height;   // 高度
};

int main( )
{
   Box Box1;        // 声明 Box1，类型为 Box
   Box Box2;        // 声明 Box2，类型为 Box
   double volume = 0.0;     // 用于存储体积
 
   // box 1 详述
   Box1.height = 5.0; 
   Box1.length = 6.0; 
   Box1.breadth = 7.0;

   // box 2 详述
   Box2.height = 10.0;
   Box2.length = 12.0;
   Box2.breadth = 13.0;

   // box 1 的体积
   volume = Box1.height * Box1.length * Box1.breadth;
   cout << "Box1 的体积：" << volume <<endl;

   // box 2 的体积
   volume = Box2.height * Box2.length * Box2.breadth;
   cout << "Box2 的体积：" << volume <<endl;
   return 0;
}
```

**需要注意的是，私有的成员和受保护的成员不能使用直接成员访问运算符 (.) 来直接访问。**

### <a name="4">三、类 & 对象详解</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

到目前为止，我们已经对 C++ 的类和对象有了基本的了解。下面的列表中还列出了其他一些 C++ 类和对象相关的概念，可以点击相应的链接进行学习。

| 概念                                                         | 描述                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [类成员函数](https://www.w3cschool.cn/cpp/cpp-class-member-functions.html) | 类的成员函数是指那些把定义和原型写在类定义内部的函数，就像类定义中的其他变量一样。 |
| [类访问修饰符](https://www.w3cschool.cn/cpp/cpp-class-access-modifiers.html) | 类成员可以被定义为 public、private 或 protected。默认情况下是定义为 private。 |
| [构造函数 & 析构函数](https://www.w3cschool.cn/cpp/cpp-constructor-destructor.html) | 类的构造函数是一种特殊的函数，在创建一个新的对象时调用。类的析构函数也是一种特殊的函数，在删除所创建的对象时调用。 |
| [C++ 拷贝构造函数](https://www.w3cschool.cn/cpp/cpp-copy-constructor.html) | 拷贝构造函数，是一种特殊的构造函数，它在创建对象时，是使用同一类中之前创建的对象来初始化新创建的对象。 |
| [C++ 友元函数](https://www.w3cschool.cn/cpp/cpp-friend-functions.html) | **友元函数**可以访问类的 private 和 protected 成员。         |
| [C++ 内联函数](https://www.w3cschool.cn/cpp/cpp-inline-functions.html) | 通过内联函数，编译器试图在调用函数的地方扩展函数体中的代码。 |
| [C++ 中的 this 指针](https://www.w3cschool.cn/cpp/cpp-this-pointer.html) | 每个对象都有一个特殊的指针 **this**，它指向对象本身。        |
| [C++ 中指向类的指针](https://www.w3cschool.cn/cpp/cpp-pointer-to-class.html) | 指向类的指针方式如同指向结构的指针。实际上，类可以看成是一个带有函数的结构。 |
| [C++ 类的静态成员](https://www.w3cschool.cn/cpp/cpp-static-members.html) | 类的数据成员和函数成员都可以被声明为静态的。                 |

#### <a name="5">1、类的成员函数</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

​	类的成员函数是指那些把定义和原型写在类定义内部的函数，就像类定义中的其他变量一样。类成员函数是类的一个成员，它可以操作类的任意对象，可以访问对象中的所有成员。

**类的成员函数有两种定义方式：**

- 直接在定义类的时候在类的内部定义

  ```C++
  class Box
  {
     public:
        double length;      // 长度
        double breadth;     // 宽度
        double height;      // 高度
     
        double getVolume(void)
        {
           return length * breadth * height;
        }
  };
  ```

- 此外，成员函数也可以在类的外部定义，此时需要在定义类的时候在类的内部首先对函数进行声明，然后再用**::**（**范围解析运算符**）来定义，

  ```C++
  class Box
  {
     public:
        double length;         // 长度
        double breadth;        // 宽度
        double height;         // 高度
        double getVolume(void);// 返回体积
  };
  double Box::getVolume(void)
  {
  	return length *breadth*height;
  }
  ```

> 这里需要强调的是，范围解析运算符（::）需要跟在类名的后面
>
> 而点运算符（.）则需要跟在对象名称后面

```C++
Box myBox;          // 创建一个对象

myBox.getVolume();  // 调用该对象的成员函数
```

一个例子🌰：

```C++
#include <iostream>

using namespace std;

class Box
{
   public:
      double length;         // 长度
      double breadth;        // 宽度
      double height;         // 高度

      // 成员函数声明
      double getVolume(void);
      void setLength( double len );
      void setBreadth( double bre );
      void setHeight( double hei );
};

// 成员函数定义
double Box::getVolume(void)
{
    return length * breadth * height;
}

void Box::setLength( double len )
{
    length = len;
}

void Box::setBreadth( double bre )
{
    breadth = bre;
}

void Box::setHeight( double hei )
{
    height = hei;
}

// 程序的主函数
int main( )
{
   Box Box1;                // 声明 Box1，类型为 Box
   Box Box2;                // 声明 Box2，类型为 Box
   double volume = 0.0;     // 用于存储体积
 
   // box 1 详述
   Box1.setLength(6.0); 
   Box1.setBreadth(7.0); 
   Box1.setHeight(5.0);

   // box 2 详述
   Box2.setLength(12.0); 
   Box2.setBreadth(13.0); 
   Box2.setHeight(10.0);

   // box 1 的体积
   volume = Box1.getVolume();
   cout << "Box1 的体积：" << volume <<endl;

   // box 2 的体积
   volume = Box2.getVolume();
   cout << "Box2 的体积：" << volume <<endl;
   return 0;
}
```

#### <a name="6">2、类访问修饰符</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

​	数据隐藏是面向对象编程的一个重要特点，它防止函数直接访问类类型的内部成员。类成员的访问限制是通过在类主体内部对各个区域标记 **public、private、protected** 来指定的。关键字 public、private、protected 称为访问说明符。

一个类可以有多个 public、protected 或 private 标记区域。**每个标记区域在下一个标记区域开始之前或者在遇到类主体结束右括号之前都是有效的**。**成员和类的默认访问修饰符是 private。**

```C++
class Base{
	public:
	//public members go here
	
	protected:
	//protected members go here
	
	private:
	//private members go here
};
```

- 公有（public）成员

  **公有成员**是在程序中类的外部是可访问的。您可以不使用任何成员函数来设置和获取公有变量的值，如下所示：

  ```C++
  #include <iostream>
   
  using namespace std;
   
  class Line
  {
     public:
        double length;
        void setLength( double len );
        double getLength( void );
  };
   
  // 成员函数定义
  double Line::getLength(void)
  {
      return length ;
  }
   
  void Line::setLength( double len )
  {
      length = len;
  }
   
  // 程序的主函数
  int main( )
  {
     Line line;
   
     // 设置长度
     line.setLength(6.0); 
     cout << "Length of line : " << line.getLength() <<endl;
   
     // 不使用成员函数设置长度⭐️
     line.length = 10.0; // OK: 因为 length 是公有的
     cout << "Length of line : " << line.length <<endl;
     return 0;
  }
  //运行结果
  Length of line : 6
  Length of line : 10
  ```

- 私有（private)成员

  **私有**成员变量或函数在类的外部是不可访问的，甚至是不可查看的。**只有类和友元函数可以访问私有成员。**

  默认情况下，类的所有成员都是私有的。例如在下面的类中，**width** 是一个私有成员，这意味着，如果您没有使用任何访问修饰符，类的成员将被假定为私有成员：

  一个例子🌰：	

  ```C++
  class Box
  {
   double width;
   public:
      double length;
      void setWidth( double wid );
      double getWidth( void );
  };
  ```

  实际操作中，我们一般会在私有区域定义数据，然后在公有区域定义相关函数，以便类可以在外部调用这些函数用来获取以及修改类的私有变量及函数。

  ```C++
  #include <iostream>
   
  using namespace std;
   
  class Box
  {
     public:
        double length;
        void setWidth( double wid );
        double getWidth( void );
   
     private:
        double width;
  };
   
  // 成员函数定义
  double Box::getWidth(void)
  {
      return width ;
  }
   
  void Box::setWidth( double wid )
  {
      width = wid;
  }
   
  // 程序的主函数
  int main( )
  {
     Box box;
   
     // 不使用成员函数设置长度
     box.length = 10.0; // OK: 因为 length 是公有的
     cout << "Length of box : " << box.length <<endl;
   
     // 不使用成员函数设置宽度
     // box.width = 10.0; // Error: 因为 width 是私有的
     box.setWidth(10.0);  // 使用成员函数设置宽度
     cout << "Width of box : " << box.getWidth() <<endl;
   
     return 0;
  }
  ```

- 保护（protected）成员

  保护成员变量与私有成员很相似，但有一点不同的是，保护成员的参数可以通过类的派生类（子类）访问，而私有成员的则不可以。

  ```C++
  #include <iostream>
  using namespace std;
   
  class Box
  {
     protected:
        double width;
  };
   
  class SmallBox:Box // SmallBox 是派生类
  {
     public:
        void setSmallWidth( double wid );
        double getSmallWidth( void );
  };
   
  // 子类的成员函数
  double SmallBox::getSmallWidth(void)
  {
      return width ;
  }
   
  void SmallBox::setSmallWidth( double wid )
  {
      width = wid;
  }
   
  // 程序的主函数
  int main( )
  {
     SmallBox box;
   
     // 使用成员函数设置宽度
     box.setSmallWidth(5.0);
     cout << "Width of box : "<< box.getSmallWidth() << endl;
   
     return 0;
  }
  ```

  #### <a name="7">3、构造函数与析构函数</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

  **类的构造函数：**类的**构造函数**是类的一种特殊的成员函数，它会在每次创建类的新对象时执行。构造函数的名称与类的名称是完全相同的，并且不会返回任何类型，也不会返回 void。构造函数可用于为某些成员变量设置初始值。✅（在这里可以类比与python中的init函数

  ```C++
  #include <iostream>
   
  using namespace std;
   
  class Line
  {
     public:
        void setLength( double len );
        double getLength( void );
        Line();  // 这是构造函数
   
     private:
        double length;
  };
   
  // 成员函数定义，包括构造函数
  Line::Line(void)
  {
      cout << "Object is being created" << endl;
  }
   
  void Line::setLength( double len )
  {
      length = len;
  }
   
  double Line::getLength( void )
  {
      return length;
  }
  // 程序的主函数
  int main( )
  {
     Line line;
   
     // 设置长度
     line.setLength(6.0); 
     cout << "Length of line : " << line.getLength() <<endl;
   
     return 0;
  }
  //输出结果
  Object is being created
  Length of line : 6
  ```

  **带有参数的构造参数：**默认的构造函数没有任何参数，但如果需要，构造函数也可以带有参数。这样在创建对象时就会给对象赋初始值，如下面的例子所示:（✅：就可以当成带有参数的init函数，在初始化的时候需要带参数使用）

  ```C++
  #include <iostream>
   
  using namespace std;
   
  class Line
  {
     public:
        void setLength( double len );
        double getLength( void );
        Line(double len);  // 这是构造函数
   
     private:
        double length;
  };
   
  // 成员函数定义，包括构造函数
  Line::Line( double len)
  {
      cout << "Object is being created, length = " << len << endl;
      length = len;
  }
   
  void Line::setLength( double len )
  {
      length = len;
  }
   
  double Line::getLength( void )
  {
      return length;
  }
  // 程序的主函数
  int main( )
  {
     Line line(10.0);
   
     // 获取默认设置的长度
     cout << "Length of line : " << line.getLength() <<endl;
     // 再次设置长度
     line.setLength(6.0); 
     cout << "Length of line : " << line.getLength() <<endl;
   
     return 0;
  }
  
  ```

  **使用初始化列表来初始化字段**

  假设有一个类 C，具有多个字段 X、Y、Z 等需要进行初始化，同理地，您可以使用上面的语法，只需要在不同的字段使用逗号进行分隔，如下所示：

  ```C++
  C::C( double a, double b, double c): X(a), Y(b), Z(c)
  {
    ....
  }
  ```

  使用初始化列表来初始化字段：

  ```C++
  Line::Line( double len): length(len)
  {
      cout << "Object is being created, length = " << len << endl;
  }
  ```

  上面的语法等同于如下语法：

  ```C++
  Line::Line( double len)
  {
      cout << "Object is being created, length = " << len << endl;
      length = len;
  }
  ```

  **类的析构函数**（作用于类的构造函数刚好相反）：类的**析构函数**是类的一种特殊的成员函数，它会在**每次删除所创建的对象时执**行。析构函数的名称与类的名称是完全相同的，只是在前面加了个波浪号（~）作为前缀，它不会返回任何值，也不能带有任何参数。**析构函数有助于在跳出程序（比如关闭文件、释放内存等）前释放资源。**

  ```C++
  #include <iostream>
   
  using namespace std;
   
  class Line
  {
     public:
        void setLength( double len );
        double getLength( void );
        Line();   // 这是构造函数声明
        ~Line();  // 这是析构函数声明
   
     private:
        double length;
  };
   
  // 成员函数定义，包括构造函数
  Line::Line(void)
  {
      cout << "Object is being created" << endl;
  }
  Line::~Line(void)
  {
      cout << "Object is being deleted" << endl;
  }
   
  void Line::setLength( double len )
  {
      length = len;
  }
   
  double Line::getLength( void )
  {
      return length;
  }
  // 程序的主函数
  int main( )
  {
     Line line;
   
     // 设置长度
     line.setLength(6.0); 
     cout << "Length of line : " << line.getLength() <<endl;
   
     return 0;
  }
  //输出结果
  Object is being created
  Length of line : 6
  Object is being deleted
  
  ```

  #### <a name="8">3、C++拷贝构造函数</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

  问题？(O_O)?  什么是拷贝构造函数？？？？

  首先对于普通类型的对象来说，它们之间的复制是很简单的，例如：

  ```cpp
  int a = 100;
  int b = a; 
  ```

  类的乱七八糟看不懂，跳过回头填坑

  #### <a name="9">4、C++友元函数(相当于给开后门，给某些函数特定权利可以访问私有资源)</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

  **类的友元函数是定义在类外部，但有权访问类的所有私有（private）成员和保护（protected）成员。**尽管友元函数的原型有在类的定义中出现过，但是友元函数并不是成员函数。

  友元可以是一个函数，该函数被称为友元函数；友元也可以是一个类，该类被称为友元类，在这种情况下，整个类及其所有成员都是友元。

  ==如果要声明函数为一个类的友元，需要在类定义中该函数原型前使用关键字 **friend**，如下所示：==

  ```cpp
  class Box
  {
     double width;
  public:
     double length;
     friend void printWidth( Box box );
     void setWidth( double wid );
  };
  //同样的，声明类ClassTwo的所有成员函数作为类ClassOne的友元，需要在类ClassOne的定义中放置如下声明：
  friend class ClassTwo;
  ```

  ```cpp
  #include <iostream>
   
  using namespace std;
   
  class Box
  {
     double width;
  public:
     friend void printWidth( Box box );
     void setWidth( double wid );
  };
  
  // 成员函数定义
  void Box::setWidth( double wid )
  {
      width = wid;
  }
  
  // 请注意：printWidth() 不是任何类的成员函数
  void printWidth( Box box )
  {
     /* 因为 printWidth() 是 Box 的友元，它可以直接访问该类的任何成员 */
     cout << "Width of box : " << box.width <<endl;
  }
   
  // 程序的主函数
  int main( )
  {
     Box box;
   
     // 使用成员函数设置宽度
     box.setWidth(10.0);
     
     // 使用友元函数输出宽度
     printWidth( box );
   
     return 0;
  }
  
  ```

  #### <a name="10">5、内联函数</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

  一般的函数有一个潜在的缺点：调用函数比求解等价表达式要慢得多。在大多数的机器上，调用函数都要做很多工作：调用前要先保存寄存器，并在返回时恢复，复制实参，程序还必须转向一个新位置执行。

  在C++中可以使用**内联函数，**其目的是为了提高函数的执行效率**，**通常与类一起使用。如果一个函数是内联的，那么在编译时，编译器会把该函数的代码副本放置在每个调用该函数的地方。

  对内联函数进行任何修改，都需要重新编译函数的所有客户端，因为编译器需要重新更换一次所有的代码，否则将会继续使用旧的函数。

  如果想把一个函数定义为内联函数，则需要在函数名前面放置关键字 **inline**，在调用函数之前需要对函数进行定义。如果已定义的函数多于一行，编译器会忽略 inline 限定符。

  在类定义中的定义的函数都是内联函数，即使没有使用 **inline** 说明符。

  下面是使用内联函数来返回两个数中的最大值：

  ```cpp
  #include <iostream>
  using namespace std;
  
  inline int Max(int x, int y)
  {
     return (x > y)? x : y;
  }
  
  // 程序的主函数
  int main( )
  {
  
     cout << "Max (20,10): " << Max(20,10) << endl;
     cout << "Max (0,200): " << Max(0,200) << endl;
     cout << "Max (100,1010): " << Max(100,1010) << endl;
     return 0;
  }
  //输出结果
  Max (20,10): 20
  Max (0,200): 200
  Max (100,1010): 1010
  ```

  有了内联函数，就能像调用一个函数那样方便地重复使用一段代码，而不需要付出执行函数调用的额外开销。很显然，使用内联函数会是最终可执行程序的体积增加。以空间换取时间，或消耗时间来增加空间，这是计算机学科中常用的方法。

  内联函数中的代码应该只是很简单、执行很快的几条语句。如果一个函数较为复杂，它执行的时间可能上万倍于函数调用的额外开销，那么将其作为内联函数处理的结果是付出让代码体积增加不少的代价，却只使速度提高了万分之一，这显然是不划算的，而且有些函数即使声明为内联的也不一定会被编译器内联。

  有时函数看上去很简单，例如只有一个包含一两条语句的循环，但该循环的执行次数可能很多，要消耗大量时间，那么这种情况也不适合将其实现为内联函数。

  另外需要注意的是，调用内联函数的语句前必须已经出现内联函数的定义（即整个函数体），而不能只出现内联函数的声明。

  ✅：**也就是说内敛函数相当于是对传统函数的改造，在定义时需要在其开头位置添加inline符号，该类函数在执行过程中相当于不需要像传统函数使用时老需要寄存调用，直接将代码复制到各个需要调用的地方**

  #### <a name="11">6、C++ this指针</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

  在 C++ 中，每一个对象都能通过 **this** 指针来访问自己的地址。**this** 指针是所有成员函数的隐含参数。因此，在成员函数内部，它可以用来指向调用对象。

  友元函数没有 **this** 指针，因为友元不是类的成员。只有成员函数才有 **this** 指针。

  ```cpp
  #include <iostream>
   
  using namespace std;
  
  class Box
  {
     public:
        // 构造函数定义
        Box(double l=2.0, double b=2.0, double h=2.0)
        {
           cout <<"Constructor called." << endl;
           length = l;
           breadth = b;
           height = h;
        }
        double Volume()
        {
           return length * breadth * height;
        }
        int compare(Box box)
        {
           return this->Volume() > box.Volume();//这个地方的this就是指向的Box这个类的本身
        }
     private:
        double length;     // Length of a box
        double breadth;    // Breadth of a box
        double height;     // Height of a box
  };
  
  int main(void)
  {
     Box Box1(3.3, 1.2, 1.5);    // Declare box1
     Box Box2(8.5, 6.0, 2.0);    // Declare box2
  
     if(Box1.compare(Box2))
     {
        cout << "Box2 is smaller than Box1" <<endl;
     }
     else
     {
        cout << "Box2 is equal to or larger than Box1" <<endl;
     }
     return 0;
  }
  //输出结果
  Constructor called.
  Constructor called.
  Box2 is equal to or larger than Box1
  ```

  #### <a name="12">7、指向类的指针</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

  一个指向 C++ 类的指针与指向结构的指针类似，访问指向类的指针的成员，需要使用成员访问运算符 **->**，就像访问指向结构的指针一样。与所有的指针一样，您必须在使用指针之前，对指针进行初始化。

  ```CPP
  #include <iostream>
   
  using namespace std;
  
  class Box
  {
     public:
        // 构造函数定义
        Box(double l=2.0, double b=2.0, double h=2.0)
        {
           cout <<"Constructor called." << endl;
           length = l;
           breadth = b;
           height = h;
        }
        double Volume()
        {
           return length * breadth * height;
        }
     private:
        double length;     // Length of a box
        double breadth;    // Breadth of a box
        double height;     // Height of a box
  };
  
  int main(void)
  {
     Box Box1(3.3, 1.2, 1.5);    // Declare box1
     Box Box2(8.5, 6.0, 2.0);    // Declare box2
     Box *ptrBox;                // Declare pointer to a class.
  
     // 保存第一个对象的地址
     ptrBox = &Box1;
  
     // 现在尝试使用成员访问运算符来访问成员
     cout << "Volume of Box1: " << ptrBox->Volume() << endl;
  
     // 保存第二个对象的地址
     ptrBox = &Box2;
  
     // 现在尝试使用成员访问运算符来访问成员
     cout << "Volume of Box2: " << ptrBox->Volume() << endl;
    
     return 0;
  }
  //输出结果
  Constructor called.
  Constructor called.
  Volume of Box1: 5.94
  Volume of Box2: 102
  ```

  #### <a name="13">8、C++类的静态成员</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

  我们可以使用 **static** 关键字来把类成员定义为静态的。当我们声明类的成员为静态时，这意味着无论创建多少个类的对象，静态成员都只有一个副本。

  **静态成员在类的所有对象中是共享的。如果不存在其他的初始化语句，在创建第一个对象时，所有的静态数据都会被初始化为零**。我们不能把静态成员放置在类的定义中，但是可以在类的外部通过使用==范围解析运算符 **::** 来重新声明静态变量==从而对它进行初始化，如下面的实例所示。

  下面的实例有助于更好地理解静态数据成员的概念：

  ```cpp
  #include <iostream>
   
  using namespace std;
  
  class Box
  {
     public:
        static int objectCount;
        // 构造函数定义
        Box(double l=2.0, double b=2.0, double h=2.0)
        {
           cout <<"Constructor called." << endl;
           length = l;
           breadth = b;
           height = h;
           // 每次创建对象时增加 1
           objectCount++;
        }
        double Volume()
        {
           return length * breadth * height;
        }
     private:
        double length;     // 长度
        double breadth;    // 宽度
        double height;     // 高度
  };
  
  // 初始化类 Box 的静态成员
  int Box::objectCount = 0;
  ‼️‼️ //在访问这种静态参数时，这里的访问符号不再是. 而是变成了::
  int main(void)
  {
     Box Box1(3.3, 1.2, 1.5);    // 声明 box1
     Box Box2(8.5, 6.0, 2.0);    // 声明 box2
  
     // 输出对象的总数
     cout << "Total objects: " << Box::objectCount << endl;
  
     return 0;
  }
  //输出结果
  Constructor called.
  Constructor called.
  Total objects: 2
  //这里static的意思就是不管怎么搞，怎么实例化，大家各个实例之间都是用同一个参数，也就是说他不属于任何一个特定的个体实例化，而是级别更高直属于类本身的，所以访问符号也从.变为了::
  ```

  #### <a name="14">9、静态函数成员</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

  如果把函数成员声明为静态的，就可以把函数与类的任何特定对象独立开来。静态成员函数即使在类对象不存在的情况下也能被调用，**静态函数**只要使用类名加范围解析运算符 **::** 就可以访问。

  静态成员函数只能访问静态数据成员，不能访问其他静态成员函数和类外部的其他函数。

  静态成员函数有一个类范围，他们不能访问类的 this 指针。您可以使用静态成员函数来判断类的某些对象是否已被创建。

  ```cpp
  #include <iostream>
   
  using namespace std;
  
  class Box
  {
     public:
        static int objectCount;
        // 构造函数定义
        Box(double l=2.0, double b=2.0, double h=2.0)
        {
           cout <<"Constructor called." << endl;
           length = l;
           breadth = b;
           height = h;
           // 每次创建对象时增加 1
           objectCount++;
        }
        double Volume()
        {
           return length * breadth * height;
        }
        static int getCount()
        {
           return objectCount;
        }
     private:
        double length;     // 长度
        double breadth;    // 宽度
        double height;     // 高度
  };
  
  // 初始化类 Box 的静态成员
  int Box::objectCount = 0;
  
  int main(void)
  {
    
    
    ‼️‼️ //注意，这种静态参数（变量及函数）的调用需要使用::而不是跟以往一样使用的是单点号，这里需要注意
      
      
     // 在创建对象之前输出对象的总数
     cout << "Inital Stage Count: " << Box::getCount() << endl;
  
     Box Box1(3.3, 1.2, 1.5);    // 声明 box1
     Box Box2(8.5, 6.0, 2.0);    // 声明 box2
  
     // 在创建对象之后输出对象的总数
     cout << "Final Stage Count: " << Box::getCount() << endl;
  
     return 0;
  }
  //输出结果
  Inital Stage Count: 0
  Constructor called.
  Constructor called.
  Final Stage Count: 2
  ```


### <a name="15">四、C++继承</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

面向对象程序设计中最重要的一个概念是继承。继承允许我们依据另一个类来定义一个类，这使得创建和维护一个应用程序变得更容易。这样做，也达到了重用代码功能和提高执行时间的效果

当创建一个类时，您不需要重新编写新的数据成员和成员函数，只需指定新建的类继承了一个已有的类的成员即可。这个已有的类称为**基类**，新建的类称为**派生类**。

#### <a name="16">1、基类&派生类</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

一个类可以派生自多个类，这意味着，它可以从多个基类继承数据和函数。定义一个派生类，我们使用一个类派生列表来指定基类。类派生列表以一个或多个基类命名，形式如下：

```C++
class derived-class: access-specifier base-class
```

其中，访问修饰符 access-specifier 是 **public、protected** 或 **private** 其中的一个，base-class 是之前定义过的某个类的名称。如果未使用访问修饰符 access-specifier，则默认为 private。

假设有一个基类 **Shape**，**Rectangle** 是它的派生类，如下所示：

```C++
#include <iostream>
 
using namespace std;

// 基类
class Shape 
{
   public:
      void setWidth(int w)
      {
         width = w;
      }
      void setHeight(int h)
      {
         height = h;
      }
   protected:
      int width;
      int height;
};

// 派生类
class Rectangle: public Shape
{
   public:
      int getArea()
      { 
         return (width * height); 
      }
};

int main(void)
{
   Rectangle Rect;
 
   Rect.setWidth(5);
   Rect.setHeight(7);

   // 输出对象的面积
   cout << "Total area: " << Rect.getArea() << endl;

   return 0;
} 
//输出结果
Total area: 35
```

#### <a name="17">2、访问控制和继承</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

派生类可以访问基类中所有的非私有成员。因此基类成员如果不想被派生类的成员函数访问，则应在基类中声明为 private。

我们可以根据访问权限总结出不同的访问类型，如下所示：

| 访问     | public | protected | private |
| :------- | :----- | :-------- | :------ |
| 同一个类 | yes    | yes       | yes     |
| 派生类   | yes    | yes       | no      |
| 外部的类 | yes    | no        | no      |

当一个类派生自基类，该基类可以被继承为 **public、protected** 或 **private** 几种类型。继承类型是通过上面讲解的访问修饰符 access-specifier 来指定的。

我们几乎不使用 **protected** 或 **private** 继承，通常使用 **public** 继承。当使用不同类型的继承时，遵循以下几个规则：

- **公有继承（public）：**当一个类派生自**公有**基类时，基类的**公有**成员也是派生类的**公有**成员，基类的**保护**成员也是派生类的**保护**成员，基类的**私有**成员不能直接被派生类访问，但是可以通过调用基类的**公有**和**保护**成员来访问。
- **保护继承（protected）：** 当一个类派生自**保护**基类时，基类的**公有**和**保护**成员将成为派生类的**保护**成员。
- **私有继承（private）：**当一个类派生自**私有**基类时，基类的**公有**和**保护**成员将成为派生类的**私有**成员。

> 一个派生类继承了所有的基类方法，但下列情况除外：

> - 基类的构造函数、析构函数和拷贝构造函数。
> - 基类的重载运算符。
> - 基类的友元函数。

#### <a name="18">3、多继承</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

多继承即一个子类可以有多个父类，它继承了多个父类的特性。

C++ 类可以从多个类继承成员，语法如下：

```
class <派生类名>: <继承方式1> <基类名1>, <继承方式2> <基类名2>
{
……
}；
```

其中，访问修饰符 access 是 **public、protected** 或 **private** 其中的一个，用来修饰每个基类，各个基类之间用逗号分隔，如上所示。现在让我们一起看看下面的实例：

```C++
#include <iostream>
 
using namespace std;

// 基类 Shape
class Shape 
{
   public:
      void setWidth(int w)
      {
         width = w;
      }
      void setHeight(int h)
      {
         height = h;
      }
   protected:
      int width;
      int height;
};

// 基类 PaintCost
class PaintCost 
{
   public:
      int getCost(int area)
      {
         return area * 70;
      }
};

// 派生类
class Rectangle: public Shape, public PaintCost
{
   public:
      int getArea()
      { 
         return (width * height); 
      }
};

int main(void)
{
   Rectangle Rect;
   int area;
 
   Rect.setWidth(5);
   Rect.setHeight(7);

   area = Rect.getArea();
   
   // 输出对象的面积
   cout << "Total area: " << Rect.getArea() << endl;

   // 输出总花费
   cout << "Total paint cost: $" << Rect.getCost(area) << endl;

   return 0;
}
```

### <a name="19">五、C++重载运算符和重载函数</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

==C++ 允许在同一作用域中的某个**函数**和**运算符**指定多个定义==，分别称为**函数重载**和**运算符重载**。

==重载声明是指一个与之前已经在该作用域内声明过的函数或方法具有相同名称的声明，但是它们的参数列表和定义（实现）不相同。==

当您调用一个**重载函数**或**重载运算符**时，编译器通过把您所使用的参数类型与定义中的参数类型进行比较，决定选用最合适的定义。选择最合适的重载函数或重载运算符的过程，称为**重载决策**。

#### <a name="20">1、函数的重载</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

在同一个作用域内，可以声明几个功能类似的同名函数，但是这些同名函数的形式参数（指参数的个数、类型或者顺序）必须不同。您不能仅通过返回类型的不同来重载函数。

下面的实例中，同名函数 **print()** 被用于输出不同的数据类型：

```cpp
#include <iostream>
using namespace std;
 
class printData 
{
   public:
      void print(int i) {
        cout << "Printing int: " << i << endl;
      }

      void print(double  f) {
        cout << "Printing float: " << f << endl;
      }

      void print(char* c) {
        cout << "Printing character: " << c << endl;
      }
};

int main(void)
{
   printData pd;
 
   // Call print to print integer
   pd.print(5);
   // Call print to print float
   pd.print(500.263);
   // Call print to print character
   pd.print("Hello C++");
 
   return 0;
}
//输出结果 ：就是定义了一堆重名函数，但是他们的输入是不一样的，再以此来区分他们之间的区别
Printing int: 5
Printing float: 500.263
Printing character: Hello C++
```

#### <a name="21">2、运算符重载</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

**重载的运算符是带有特殊名称的函数**，函数名是由关键字 operator 和其后要重载的运算符符号构成的。与其他函数一样，重载运算符有一个返回类型和一个参数列表。

```cpp
//作为成员函数时的定义方法
Box operator+(const Box&);
```

==声明加法运算符用于把两个 Box 对象相加，返回最终的 Box 对象。大多数的重载运算符可被定义为普通的非成员函数或者被定义为类成员函数。如果我们定义上面的函数为类的非成员函数，那么我们需要为每次操作传递两个参数，如下所示==：

补充:⁉️: **区分类的成员函数与类的非成员函数** 举一个例子🌰：

```cpp
////////////原始的类//////////////
class People{
        public:
            ...
            void Getup( );
            void Washing( );
            void eating( );
            ...
        }
////////////成员函数//////////////
class People
{
  			public:
  			……
          void morningAction(){ //在这里，morningAction函数也就是成员函数
          	void Getup( );
            void Washing( );
            void eating( );  
        }
        		
}
////////////非成员函数//////////////
void moringAction(People& p)//在这里，将函数定义在类的外部，将类作为输入参数并操作类中的函数及变量的方法，此时这个函数被称作非成员函数
        {
                p.Getup( );
                p.Washing( );
                p.eating( );
        }
```

如果我们定义上面的函数为类的非成员函数，那么我们需要为每次操作传递两个参数，如下所示：

```cpp
//作为非成员函数时定义重载符的语句
Box operator+(const Box&, const Box&);
```

下面的实例使用成员函数演示了运算符重载的概念。在这里，对象作为参数进行传递，对象的属性使用 **this** 运算符进行访问，

```cpp
#include <iostream>
using namespace std;

class Box
{
   public:

      double getVolume(void)
      {
         return length * breadth * height;
      }
      void setLength( double len )
      {
          length = len;
      }

      void setBreadth( double bre )
      {
          breadth = bre;
      }

      void setHeight( double hei )
      {
          height = hei;
      }
      // 重载 + 运算符，用于把两个 Box 对象相加
      Box operator+(const Box& b) //相当于检测到有BOX类跟+连用时，就会自动重载
      {
         Box box;
         box.length = this->length + b.length;
         box.breadth = this->breadth + b.breadth;
         box.height = this->height + b.height;
         return box;
      }
   private:
      double length;      // 长度
      double breadth;     // 宽度
      double height;      // 高度
};
// 程序的主函数
int main( )
{
   Box Box1;                // 声明 Box1，类型为 Box
   Box Box2;                // 声明 Box2，类型为 Box
   Box Box3;                // 声明 Box3，类型为 Box
   double volume = 0.0;     // 把体积存储在该变量中
 
   // Box1 详述
   Box1.setLength(6.0); 
   Box1.setBreadth(7.0); 
   Box1.setHeight(5.0);
 
   // Box2 详述
   Box2.setLength(12.0); 
   Box2.setBreadth(13.0); 
   Box2.setHeight(10.0);
 
   // Box1 的体积
   volume = Box1.getVolume();
   cout << "Volume of Box1 : " << volume <<endl;
 
   // Box2 的体积
   volume = Box2.getVolume();
   cout << "Volume of Box2 : " << volume <<endl;

   // 把两个对象相加，得到 Box3
   Box3 = Box1 + Box2; //此处自动重载加号运算符

   // Box3 的体积
   volume = Box3.getVolume();
   cout << "Volume of Box3 : " << volume <<endl;

   return 0;
}
//输出结果
Volume of Box1 : 210
Volume of Box2 : 1560
Volume of Box3 : 5400
```

下面是可重载的运算符列表：

| +    | -    | *    | /      | %      | ^         |
| ---- | ---- | ---- | ------ | ------ | --------- |
| &    | \|   | ~    | !      | ,      | =         |
| <    | >    | <=   | >=     | ++     | --        |
| <<   | >>   | ==   | !=     | &&     | \|\|      |
| +=   | -=   | /=   | %=     | ^=     | &=        |
| \|=  | *=   | <<=  | >>=    | []     | ()        |
| ->   | ->*  | new  | new [] | delete | delete [] |

下面是不可重载的运算符列表：

| ::   | .*   | .    | ?:   |
| ---- | ---- | ---- | ---- |

### <a name="22">六、重载运算符实例</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

#### <a name="23">**1、一元运算符重载**（也就是只有一个数字参与运算的情况）</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

一元运算符只对一个操作数进行操作，下面是一元运算符的实例：

- [递增运算符（ ++ ）和递减运算符（ -- ）](https://www.w3cschool.cn/cpp/increment-decrement-operators-overloading.html)
- 一元减运算符，即负号（ - ）
- 逻辑非运算符（ ! ）

一元运算符通常出现在它们所操作的对象的左边，比如 !obj、-obj 和 ++obj，但有时它们也可以作为后缀，比如 obj++ 或 obj--。

例子1：

```cpp
#include <iostream>
using namespace std;
 
class Distance
{
   private:
      int feet;             // 0 到无穷
      int inches;           // 0 到 12
   public:
      // 所需的构造函数
      Distance(){
         feet = 0;
         inches = 0;
      }
      Distance(int f, int i){
         feet = f;
         inches = i;
      }
      // 显示距离的方法
      void displayDistance()
      {
         cout << "F: " << feet << " I:" << inches <<endl;
      }
      // 重载负运算符（ - ）
      Distance operator- ()//因为这里是前缀一元运算符，不用其他参数，所以这里的参数输入位置可以是空的
      {
         feet = -feet;
         inches = -inches;
         return Distance(feet, inches);//构造函数
      }
};
int main()
{
   Distance D1(11, 10), D2(-5, 11);
 
   -D1;                     // 取相反数
   D1.displayDistance();    // 距离 D1

   -D2;                     // 取相反数
   D2.displayDistance();    // 距离 D2

   return 0;
}
//返回结果
F: -11 I:-10
F: 5 I:-11
```

例子2：⭐️很重要，区分运算符是前缀还是后缀的

```cpp
#include <iostream>
using namespace std;
 
class Time
{
   private:
      int hours;             // 0 到 23
      int minutes;           // 0 到 59
   public:
      // 所需的构造函数
      Time(){
         hours = 0;
         minutes = 0;
      }
      Time(int h, int m){
         hours = h;
         minutes = m;
      }
      // 显示时间的方法
      void displayTime()
      {
         cout << "H: " << hours << " M:" << minutes <<endl;
      }
      // 重载前缀递增运算符（ ++ ）
      Time operator++ ()  
      {
         ++minutes;          // 对象加 1
         if(minutes >= 60)  
         {
            ++hours;
            minutes -= 60;
         }
         return Time(hours, minutes); //这里返回的相当于是构造函数，将对象重新初始化了
      }
      // 重载后缀递增运算符（ ++ ）
      Time operator++( int )         
      {
         // 保存原始值
         Time T(hours, minutes);
         // 对象加 1
         ++minutes;                    
         if(minutes >= 60)
         {
            ++hours;
            minutes -= 60;
         }
         // 返回旧的原始值
         return T; 
      }
};
int main()
{
   Time T1(11, 59), T2(10,40);
 
   ++T1;                    // T1 加 1
   T1.displayTime();        // 显示 T1
   ++T1;                    // T1 再加 1
   T1.displayTime();        // 显示 T1
 
   T2++;                    // T2 加 1
   T2.displayTime();        // 显示 T2
   T2++;                    // T2 再加 1
   T2.displayTime();        // 显示 T2
   return 0;
}
//输出结果
H: 12 M:0
H: 12 M:1
H: 10 M:41
H: 10 M:42
```

#### <a name="24">2、二元运算符重载</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

二元运算符需要两个参数，下面是二元运算符的实例。我们平常使用的加运算符（ + ）、减运算符（ - ）、乘运算符（ * ）和除运算符（ / ）都属于二元运算符。就像加(+)运算符。

下面的实例演示了如何重载加运算符（ + ）。类似地，您也可以尝试重载减运算符（ - ）和除运算符（ / ）。

```cpp
#include <iostream>
using namespace std;
 
class Box
{
   double length;      // 长度
   double breadth;     // 宽度
   double height;      // 高度
public:
 
   double getVolume(void)
   {
      return length * breadth * height;
   }
   void setLength( double len )
   {
       length = len;
   }
 
   void setBreadth( double bre )
   {
       breadth = bre;
   }
 
   void setHeight( double hei )
   {
       height = hei;
   }
   // 重载 + 运算符，用于把两个 Box 对象相加
   Box operator+(const Box& b)
   {
      Box box;
      box.length = this->length + b.length;
      box.breadth = this->breadth + b.breadth;
      box.height = this->height + b.height;
      return box;
   }
};
// 程序的主函数
int main( )
{
   Box Box1;                // 声明 Box1，类型为 Box
   Box Box2;                // 声明 Box2，类型为 Box
   Box Box3;                // 声明 Box3，类型为 Box
   double volume = 0.0;     // 把体积存储在该变量中
 
   // Box1 详述
   Box1.setLength(6.0); 
   Box1.setBreadth(7.0); 
   Box1.setHeight(5.0);
 
   // Box2 详述
   Box2.setLength(12.0); 
   Box2.setBreadth(13.0); 
   Box2.setHeight(10.0);
 
   // Box1 的体积
   volume = Box1.getVolume();
   cout << "Volume of Box1 : " << volume <<endl;
 
   // Box2 的体积
   volume = Box2.getVolume();
   cout << "Volume of Box2 : " << volume <<endl;
 
   // 把两个对象相加，得到 Box3
   Box3 = Box1 + Box2;
 
   // Box3 的体积
   volume = Box3.getVolume();
   cout << "Volume of Box3 : " << volume <<endl;
 
   return 0;
}
//输出结果
Volume of Box1 : 210
Volume of Box2 : 1560
Volume of Box3 : 5400
```

#### <a name="25">3、关系运算符重载</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

C++ 语言支持各种关系运算符（ < 、 > 、 <= 、 >= 、 == 等等），它们可用于比较 C++ 内置的数据类型。

您可以重载任何一个关系运算符，重载后的关系运算符可用于比较类的对象。

```cpp
#include <iostream>
using namespace std;
 
class Distance
{
   private:
      int feet;             // 0 到无穷
      int inches;           // 0 到 12
   public:
      // 所需的构造函数
      Distance(){
         feet = 0;
         inches = 0;
      }
      Distance(int f, int i){
         feet = f;
         inches = i;
      }
      // 显示距离的方法
      void displayDistance()
      {
         cout << "F: " << feet << " I:" << inches <<endl;
      }
      // 重载负运算符（ - ）//一元运算符
      Distance operator- ()  
      {
         feet = -feet;
         inches = -inches;
         return Distance(feet, inches);
      }
      // 重载小于运算符（ < ）
      bool operator <(const Distance& d) //这里用的时布尔值
      {
         if(feet < d.feet)
         {
            return true;
         }
         if(feet == d.feet && inches < d.inches)
         {
            return true;
         }
         return false;
        //只会返回一个return 也就是就没走到上面两个return时默认返回false
      }
};
int main()
{
   Distance D1(11, 10), D2(5, 11);
 
   if( D1 < D2 )
   {
      cout << "D1 is less than D2 " << endl;
   }
   else
   {
      cout << "D2 is less than D1 " << endl;
   }
   return 0;
}
//输出结果
D2 is less than D1
```

#### <a name="26">4、输入/输出运算符重载</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

C++ 能够使用流提取运算符 >> 和流插入运算符 << 来输入和输出内置的数据类型。您可以重载流提取运算符和流插入运算符来操作对象等用户自定义的数据类型。

在这里，有一点很重要，我们需要把运算符重载函数声明为类的友元函数，这样我们就能不用创建对象而直接调用函数。

**重载输入运算符>>**

下面我们以全局函数的形式重载`>>`，使它能够读入两个 double 类型的数据，并分别赋值给复数的实部和虚部：

```cpp
istream & operator>>(istream &in, complex &A){
    in >> A.m_real >> A.m_imag;
    return in;
}
```

istream 表示输入流，cin 是 istream 类的对象，只不过这个对象是在标准库中定义的。之所以返回 istream 类对象的引用，是为了能够连续读取复数，让代码书写更加漂亮，例如：

```cpp
complex c1, c2;cin>>c1>>c2;
```

如果不返回引用，那就只能一个一个地读取了：

```cpp
complex c1, c2;cin>>c1;cin>>c2;
```

另外，运算符重载函数中用到了 complex 类的 private 成员变量，必须在 complex 类中将该函数声明为友元函数：

```cpp
friend istream & operator>>(istream & in , complex &a);
```

`>>`运算符可以按照下面的方式使用：

```cpp
complex c;
cin>>c;
```

当输入`1.45 2.34`后，这两个小数就分别成为对象 c 的实部和虚部了。`cin>> c;`这一语句其实可以理解为：

```cpp
operator >> (cin, c3)
```

调用函数时，形参in成为cin的引用，形参A成为c3的引用，因此调用函数的过程变为：

```cpp
cin >> c3.m_real >> c3.m_imag; return cin
```

**重载输出运算符 <<**

同样地，我们也可以模仿上面的形式对输出运算符`>>`进行重载，让它能够输出复数，请看下面的代码：

```cpp
ostream & operator<<(ostream &out, complex &A){
    out << A.m_real <<" + "<< A.m_imag <<" i ";
    return out;
}
```

ostream 表示输出流，cout 是 ostream 类的对象。由于采用了引用的方式进行参数传递，并且也返回了对象的引用，所以重载后的运算符可以实现连续输出。
为了能够直接访问 complex 类的 private 成员变量，同样需要将该函数声明为 complex 类的友元函数：（只有静态函数才能不经创建直接访问）

```cpp
friend ostream & operator<<(ostream &out, complex &A);
```

一个例子🌰：

```cpp
#include <iostream>
using namespace std;
 
class Distance
{
   private:
      int feet;             // 0 到无穷
      int inches;           // 0 到 12
   public:
      // 所需的构造函数
      Distance(){
         feet = 0;
         inches = 0;
      }
      Distance(int f, int i){
         feet = f;
         inches = i;
      }
      friend ostream &operator<<( ostream &output, 
                                       const Distance &D )
      { 
         output << "F : " << D.feet << " I : " << D.inches;
         return output;            
      }

      friend istream &operator>>( istream  &input, Distance &D )
      { 
         input >> D.feet >> D.inches;
         return input;            
      }
};
int main()
{
   Distance D1(11, 10), D2(5, 11), D3;

   cout << "Enter the value of object : " << endl;
   cin >> D3;
   cout << "First Distance : " << D1 << endl;
   cout << "Second Distance :" << D2 << endl;
   cout << "Third Distance :" << D3 << endl;


   return 0;
}
//输出结果
$./a.out
Enter the value of object :
70
10
First Distance : F : 11 I : 10
Second Distance :F : 5 I : 11
Third Distance :F : 70 I : 10
```

#### <a name="27">4、赋值运算符重载</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

就像其他运算符一样，您可以重载赋值运算符（ = ），用于创建一个对象，比如拷贝构造函数。

下面的实例演示了如何重载赋值运算符。

```cpp
#include <iostream>
using namespace std;
 
class Distance
{
   private:
      int feet;             // 0 到无穷
      int inches;           // 0 到 12
   public:
      // 所需的构造函数
      Distance(){
         feet = 0;
         inches = 0;
      }
      Distance(int f, int i){
         feet = f;
         inches = i;
      }
      void operator=(const Distance &D )
      { 
         feet = D.feet;
         inches = D.inches;
      }
      // 显示距离的方法
      void displayDistance()
      {
         cout << "F: " << feet <<  " I:" <<  inches << endl;
      }
      
};
int main()
{
   Distance D1(11, 10), D2(5, 11);

   cout << "First Distance : "; 
   D1.displayDistance();
   cout << "Second Distance :"; 
   D2.displayDistance();

   // 使用赋值运算符
   D1 = D2;
   cout << "First Distance :"; 
   D1.displayDistance();

   return 0;
}
//输出结果
First Distance : F: 11 I:10
Second Distance :F: 5 I:11
First Distance :F: 5 I:11
```

#### <a name="28">5、函数调用运算符 () 重载</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

函数调用运算符 () 可以被重载用于类的对象。当重载 () 时，您不是创造了一种新的调用函数的方式，相反地，这是创建一个可以传递任意数目参数的运算符函数

```cpp
#include <iostream>
using namespace std;
 
class Distance
{
   private:
      int feet;             // 0 到无穷
      int inches;           // 0 到 12
   public:
      // 所需的构造函数
      Distance(){
         feet = 0;
         inches = 0;
      }
      Distance(int f, int i){
         feet = f;
         inches = i;
      }
      // 重载函数调用运算符
      Distance operator()(int a, int b, int c)
      {
         Distance D;
         // 进行随机计算
         D.feet = a + c + 10;
         D.inches = b + c + 100 ;
         return D;
      }
      // 显示距离的方法
      void displayDistance()
      {
         cout << "F: " << feet <<  " I:" <<  inches << endl;
      }
      
};
int main()
{
   Distance D1(11, 10), D2;

   cout << "First Distance : "; 
   D1.displayDistance();

   D2 = D1(10, 10, 10); // invoke operator()只要检测到（）内变为三个了，证明就激发了这个重载，就会进行内部定义的运算。
   cout << "Second Distance :"; 
   D2.displayDistance();

   return 0;
}
//输出结果
First Distance : F: 11 I:10
Second Distance :F: 30 I:120
```

### <a name="29">七、C++类的多态</a><a style="float:right;text-decoration:none;" href="#index">[Top]</a>

**多态**按字面的意思就是多种形态。当类之间存在层次结构，并且类之间是通过继承关联时，就会用到多态。

C++ 多态意味着调用成员函数时，会根据调用函数的对象的类型来执行不同的函数

```cpp
#include <iostream> 
using namespace std;
 
class Shape {
   protected:
      int width, height;
   public:
      Shape( int a=0, int b=0)
      {
         width = a;
         height = b;
      }
      int area()
      {
         cout << "Parent class area :" <<endl;
         return 0;
      }
};
class Rectangle: public Shape{
   public:
      Rectangle( int a=0, int b=0):Shape(a, b) { }
      int area ()
      { 
         cout << "Rectangle class area :" <<endl;
         return (width * height); 
      }
};
class Triangle: public Shape{
   public:
      Triangle( int a=0, int b=0):Shape(a, b) { }
      int area ()
      { 
         cout << "Triangle class area :" <<endl;
         return (width * height / 2); 
      }
};
// 程序的主函数
int main( )
{
   Shape *shape;
   Rectangle rec(10,7);
   Triangle  tri(10,5);

   // 存储矩形的地址
   shape = &rec;
   // 调用矩形的求面积函数 area
   shape->area();

   // 存储三角形的地址
   shape = &tri;
   // 调用三角形的求面积函数 area
   shape->area();
   
   return 0;
}
//输出结果
Parent class area
Parent class area
❌：不对啊，我希望输出的结果是两个的子类的，但是这里只有父类area函数的调用
```

> 导致错误输出的原因是，调用函数 area() 被编译器设置为基类中的版本，这就是所谓的**静态多态**，或**静态链接** - 函数调用在程序执行前就准备好了。有时候这也被称为**早绑定**，因为 area() 函数在程序编译期间就已经设置好了。

为了克服上述问题，我直接在父类定义的需要被重写的函数之前佳哥virtual，然后后续编译器在运行的时候就会自动使用子类中的定义方法。

```cpp
class Shape {
   protected:
      int width, height;
   public:
      Shape( int a=0, int b=0)
      {
         width = a;
         height = b;
      }
      virtual int area()
      {
         cout << "Parent class area :" <<endl;
         return 0;
      }
};
//输出结果
//Rectangle class area
//Triangle class area
```

此时，编译器看的是指针的内容，而不是它的类型。因此，由于 tri 和 rec 类的对象的地址存储在 *shape 中，所以会调用各自的 area() 函数。

正如您所看到的，每个子类都有一个函数 area() 的独立实现。这就是**多态**的一般使用方式。有了多态，您可以有多个不同的类，都带有同一个名称但具有不同实现的函数，函数的参数甚至可以是相同的

> ❌：在这里，这个带有virtual定义的函数就叫做虚函数

**虚函数** 是在基类中使用关键字 **virtual** 声明的函数。在派生类中重新定义基类中定义的虚函数时，会告诉编译器不要静态链接到该函数。

==我们想要的是在程序中任意点可以根据所调用的对象类型来选择调用的函数，这种操作被称为**动态链接**，或**后期绑定==**。

**纯虚函数**

您可能想要在基类中定义虚函数，以便在派生类中重新定义该函数更好地适用于对象，但是您在基类中又不能对虚函数给出有意义的实现，这个时候就会用到纯虚函数。

我们可以把基类中的虚函数 area() 改写如下：

```cpp
class Shape {
   protected:
      int width, height;
   public:
      Shape( int a=0, int b=0)
      {
         width = a;
         height = b;
      }
      // pure virtual function
      virtual int area() = 0; //在这里，也就是不定义函数内容，直接给他赋值成0
};
```

