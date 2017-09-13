# Sort a linked list in O(n log n) time using constant space complexity.  
```
package SortList;

public class Solution148 {
	public ListNode sortList(ListNode head) {
		if(head==null||head.next==null){
			return head;
		}
		ListNode slow=head;
		ListNode fast=head;
		ListNode pre=null;
		//分两段的方法是使用 fast-slow 法，用两个指针，一个每次走两步，一个走一步，直到快的走到了末尾，
		//然后慢的所在位置就是中间位置，这样就分成了两段
		while(fast!=null&&fast.next!=null){
			pre=slow;
			slow=slow.next;
			fast=fast.next.next;
		}
		pre.next=null;
		ListNode l1=sortList(head);
		ListNode l2=sortList(slow);
		return merge(l1,l2);
	}
	public ListNode merge(ListNode l1,ListNode l2){
		ListNode dummy=new ListNode(0);
		ListNode curr=dummy;
		while(l1!=null&&l2!=null){
			if(l1.val>l2.val){
				curr.next=l2;
				l2=l2.next;
			}else{
				curr.next=l1;
				l1=l1.next;
			}
			curr=curr.next;
		}
		if(l1==null){
			curr.next=l2;
		}
		if(l2==null){
			curr.next=l1;
		}
		return dummy.next;
	}
}

```
归并排序是建立在归并操作上的一种有效的排序算法。该算法是采用分治法（Divide and Conquer）的一个非常典型的应用。

首先考虑下如何将将二个有序数列合并。这个非常简单，只要从比较二个数列的第一个数，谁小就先取谁，取了后就在对应数列中删除这个数。

然后再进行比较，如果有数列为空，那直接将另一个数列的数据依次取出即可。

解决了上面的合并有序数列问题，再来看归并排序，其的基本思路就是将数组分成二组A，B，
如果这二组组内的数据都是有序的，那么就可以很方便的将这二组数据进行排序。

如何让这二组组内数据有序了？

可以将A，B组各自再分成二组。依次类推，当分出来的小组只有一个数据时，可以认为这个小组组内已经达到了有序，
然后再合并相邻的二个小组就可以了。这样通过先递归的分解数列，再合并数列就完成了归并排序。

归并排序的效率是比较高的，设数列长为N，将数列分开成小数列一共要logN步，每步都是一个合并有序数列的过程，时间复杂度可以记为O(N)，故一共为O(N*logN)。
因为归并排序每次都是在相邻的数据中进行操作，所以归并排序在O(N*logN)的几种排序方法（快速排序，归并排序，希尔排序，堆排序）也是效率比较高的。
