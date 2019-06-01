返回数据解析
-----

协议头: 0x55 , 位置:0
未知数据: 位置: 2  
数据类型:  位置:3


m.c(str)
---
```java
public static int a(CharSequence charSequence, int defaultValue) {
        if (!TextUtils.isEmpty(charSequence)) {
            try {
                i = Integer.parseInt(charSequence.toString());
            } catch (NumberFormatException e) {
            }
        }
        return i;
}
```



IR_BATTERY_DATA 电量信息 
----
数据包要求最少5位

电量 位置:4 方法: byteToInt(arr[4])

IR_TH_DATA  温湿度信息    
----
数据包要求最少8位

temperature: 温度 位置:4,5 方法:parese(4 ,2)
humidity: 湿度 位置:6,7 方法: parese(6 ,2)

解析方法:

```java
public void int parese(byte[] arr, int index, int length) {
	//索引
	int i = 0; 
	//数据长度
	int l = index + length > arr.length ? arr.length - 1 : length;
	
	if (l < 0) {
       l = 0;
    }
	
	int res = 0;
	while(i < l) {
		res |= byteToInt(arr[i + index]) << (i * 8)
	}


}

public static int byteToInt(byte b) {
        return b & 255;
    }

```