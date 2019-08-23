## 例子
```
function A(){
    var _var = "Hello";

    function B(){
        return _val + " world";
    }

    return B;
}

let C = A();
console.log(C()); // Hello world
```

## 说明
```C``` 引用到函数B, ```C()``` 指向了 ```_var + "world"```, 当 GC 的时候，A 中的变量实际上被 C 所引用，A 不会被释放，这样，A 就可以常驻在内存中。

## 用处
1. _var 可以作为 A 内的私有变量，
2. A 常驻内存，可以在 A 内做缓存。

## 缺点
控制不好会影响程序性能，并且在某些时候闭包会让代码变得复杂。    
私有变量及缓存都可以通过其他方式来解决。
