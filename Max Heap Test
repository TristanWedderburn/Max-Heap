package MaxHeap;

import static MaxHeap.MaxHeap.testheapsort;

public class TestMaxHeap {
    public static void main(String[] args) {
        Integer[] test1={1,2,3,4,5,6,7,8,9};
        MaxHeap heap1= new MaxHeap(test1);
        System.out.println("constructor test:");
        System.out.println("unsorted constructor:");
        heap1.levelOrder();
        
        System.out.println("\nheapsort test:");
        testheapsort(test1);
        
        MaxHeap heap2= new MaxHeap(test1);
        
        System.out.println("\nheap after heapsort:");
        heap2.levelOrder();
        
        System.out.println("\ntest insert:");
        heap1.insert(10);
        heap1.levelOrder();
        
        System.out.println("\ntest deleteMax:");
        heap1.deleteMax();
    }
}
