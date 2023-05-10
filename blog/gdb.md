# GDB


### VSCode 在 Debug Console 执行 gdb 命令

VSCode 的 debug 控制台默认是直接打印变量的值，执行 gdb 命令需要加 `-exec` 前缀，例如

例如 
```sh
-exec set print object on
```


### 打印父类指针的具体子类类型

- 通过 typeid 函数
```sh
p typeid(*obj)
```

- 开启 print object

```sh
(gdb) whatis p
type = Shape &
(gdb) ptype p
type = class Shape {
  public:
    virtual void draw(void);
} &

(gdb) set print object on
(gdb) whatis p
type = /* real type = Circle & */
Shape &
(gdb) ptype p
type = /* real type = Circle & */
class Shape {
  public:
    virtual void draw(void);
} &
```


### gdb 调试技巧

https://github.com/hellogcc/100-gdb-tips
