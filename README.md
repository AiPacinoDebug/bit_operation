### javascript Bitwise acceleration techniques.
#### 1. If multiplied by a value of 2, you can use the left shift (Left Shift) to accelerate 300%.
```
x = x * 2;
x = x * 64;
```
**equals**:
```
x = x << 1; // 2 = 21
x = x << 6; // 64 = 26
```


#### 2. If in addition to the previous one of the multiple values, you can use the right shift operation to accelerate 350%.
```
x = x / 2;
x = x / 64;
```
**equals**:
```
x = x >> 1;// 2 = 21
x = x >> 6;// 64 = 26
```


#### 3. Incremental value by 10%.
```
x = int(1.232)
```
**equals**:
```
x = 1.232 >> 0;
```

#### 4. Exchange two values (swap), the use of XOR can accelerate 20%.
```
var t:
t = a;
a = b;
b = t;
```
**equals**:
```
a = a^b;
b = a^b;
a = a^b;
```

#### 5. Plus or minus conversion, you can add 300%.
```
i = -i;
```
**equals**:
```
i = ~i + 1; // NOT
```
**equals**:
```
i = (i ^ -1) + 1; // XOR
```

#### 6. Take the remainder, if the divisor is a multiple of 2, you can use the AND operation to speed up the 600%.
```
x = 131 % 4;
```
**equals**:
```
x = 131 & (4 - 1);
```

#### 7. Use the AND operation to check whether the integer is a multiple of 2, can accelerate 600%.
```
isEven = (i % 2) == 0;
```
**equals**:
```
isEven = (i & 1) == 0;
```

#### 8. Accelerated Math.abs 600% of the written 1, writing 2 than the wording 1 to accelerate 20%.
```
i = x < 0 ? -x : x;
```
**equals**:
```
i = (x ^ (x >> 31)) - (x >> 31);
```
**equals**:
```
i=x^(~(x>>31)+1)+(x>>31);
```


#### 9. Compare the two values after the multiplication of whether the same symbol, to accelerate 35%.
```
eqSign = a * b > 0;
```
**equals**:
```
eqSign = a ^ b > 0;
```

#### 10. RGB color separation.
```
var bitColor = 0xff00cc;
var r = bitColor >> 16;
var g = bitColor >> 8 & 0xFF;
var b = bitColor & 0xFF;
```


#### 11. RGB color merge
```
var r = 0xff;
var g = 0x00;
var b = 0xcc;
var bitColor:uint = r << 16 | g << 8 | b;
```