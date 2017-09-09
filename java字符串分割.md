public String [] split (String  regex, int limit) 
看下说明limit 参数控制模式应用的次数，因此影响所得数组的长度。
如果该限制 n 大于 0，则模式将被最多应用 n  - 1 次，数组的长度将不会大于 n ，而且数组的最后一项将包含所有超出最后匹配的定界符的输入。
如果 n 为非正，那么模式将被应用尽可能多的次数，而且数组可以是任何长度。
如果 n 为 0，那么模式将被应用尽可能多的次数，数组可以是任何长度，并且结尾空字符串将被丢弃。
而对于函数 public String [] split (String  regex)该方法的作用就是使用给定的表达式和限制参数 0 来调用两参数 split方法。
```
public class Test {
	public static void main(String[] args) {
		String s=":a:b:c::d:e:f:";
		for(String str:s.split(":")){
			System.out.print(str+"-");
		}
		System.out.println();
		for(String str:s.split(":",-1)){
			System.out.print(str+"-");
		}
		System.out.println();
		for(String str:s.split(":",3)){
			System.out.print(str+"-");
		}
	}
}
输出：
-a-b-c--d-e-f-
-a-b-c--d-e-f--
-a-b:c::d:e:f:-
```
