```
public class Test {
	public static void main(String[] args) {
		LinkedList<String> list = new LinkedList<>();
		// LinkedList实现的接口：List<E>, Deque<E>, Cloneable, java.io.Serializable
		list.add("a");// Appends the specified element to the end of this list.
		list.add("b");
		list.add("c");
		list.forEach(x -> System.out.print(x + " "));
		System.out.println();
		String s=list.peek();//Retrieves, but does not remove, the head (first element) of this list.
		System.out.println(s);
		list.remove();// return the head of this list
		list.forEach(x -> System.out.print(x + " "));
		
//		int digit=Character.getNumericValue('2');
//		System.out.println(digit);
	}
}

输出结果：
a b c 
a
b c 
```
