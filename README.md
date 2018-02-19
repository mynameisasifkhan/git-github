# git-githubpackage Linked_List;

import Linked_List.identical_linkedlist.ListNode;

public class Sorting_two_linkedlist {
	public ListNode head,head1;
	public static class ListNode
	{
		int data;
		ListNode next;
		public ListNode(int data)
		{
			this.data=data;
			this.next=null;
		}
	}
	public static ListNode merge(ListNode head,ListNode head1)//sorting node is used to point element having lesser value
	{
		ListNode sorting=null;
		ListNode newhead=null;
		if(head==null)
			return head1;
		if(head1==null)
			return head;
		if(head!=null && head1!=null)
		{
			if(head.data<=head1.data){
				sorting=head;
			head=sorting.next;}
			else
			{
				sorting=head1;
			head1=sorting.next;
			}
		}
		newhead=sorting;
		while(head!=null && head1!=null)
		{
			if(head.data<=head1.data)
			{
				sorting.next=head;
				sorting=head;
				head=sorting.next;
			}
			else
			{
				sorting.next=head1;
				sorting=head1;
				head1=sorting.next;
			}
		}
		if(head==null)
			sorting.next=head1;
		if(head1==null)
			sorting.next=head;
		return newhead;
	}
	 public static void display(ListNode head)//method for printing element of linked list...
	 {
		 if(head==null)
			 return;
		 ListNode current=head;
		 while(current!=null)
		 {
			 System.out.print(current.data+"-->");
			 current=current.next;
		 }
		 System.out.println("null");
	 }
	

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		ListNode head=new ListNode(2);
		ListNode second=new ListNode(5);
		ListNode third=new ListNode(8);
		ListNode fourth=new ListNode(8);
		head.next=second;
		second.next=third;
		third.next=fourth;
		ListNode head1=new ListNode(4);
		ListNode second1=new ListNode(6);
		ListNode third1=new ListNode(9);
		ListNode fourth1=new ListNode(10);
		head1.next=second1;
		second1.next=third1;
		third1.next=fourth1;
		Sorting_two_linkedlist list=new Sorting_two_linkedlist();
		ListNode node=list.merge(head,head1);
		list.display(node);

	}

}
