package first;

public class Wuhanjiayou {
	public static void main(String[] args) {
		//wu*han=jia*you
		//0w 1u 2h 3a 4n 5j 6i 7y 8o
		int[]list = {1,1,1,1,1,1,1,1,1};
		boolean exist=true;
		boolean repeat=false;
		while(exist) {
			int k=repeat(list);
			if(k==-1) {
				if(check(list)==true)
					sysout(list);
			}
					k=0;
			if(k!=-1) {
				list[k]++;
				change(list);
			}
			if(list[list.length-1]>9)
				exist=false;
		}
		
	}
	public static int repeat(int[] list) {
		for(int a=0;a<list.length-1;a++)
		{
			for(int b=a+1;b<list.length;b++)
			{
				if(list[a]==list[b])
				{
					return a;
				}
			}
		}
		return -1;
	}
	public static boolean check(int[] list) {
		if((10*list[0]+list[1])*(100*list[2]+10*list[3]+list[4])==(100*list[5]+10*list[6]+list[3])*(100*list[7]+10*list[8]+list[1])) {
			int[] alist=new int[5];
			for(int a=0;a<alist.length;a++) {
				alist[a]=(int) ((10*list[0]+list[1])*(100*list[2]+10*list[3]+list[4])/(Math.pow(10,4-a))%10);
				if(alist[a]==0)
					return false;
			}
			return true;
		}
		return  false;
	}
	public static int[] change(int[] list) {
		int[] alist=list;
		for(int a=0;a<alist.length-1;a++) {
			if(alist[a]>9) {
				alist[a]=1;
				alist[a+1]++;
			}
		}
		return alist;
	}
	public static void sysout(int[] list) {
		System.out.println((10*list[0]+list[1])+"*"+(100*list[2]+10*list[3]+list[4])+"=="+(100*list[5]+10*list[6]+list[3])+"*"+(100*list[7]+10*list[8]+list[1]));
	}
}
