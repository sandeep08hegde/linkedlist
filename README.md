//linkedlist
#include <stdio.h>
#include<stdlib.h>
#include<string.h>
 struct node
{
    int idata;
    char cdata[6];
    struct node*link;
    
};
typedef struct node NODE;
NODE* getdata();
int main()
{
 NODE *first=NULL;
 NODE *second,*third,*temp;
 first=getdata();
 first->idata=12;
 strcpy(first->cdata,"CAT");
 first->link=NULL;
 second = getdata();
 second->idata=56;
 strcpy(second->cdata,"GOT");
 first->link=second;
 third=getdata();
 third->idata=46;
 strcpy(third->cdata,"BAT");
 third->link=NULL;
 second->link=third;
 for( temp=first;temp!=NULL;temp=temp->link)
 printf("%d%s ",temp->idata,temp->cdata);
 return 0;
}

NODE* getdata()
{
    NODE *temp;
    temp=(NODE*)malloc(sizeof(NODE));
    if(temp==NULL)
     {
         printf("no memory\n");
         return NULL;
         
     }
     return temp;
     
}
