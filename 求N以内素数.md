厄拉多筛选法选取素数的核心在于避开第上次循环中已经证伪的数。

例如创建一个大小为N的数组，循环遍历第一遍，取2和k=2++,排除了所有的小于N的2的倍数，第二遍，取3和2++，排除了3倍数……

```java
public int countPrimes(int n) {
     boolean []flagArray = new boolean[n];`
     for (int i=2; i<n; i++){
    	 flagArray[i] = true;
     }

 for (int i=2; i<n; i++){
	 if (flagArray[i]){
		 for (int k=2; k*i<n; k++){
			 flagArray[k*i] = false;
		 }
	 }
 }
 
 int result = 0;
 for (int i=2; i<n; i++){
	 if (flagArray[i]){
		 result++;
	 }
 }
 
 return result;
}
```

