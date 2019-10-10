# 2.23

## 不能，还不知道指针是否已初始化。



# 2.24

## 因为p是void的一个空指针，可以接受任意类型，而lp不能接受int型。



# 2.25

##  （a）ip是int型的指针，i是int型的变量，r是int型的一个引用。 

## （b）i是int型的变量，ip是一个空指针。

## （c) ip是int型的指针，ip2是int型的变量。



# 2.35

## i是const int 型，j是int型，k是const int &型，p是const int*型，j2是const int型，k2是const int &型。



# 3.4

## (1)

```c++
// kangshaojie
#include <iostream>
#include <string>
int main() {
    std:: string a , b;
    std:: cin >> a >> b;
    if (a != b) {
        std:: cout << (a >= b ? a : b) << '\n';
    }
    return 0;
}
```



## (2)

```c++
// kangshaojie
#include <iostream>
#include <string>
int main() {
    std:: string a , b;
    std:: cin >> a >> b;
    if (a.size() != b.size()) {
        std:: cout << (a.size() >= b.size() ? a : b) << '\n';
    }
    return 0;
}
```



# 3.5

## (1)

```c++
// kangshaojie
#include <iostream>
#include <string>
int main() {
    std:: string a , b;
    while (getline(std:: cin, b)) {
        a += b;
    }
    std:: cout<< a;
    return 0;
}
```



## (2)

```c++
// kangshaojie
#include <iostream>
#include <string>
int main() {
    std:: string a , b;
    while (getline(std:: cin, b)) {
        a += b;
        a += ' ';
    }
    std:: cout<< a;
    return 0;
}
```



# 3.20

## (1)

```c++
// kangshaojie
#include <iostream>
#include <string>
#include <vector>
int main() {
    std:: vector<int> My_vector;
    int a[10];
    for (int i = 0 ; i < 10 ; i++) {
        std:: cin >> a[i];
    }
    for (int j = 0 ; j < 10 ; j++) {
        My_vector.push_back(a[j]);
    }
    int sum[10];
    for (int k = 0 ; k < 10 ; k++) {
        sum[k] = My_vector[k] + My_vector[k+1];
        std:: cout << sum[k] << '\n';
        k++;
    }
    return 0;
}
```



## (2)

```c++
// kangshaojie

#include <iostream>
#include <string>
#include <vector>
int main() {
    std:: vector<int> My_vector;
    int a[10];
    for (int i = 0 ; i < 10 ; i++) {
        std:: cin >> a[i];
    }
    for (int j = 0 ; j < 10 ; j++) {
        My_vector.push_back(a[j]);
    }
    int sum[10];
    for (int k = 0 ; k < 5 ; k++) {
        sum[k] = My_vector[k] + My_vector[9-k];
        std:: cout << sum[k] << '\n';
        k++;
    }
    return 0;
}
```



# 3.23

```c++
// kangshaojie
#include<iostream>
#include<iterator>
#include<vector>
using std:: vector; using std:: iterator; using std:: cout; using std:: endl;
int mian() {
    vector<int> a(10, 1);
    for (auto b = a.begin(); b != a.end(); ++b)
        *b *= 2;
    for (auto value : a)
        cout << value << ' ';
    return 0;
}
```



# 6.10

```c++
// kangshaojie
#include<iostream>
#include<string>

int exchange(int &x[runtime] , int &y[runtime]) {
    int a;
    a = x;
    x = y;
    y = a;
    return 0;
}
int main() {
    int x , y;
    std:: cin >> x >> y;
    exchange(x , y);
    std:: cout << x << ' ' << y;
    return 0;
}
```



# 6.19

## (a) 不合法，因为函数只有一个参数，但传进了两个参数

## (b) 合法

## (c) 合法

 ## (d) 合法

# 6.39

## (a) 错误，重复声明

## (b) 错误

## (c) 正确

# 7.16

## 访问说明符的作用域是开始知道下一个访问说明符或者类结束。不想被使用该类的程序看到的代码细节，都要private.

# 7.27

## myScreen.move(4, 0).set('#').display(std::cout);

## //move()和display()函数可以相互调用，因为他们的返回值是对象的本身，该对象就是myScreen,move()和dispaly()函数对myScerrn执行不同的操作

# 7.49

## (a)合法 
## (b)不合法，Salesdata&类型与Salesdata类型之间不可转换 
## (c)不合法，const不对，因为combine本身是需要改变传入参数的

# 7.58

## rate不应该被声明为const对象，因为其是利率，但是实际情况中它也是可变的。而vec也不需要在类内就定义好大小，可以在另一个.h文件中声明大小。

