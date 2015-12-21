# js-
<br>1、join是数组转化为字符串   array.join(“  ”)中间的是每个数组的项链接的时候用什么链接，而字符串转化为数组的方法是string.split()方法   split方法只有一个参数，表示由字符串哪个符号开始分割为数组，若是空字符串，则返回的数组是字符串每个字符，适用于字符串的每个字符解析！！！！
<br>2、数组的toString()和valueOf方法输出的都是每项由逗号隔开的，函数的toStrong方法是输出函数的源代码.
<br>3、Concat()参数值将被添加原来的末尾，返回一个新的。Slice()方法是切割的问题，切割从哪到哪或者从哪到结束
<br>4、数组的push()方法是在末尾添加一个项，而pop是删除最后一个项  但是var a=array.pop()返回的是删除掉的，shift()是删除数组的第一项，unshift是把一个项放在第一个,然后把余下的向后移位，所以通过shift和push可以有队列的感觉
<br>5、Reverse方法是颠倒数组项的顺序，sort是将数组升序，是按字母顺序，而对于数字，就有问题了
<br>6、Splice()是把数据项插入数组中部，或者删除中部，删除的参数两个：要删除的第一个项起，和要删除多少个，替换不删除：三个参数：起始位置，替换的个数，替换的项。后面参数可以使替换插入的更多的项
<br>7、替换并删除：三个参数：起始位置，删除的个数，插入的项。后面参数可以使替换插入的更多的项。
<br>8、Js中不存在独立的函数，每个函数都是一个对象的方法。Pars
<br>9、eInt   parseFloat 这些全局函数都是Global内置对象的方法，encodeURI()处理完整的url，基本只处理空格，但不处理特殊的字符，和encodeURIComponent()处理一个片断的url，并且处理所有的非标准字符 冒号反斜杠什么的   都用于浏览器的编码。而decodeURI是解码
<br>10、Eval方法在js中很强大，是一个解释程序，eval调用内部引用的变量可在参数以外定义。例如：var a=”aaaaa”  eval(“alert(msg)”);
<br>11、Global对象还有一些属性。例如undefined   NaN等
<br>12、所有非本地对象都是宿主对象，所有BOM和DOM对象都是宿主对象
<br>13、Js只存在一种作用域，公用作用域，所有属性和方法默认都是公用的，而在属性名前后加下划线，开发者表示是私有作用域，只是让开发者自己知道是私有的，但是不会改变他是公用的作用域。
<br>14、构造函数是函数，函数是对象，对象有属性和方法。所以也就可以在一个函数再定义一个函数
<br>15、定义类和对象 的方式1:工厂方式，也就是定义一个方法，会返回一个对象，也就是新生成那个对象。然后要新建对象，直接调用方法就像，这样就有公共的属性和方法，可以自己创建新的时候修改

----------继续记录------------


<br>16.一般工厂方式建对象的时候，会在里面写一些函数方法，这样就每次创建对象都会有这个方法，这样浪费内存，有时想让这个方法是公共的方法，就在工厂外定义一个对象的公共函数，然后通过属性指向该方法，也就相当于指向了，而不是创建。但是这样并没有什么意义，用原型方式可以解决。
<br>17.构造函数内部无创建对象，而是使用this关键字。并且命名第一个字母是大写。
<br>18.原型方式利用了对象的prototype属性，把它看成创建新对象所依赖的原型。用空构造函数来设置类名，然后所有的属性和方法都被直击赋予prototype属性。Car.prototype.color=”red”;Car.prototype.show=function(){`````};   这种方法不能是有参构造函数，则必须在创建对象之后才能修改属性，并且严重的是，当属性指向的是对象而不是函数时，有问题，因为对象不是被多个实例共享的。这样就会改变一个对象的东西，其他实例的对象也会跟着改变。原型链的查找，一般没有的话就会一直向上查找，一直到查到原型链的根部。也就是就近原则。所以每个对象基本上都有tostring方法，因为所有原型链根部也就是object都有tostring方法。
<br>19.所以为了创建合理的对象，就要联合使用构造函数和原型方式去创建。这样就像其他语言一样创建对象了。方法是，用构造函数定义对象的所有非函数属性，用原型方式定义对象的函数（方法），这样就可以所有函数只被创建一次，而每个实例都有自己的属性。记得函数里要用this。
<br>20.而动态原型方法则是更完美这种混合方式的。改的地方是，赋予对象方法的位置。
<br>21.混合工厂方式与工厂方式差不多，建工厂都是差不多的，但是在利用工厂创建对象的时候就不一样了，用了new xxx()，而工厂方式是直接xxx();应该避免使用这种方法。
<br>22.Js字符串也一样，是不可变的，即值是不能改变的
<br>23.有时候用字符串直接复制或者+链接，重复几百次几千次就会造成性能问题，解决方法是用array数组。，然后用join去创建最后的字符串，也就是对字符串的操作，就先用数组存着，然后最后才转化为字符串。也可以用stringbuffer类打包功能。
<br>24.检测性能问题，可以用时间去测 data =new Date()  是检测性能的常用方法。
<br>25.也可以重定义已有的方法。因为函数名是一个指向函数的指针，所以可以让他重新指向另外一个函数。但是在覆盖原始方法前，比较安全的做法是存储它的指针，以便以后使用。
<br>26.UML可以可视化的表示一些复杂的继承关系等类与类，对象与对象之间的关系。
<br>27.本地类和宿主类不能作为基类，这样可以防止代码注入。抽象类是给子类提供通用的函数，但是不能直接使用基类，就是抽象类。
<br>28、继承的方式：1对象冒充：delete  一个方法，就可以以后不能对这个方法的调用了。
所有的新属性和新方法都必须在删除了新方法的代码行后定义，否则，可能会覆盖超累的相关属性和方法。
对象冒充可以支持多继承。书写形式是。
Function z(){
  this.newmethod=a;
  this.newmethod();
  delete this.newmethod;

  this.newmethod=b;
  this.newmethod();
  delete this.newmethod;
}
弊端是，若方法a和b具有同样的属性和方法，后面的优先级比前面的高。
<br>2.call()方法继承。和对象冒充很相似。第一个参数是this对象，其他都是直接传递给函数自身的。这样，对象冒充的这三行就可以换成为call（）了，例如
this.newmethod=a;
  this.newmethod();
  delete this.newmethod;
可以换位a.call(this,xxx);
<br>3.、apply()方法继承，有两个参数，this对象，和要传递给函数的参数的数组。和call（）不同的就是，参数是数组参数了，而不是一个一个的参数。
<br>4.原型链继承，prototype对象是个模板，要实例化的对象都以这个模板为基础， prototype对象的任何属性和方法都被传递给那个类的所以实例，原型链就是利用这种机制的。
B.prototype=new a();把b的prototype属性设置成a的实例，这就是想要a的所有属性和方法， 但是有不行逐个将他们赋予b的prototype属性。需要注意的是，和对象冒充一样，子类的所有属性和方法都要在prototype属性被赋值之后，这样才能覆盖，原型链的弊端是不支持多重继承。
<br>5.混合方式。用对象冒充继承构造函数的属性，用原型链继承prototype对象的方法。就是这两个混合。
经常这样定义一个基类 function A(color){
                          This.color=color;
}
A.prototype.getArea=function(){
    
}
子类继承A

Function B(sides){
  A.call(this,”red”);
 This.sides=sides
}
B.prototype=new A();
B.prototype.getArea=function(){  //覆盖了

}

----------继续记录------------


