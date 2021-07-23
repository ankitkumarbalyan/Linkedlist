// create a class of singly linked list 
public class LinkedList
{   // Create a ListNode head
    private ListNode head;
    private static class ListNode{
        private int data; // declare data variable 
        private ListNode next; // declare next pointer 
        // create a constructor 
        public ListNode(int data){
            this.data=data;
            this.next=null;
        }
    }
    // create a method to display the node of linked list
    public void display(){
        ListNode current=head;
        while(current!=null){

            System.out.print(current.data+"->");
            current=current.next;
        }
        System.out.println("null");
    }
    // method to find the length of a singly linked list
     public int findLength(){
        int count=0;
        ListNode current=head;
        while(current!=null){
            count++;
            current=current.next;
        }
        return count;
    }
    // method to insert a node at beginning of a singly linked list
    public void insertFirst(int value){
        ListNode newNode=new ListNode(value);
        newNode.next=head;
        head=newNode;
    }
    // method to insert at last in singly linked list
    public void insertLast(int value){
        ListNode newNode=new ListNode(value);
        if(head==null){
            head=newNode;
            return;
        }
    
        ListNode current=head;
        while(current.next!=null){
            current=current.next;
        }
        current.next=newNode;

        
    }
    // method to delete first node in a list 
    public ListNode deleteFirst(){
        if(head==null){
            return null;
        }
        ListNode temp =head;
        head=head.next;
        temp.next=null;
        return temp;
    }
    // delete a last node in a linked list
    public ListNode deleteLast(){
        if(head==null || head.next==null){
            return head;
        }
        ListNode current=head;
        ListNode previous=null;
        while(current.next!=null){
            previous=current;
            current=current.next;
        }
         previous.next=null;
         return current;
    }
    // method to check is given element is present or not 
    public boolean isFind(int searchKey){
        ListNode current=head;
        while(current!=null){
        if(current.data==searchKey){
            return true;
        }
        current=current.next;
    }
    return false;
}
// method to check given element is present and print that data
 public int findData(int searchKey){
        ListNode current=head;
        while(current!=null){
        if(current.data==searchKey){
            return current.data;
        }
        current=current.next;
    }
    return -1;
}


    // main method 
    public static void main(String[] args) {
        // create object of LinkedList class 
        LinkedList sll=new LinkedList();
        // create  head node ,first node ,second node ,third node and fourth node 
        sll.head= new ListNode(10);
        ListNode second=new ListNode(5);
        ListNode third=new ListNode(7);
        ListNode fourth=new ListNode(9);
        // link the all node using next pointer
        sll.head.next=second;
        second.next=third;
        third.next=fourth;
        sll.display();
        sll.insertFirst(3);
        sll.insertFirst(2);
        sll.display();
        sll.insertLast(5);
        sll.insertLast(6);
        sll.display();
        sll.deleteFirst();
        sll.display();
        sll.deleteLast();
        sll.display();
        
        sll.display();
        
        System.out.println(sll.findLength());
        if (sll.isFind(1)){
            System.out.print("found and data is ");
        }
        else{
            System.out.print("not found ");
        }
      
        System.out.println(sll.findData(1));
      

		
	}
}
