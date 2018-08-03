package MaxHeap;

import java.util.Arrays;

public class MaxHeap {

    Integer[] data;
    private int size;
    private int heapsize;

    public MaxHeap(int n) {//null constructor
        size = n;
        heapsize = 0;
        data = new Integer[n];
    }

    public MaxHeap(Integer[] someArray) { //running time is n*log n average, memory is n
        size = someArray.length + 1;
        heapsize = 0;
        data = new Integer[size];

        if (someArray.length > 0) {
            for (int i = 0; i < someArray.length; i++) {//running time is n
                insert(someArray[i]);
            }
        }
    }

    public void insert(int n) {//running time is big theta log n average, memory is big theta 1 average
        int current = heapsize + 1;
        if (current >= size) {//running time is n, memory is n if called
            Integer[] data2 = new Integer[2 * size];//if resize needed before inserted into heap
            for (int i = 0; i < size; i++) {
                data2[i] = data[i];
            }
            data = data2;
            size = data.length;
        }
        data[current] = n;
        System.out.println("after insert:");

        while (current > 1 && data[current / 2] < data[current]) {//log n running time //compares current node to its parent node in the heap to determine propoer placement in the heap
            int temp = data[current / 2];
            data[current / 2] = data[current];
            data[current] = temp;

            current /= 2;
        }
        System.out.println("after proper positioning:");
        levelOrder();
        heapsize++;
    }

    public int deleteMax() {
        if (heapsize == 0) {
            return -1;
        } else {
            int max = data[1];
            System.out.println("heapsize: "+heapsize);
            System.out.println("Max: " + data[1]);
            if(heapsize<=4&&heapsize>2){
                for(int i=1;i<heapsize;i++){
                    data[i]=data[i+1];
                }
                System.out.println("Max replaced with: " + data[1]);
                data[heapsize] = null;
                --heapsize;
            }
            else{
            data[1] = data[heapsize];
            System.out.println("Max replaced with: " + data[1]);
            data[heapsize] = null;
            --heapsize;
      
            for (int i = 1; i <= heapsize; i *= 2) {
                System.out.println("i: "+i);
                    if (i * 2 < heapsize && data[i] < data[i * 2] && data[i] > data[i * 2 + 1]) {
                        System.out.println("swap with left child");
                        int temp = data[i * 2];
                        data[i * 2] = data[i];
                        data[i] = temp;
                    } else if (i * 2 + 1 < heapsize && data[i] < data[i * 2+1] && data[i] >data[i * 2]) {
                        System.out.println("swap with right child");
                        int temp = data[i * 2 + 1];
                        data[i * 2 + 1] = data[i];
                        data[i] = temp;
                    } else if ((i * 2 < heapsize && data[i * 2] > data[i])&&(i * 2 + 1 < heapsize && data[i * 2+1] > data[i])) {
                        System.out.println("both children are greater than parent so swap with bigger child");
                        if (data[i * 2] > data[i * 2 + 1]) {
                            int temp = data[i * 2];
                            data[i * 2] = data[i];
                            data[i] = temp;
                        } else {
                            int temp = data[i * 2 + 1];
                            data[i * 2 + 1] = data[i];
                            data[i] = temp;
                        }
                    }
                    else if(data[i*2]==null||data[i*2+1]==null){
                        break;
                    }
                    levelOrder();
                }
            }
            return max;
        }
    }

    public String toString() {
        String output = new String();

        for (int i = 1; i <= heapsize; i++) {
            output += data[i];
        }
        return output;
    }

    public void levelOrder() {//running time is n*log n
        for (int i = 0; i < heapsize; i++) {
            for (int j = (int) Math.pow(2, i); j < Math.pow(2, i + 1) && j <= heapsize; j++) {//runs only until the next power of 2
                if (data[j] != null) {
                    System.out.print(data[j] + " ");//adds number to same line
                }
            }
            System.out.println();//new line after all numbers are done on the same level
        }
    }

    public static void heapsort(Integer[] arrayToSort) {//running time is n*log n, memory is 1
        MaxHeap temp = new MaxHeap(arrayToSort);//create new MaxHeap object from arrayToSort
        for (int i = 0; i < arrayToSort.length; i++) {//repeatedly call deleteMax to heapsort array
            arrayToSort[i] = temp.deleteMax();
        }
    }
    public static void testheapsort(Integer[] arrayToSort) {
        MaxHeap temp = new MaxHeap(arrayToSort);
        System.out.println("prior to heapsort: "+Arrays.toString(arrayToSort));
        for (int i = 0; i < arrayToSort.length; i++) {
            
            arrayToSort[i] = temp.deleteMax();
            System.out.println("deleted value: "+arrayToSort[i]);
            System.out.println("arrayToSort: "+Arrays.toString(arrayToSort));
            temp.levelOrder();
        }
    }

    public int getSize() {
        return size;
    }

    public int getHeapSize() {
        return heapsize;
    }
}
