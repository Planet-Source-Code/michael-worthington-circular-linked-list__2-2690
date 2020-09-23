<div align="center">

## Circular Linked List


</div>

### Description

The Circular Linked List class is created from scratch as well as uses its own Node class. It differs from the regular linked list because the last node points to the first node. CLL's are like arrays but have some differences. This is an excellent class for college students learning java.
 
### More Info
 
I threw in a main method to give a brief idea of how to use the CLL. The following is the output:

( )

( cool crazy punk )

true

false

( punk crazy cool )


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[michael worthington](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/michael-worthington.md)
**Level**          |Beginner
**User Rating**    |4.6 (23 globes from 5 users)
**Compatibility**  |Java \(JDK 1\.2\)
**Category**       |[Data Structures](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/data-structures__2-67.md)
**World**          |[Java](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/java.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/michael-worthington-circular-linked-list__2-2690/archive/master.zip)





### Source Code

```
public class CLL
{
  private class Node
  {
    Object data;
    Node next;
    public Node(Object data, Node next)
    {
      this.data = data;
      this.next = next;
    }
    public String toString()
    {
      return this.data.toString();
    }
  }
Node rear;
public CLL()
{rear = null;}
public String toString()
{
  if(rear==null)return "( )";
  Node temp = rear.next;
  String retval = "( ";
  do{
    retval= (retval + temp.data.toString() + " ");
    temp = temp.next;
    }while(temp!=rear.next);
  retval+=")";
  return retval;
}
public boolean isEmpty()
{return (rear==null);}
public void clear()
{rear=null;}
public void add(Object obj)
{
  Node temp = new Node(obj,null);
  if(rear==null)
  {
    temp.next = temp;
    rear = temp;
  }
  else
  {
    temp.next = rear.next;
    rear.next = temp;
  }
}
public Object delete()
{
  if(isEmpty())return "empty list";
  Object temp = rear.next.data;
  rear.next = rear.next.next;
  return temp;
}
public boolean find(Object target)
{
  if(isEmpty())return false;
  Node temp = rear.next;
  do{
    if(temp.data==target)return true;
    temp=temp.next;
    }while(temp!=rear.next);
  return false;
}
public void reverse()
{
  CLL temp = new CLL();
  Node temper = rear.next;
  if(isEmpty()){}
  else
  {
    do{
      temp.add(temper.data);
      temper = temper.next;
      }while(temper!=rear.next);
    rear = temp.rear;
  }
}
public static void main(String[] args)
{
  CLL x = new CLL();
  System.out.println(x);
  x.add("punk");
  x.add("crazy");
  x.add("cool");
  System.out.println(x);
  System.out.println(x.find("crazy"));
  System.out.println(x.find("lame"));
  x.reverse();
  System.out.println(x);
}
}
```

