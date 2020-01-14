# Data_Structures
Implementations of all data structure programmes

//Programme to Insert an element to a linked list at a given position using java
*********************************************************************************************
public class Main {
    public static void main(String args[]){
link l=new link();
l.add(1,9);
l.prin();
l.add(1,7);
        l.prin();
        l.add(2,4);
        l.prin();
        l.add(8,10);
        l.prin();
        l.add(1,3);
        l.prin();
        l.add(4,44);
        l.prin();
    }
}
class link{
    class node{
        int data;
        node next;
        public node(int d){
            data=d;
            next=null;
        }
    }
    node head=null;
    node tail=null;
    static int count=0;
    public void add(int p,int d){
        node n=new node(d);
        if(head==null){
            head=n;
            tail=head;
            count++;
        }
        else{
            if(p==1){
                n.next=head;
                head=n;
            }
            else if(p>=getSize()){
                tail.next=n;
                tail=n;
            }
            else{
                node temp=head;
                for(int i=1;i<p-1;i++){
                    temp=temp.next;
                }
                node aage=null;
                aage=temp.next;
                temp.next=n;
                n.next=aage;
            }
            count++;
        }
    }
    public int getSize(){
        return count;
    }
    public void prin(){
        node temp=head;
        while(temp!=null){
            System.out.print(temp.data+" ");
            temp=temp.next;
        }
        System.out.println();
    }

}
