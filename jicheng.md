# js的常用继承方式

## 原型链继承

实现:原型对象等于实例，并指定constructor

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>继承</title>
  </head>
  <body>

    <script type="text/javascript">

      /*
      原型链继承
      */
      function Person(name){
        this.name = name;
      }
      Person.prototype.getName = function(){
        return this.name;
      }


      function Student(name,score){
        this.name = name;
        this.score = score;
      }


      /*继承了Person的属性和方法*/
      Student.prototype = new Person("human");
      // console.log(Student.prototype);

      //指定Student的构造器，因为被之前的继承给覆盖了。
      Student.prototype.constructor = Student;

      /*
      在继承的基础上，有扩展了自身的方法
      */
      Student.prototype.getSocre = function () {
        return this.score;
      };

      /*自己原型上的方法会覆盖继承过来的同名方法*/
      Student.prototype.getName= function () {
        return "Student :" + this.score;
      };


      var human = new Person("human");
      console.log(human.constructor);//Person

      var one = new Student('zhansan', 59);
      console.log(one);
      console.log(one.getName());
      console.log(one.constructor);//输出该对象的构造函数！！！！



    </script>

  </body>
</html>
```

缺点:一个实例对象改变原型上的属性和方法，就会影响到其他实例对象

## 借助构造函数继承

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>借用构造函数继承</title>
  </head>

  <body>

    <script type="text/javascript">
     function Person(name,age){
       this.name = name;
       this.age = age;
       this.colors = ["red", "green", "blue"];
     }

     Person.prototype.getName = function () {
       return this.name;
     };

     Person.prototype.getAge = function () {
       return this.age;
     };

     function Student(name,age,score){
       //直接调用了Person构造函数
       Person.call(this,name,age);//直接使用已有
       this.score = score;//添加新的属性
     }

     /*
     借用构造函数，让每个对象都用于自己的属性，相互之间任何关系
     但是原型上的属性和方法，是没法拥有的。
     */

     var one = new Student('lisi', 17,60);
     console.log(one);
     one.colors.push("black");

     var two = new Student("zhangsan", 18,61);
     console.log(two);


    </script>

  </body>
</html>
```

## 组合继承

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>组合继承(原型链继承+借用构造函数继承)</title>
  </head>
  <body>

    <script type="text/javascript">

      function Person(name,age){
        this.name = name;
        this.age = age;
      }

      Person.prototype.getName = function () {
        return this.name;
      }

      Person.prototype.getAge = function () {
        return this.age;
      }


      function Student(name,age,score) {
        Person.call(this,name,age);
        this.score = score;
      }

      Student.prototype = new Person();
      Student.prototype.constructor = Student;
      Student.prototype.getScore = function () {
        return this.score;
      };

      var one = new Student('lisi', 18,80);
      console.log(one);
      console.log(one.getName());
      console.log(one.getAge());
      console.log(one.getScore());





    </script>
  </body>
</html>
```
