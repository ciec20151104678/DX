#include<stdio.h>
#include<stdlib.h>
#include<string.h>
int main()
{
	FILE  *fp1;
	char *text;
	int len;
	fp1=fopen("export.gpx","r+");
	if((fp1 =fopen("export.gpx","r+"))==0) 
	{
		printf("文件读取错误");
		return (-1);
	}
	fseek(fp1,0,SEEK_END);
	len=ftell(fp1);
	text=(char*)malloc(len);
	printf("length=%d\n",len);
	fseek(fp1,0,0);
	fread(text,1,len,fp1);
	printf("%s\n",text);
	free(text);
	return 0;
} 
