# 交换数值
1. 第一种
    ```
    function swapNumber(a, b){
        b = b - a;
        a = a + b;
        b = a - b;
    }
    ```
2. 第二种
    ```
    function swapNumber(a, b){
        a = a ^ b;
        b = a ^ b;
        a = a ^ b;
    }
    ```
# 去重
执行循环，并保存一个对象/关联数组；
如果第一次找到一个元素，会设置它的值为真（将元素添加一次）,
如果在对象中找到这个元素，不会将它插入到返回的数组中。
```
function removeDuplicate(arr){
    var exists = {};
    var outArr = [];
    var elm;

    for(var i = 0; i < arr.length; i++){
        elm = arr[i];

        if(!exists[elm]){
            outArr.push(elm);
            exists[elm] = true;
        }
    }

    return outArr;
}
```
# 合并数组
为每个数组保留一个指针
```
function mergeSortedArray(a, b){
    var merged = [];
    var aElm = a[0];
    var bElm = b[0];
    var i = 1;
    var j = 1;

    if(a.length === 0){
        return b;
    }

    if(b.length === 0){
        return a;
    }

    while(aElm || bElm){
        if((aElm && !bElm) || aElm < bElm){
            merged.push(aElm);
            aElm = a[i++];
        }else{
            merged.push(bElm);
            bElm = b[j++];
        }
    }

    return merged;
}
```
# 斐波那契
1. 第一种：创建一个数组并从迭代开始
    ```
    function fibonacci(n){
        var fibo = [0, 1];
    
        if(n <= 2){
            return 1;
        }
    
        for(var i = 2; i <= n; i++){
           fibo[i] = fibo[i-1] + fibo[i - 2];
        }
    
        return fibo[n];
    }
    ```
2. 第二种：递归
    ```
    function fibonacci(n){
        if(n <= 1){
            return n;
        }else{
            return fibonacci(n - 1) + fibonacci(n - 2);
        }
    }
    ```
# 最大公约数
1. 第一种
    ```
    function greatestCommonDivisor(a, b){
        var divisor = 2;
        var greatestDivisor = 1;
    
        if(a < 2 || b < 2){
            return 1;
        }
    
        while(a >= divisor && b >= divisor){
            if(a % divisor === 0 && b % divisor === 0){
                greatestDivisor = divisor;
            }
    
            divisor++;
        }
    
        return greatestDivisor;
    }
    ```
2. 第二种：算法范式
    ```
    function greatestCommonDivisor(a, b){
        if(b === 0){
            return a;
        }else{
            return greatestCommonDivisor(b, a % b);
        }
    }
    ```
# 素数
1. 第一种
素数只能被1和本身整除
while循环并加1
    ```
    function isPrime(n){
        var divisor = 2;
    
        while(n > divisor){
            if(n % divisor === 0){
                return false
            }else{
                divisor++;
            }
        }
    
        return true
    }
    ```
2. 第二种
除数一次增加1，在3之后可以增加2
如果一个数可以被任何偶数整除，它将被2整除
一个数字不能被大于其一半的数字整除
一个数字可以被其三分之一的数字整除
除数将小于math.sqrt(N)
    ```
    function isPrime(n){
        var divisor = 3;
        var limit = Math.sqrt(n);
    
        if(n === 2 || n === 3){
            return true
        }
    
        if(n % 2 === 0){
            return false
        }
    
        while(divisor <= limit){
            if(n % divisor === 0){
                return false
            }else{
                divisor+=2;
            }
        }
    
        return true
    }
    ```
# 素数因子
执行while循环，开始除以2，如果不能整除，记录这个除数，直到完成
```
function primeFactors(n){
    var factors = [];
    var divisor = 2;

    while(n > 2){
        if(n % divisor === 0){
            factors.push(divisor);
            n = n / divisor;
        }else{
            divisor++;
        }
    }

    return factors;
}
```