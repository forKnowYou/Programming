# 编程规范

C语言 Arduino封库编程规范

## 索引
* [简介](#简介)
* [变量及函数命名](#变量及函数命名)
* [宏](#宏)
* [枚举](#枚举)
* [类](#类)
* [缩进](#缩进)
* [{}](#{})
* [if-else](#if-else)
* [switch-case](#switch-case)
* [运算符](#运算符)
* [Readme中多个参数函数写法](#readme中多个参数函数写法)
* [ino文件头部写法](#ino文件头部写法)

## 变量及函数

*首字母小写, 下个单词首字母大写
*专有名词要大写

正确的写法

```C++
int sensorValue;
int SDCard,IIS,I2C;
```

错误的写法

```C++
int sensor_value;
float sensorvalue;
byte sensor_Value;
```

## 宏

所有字母都要大写
正确的写法
```C++
#define MAX 1000
#define SENSOR_REG1 1
```

错误的写法：
```C++
#define Max 1000
#define sensorReg1 1
```

## 枚举

前面要加e，后面首字母大写
```C++
enum eDAY
{
  eSunday=0,
  eMonday,
  eTuesday,
  eWednesday,
  eThursday,
  eFriday,
  eSaturday,
}
```

## 类

以DFRobot_开头,后面接ClassName,ClassName首字母要大些
正确的写法
```C++
class DFRobot_SIM7000;
class DFRobot_BME280;
class DFRobot_Lora;
```
错误的写法
```C++
class DFRobot_sim7000;
class Lora;
class DFRobotLora;
```

## 缩进

全部使用空格缩进，不要使用tab缩进（除了特殊用途，比如keywords makefile里），请用notepad++检查

## {}
在函数中，{}顶格写，例如

```C++
void func()
{
  //do something
}
```

## if-else

{写在语句后面，}写在新行,这样很方便调试。例如
```C++
if(conditon1){
  //do something
}else if(conditon2){
  //do something
}else{
  //do something
}
```

## switch-case

case与switch对其，{跟在switch语句后面，例如
```C++
switch(value){
case x:
  //do something
case y:
  //do something
default:
  //do something
}
```

## 运算符

前后需要留空格(此条根据具体情况，不强制)

```C++
for(int x = 0; x <= 10; x++)
```

## Readme中多个参数函数写法
采用doxygen注释规则描述参数

```C++
    /*!
     *  @brief Set operational mode to VL53L0X
     *
     *  @param mode  Work mode settings
     *      Single : Single mode
     *      Continuous : Back-to-back mode
     *  @param precision  Set measurement precision
     *      High：High precision(0.25mm)
     *      Low: Low precision(1mm)
     *  @return  true if execute successfully, false otherwise.
     */
    bool setMode(uint8_t mode, uint8_t precision);
```

## ino文件头部写法
```C++
 /*!
  * file 文件名（不能使用中文）
  * 如何做这个实验（不能使用中文）
  * @n 实验现象是什么（不能使用中文）
  *
  * Copyright   [DFRobot](http://www.dfrobot.com), 2016
  * Copyright   GNU Lesser General Public License
  *
  * version  V1.0
  * date  2017-10-9
  */
  ```
