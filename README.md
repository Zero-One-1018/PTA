习题7-3 判断上三角矩阵 (15分)
上三角矩阵指主对角线以下的元素都为0的矩阵；主对角线为从矩阵的左上角至右下角的连线。

本题要求编写程序，判断一个给定的方阵是否上三角矩阵。
输入格式：
输入第一行给出一个正整数T，为待测矩阵的个数。接下来给出T个矩阵的信息：每个矩阵信息的第一行给出一个不超过10的正整数n。随后n行，每行给出n个整数，其间以空格分隔。

输出格式：
每个矩阵的判断结果占一行。如果输入的矩阵是上三角矩阵，输出“YES”，否则输出“NO”。
输入样例：
2
3
1 2 3
0 4 5
0 0 6
2
1 0
-8 2
输出样例：
YES
NO


做题思路：
/*此题对于我来说有一个最大的难点，就是T个矩阵；我刚开始以为使用结构体，但技术还没到家；但我想到了可以使用for循环，几个矩阵就循环几次；其次就是理解什么是上三角矩阵；将其规律找到；当其行数大于列数时，如果存在元素为0；则输出NO;否则输出YES;*/


代码如下：
#include <stdio.h>
int main()
{
	int T;
	int i,j,k;
	scanf("%d",&T);//T个矩阵；
	for(i=0;i<T;i++)//一个矩阵一个循环；
        {
		int n;
		int flag=1;
		scanf("%d",&n);
		int str[n][n];
		for( j=0;j<n;j++){
			for( k=0;k<n;k++){
				scanf("%d",&str[j][k]);//读入元素；
			}
		}
		for(j=0;j<n;j++){
			for(k=0;k<n;k++){
				if(j>k&& str[j][k]!=0) flag=0;//上三角矩阵判断；
			} 
		}
		if(flag== 1) printf("YES\n");
		else if (flag==0) printf("NO\n");//输出；
		
	} 
	return 0;
 } 


