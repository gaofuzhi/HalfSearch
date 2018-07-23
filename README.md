# HalfSearch

package test;
/*
 * 折半查找算法
 * 每次取一半的中间数进行比较
 * (前提：原数组已经排好序(升序或降序))
 * 注意事项：当给   lastIndex = midIndex-1;
 * 				firstIndex = midIndex+1;
 * 赋值的时候  只要后面有加减1的时候(一定要加，不然数组中没这个数的时候，无法跳出循环(死循环))
 * 当找不到这个数的时候  最后一定会有： firstIndex > lastIndex	
 */
public class HalfSearch {
	public static void main(String[] args) {
		//需要查找的数
		int num = 3;
		//被查找的数组
		int[] arr = new int[]{1,3,7,9,11,77,78,79};
		//下标				  	
		int midIndex = 0;
		int firstIndex = 0;
		int lastIndex = arr.length;
		boolean flag = false;
		//折半算法
		while(flag==false&&firstIndex<=lastIndex){
			midIndex = (firstIndex+lastIndex)/2;
			if(num==arr[midIndex]){
			System.out.println("找到了您要找的数！它的下标是："+midIndex);
			flag = true;
			}
			if(num<arr[midIndex]){
				lastIndex = midIndex-1;
				}
			if(num>arr[midIndex]){
				firstIndex = midIndex+1;
			}			
		}
			//用arr[midIndex]判断值是否相等也可以
			if(flag==false){
				System.out.println("sorry,i can’t found it!");
			}
	}
}
