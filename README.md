# ruiruirui
C语言


// struct no.1 (直接定义输出结果)
#include <stdio.h>
#define N 100
#define M 3


 


int main()
{
    typedef struct student
    {
        int studentID;
        char studentName[N];
        char studentSex;
        int yearOfbirth;
        float score[M];
    }STU;
    
    STU s1 = {20014127,"lvqingrui",'M',2002,95,85,95};
    STU s2 = {20020507,"cuoguojiusuanleba",'F',2002,{100,100,100}};
    
    printf("第一个同学的学号，姓名，性别，出生年份，平时成绩，期中成绩，期末成绩:\n");
    printf("%d,%s,%c,%d,%f,%f,%f\n",s1.studentID,s1.studentName,s1.studentSex,s1.yearOfbirth,s1.score[0],s1.score[1],s1.score[2]);
    
    printf("第二个同学的学号，姓名，性别，出生年份，平时成绩，期中成绩，期末成绩:\n");
    printf("%d,%s,%c,%d,%f,%f,%f\n",s2.studentID,s2.studentName,s2.studentSex,s2.yearOfbirth,s2.score[0],s2.score[1],s2.score[2]);
    
    return 0;
}
 */

//struct no.2(从键盘中输入和输出) 并使用嵌套

/*
#include <stdio.h>
#define M 100
#define N 3

int main()
{
    typedef struct date
    {
        int year;
        int month;
        int day;
    }DATE;
    
    
    typedef struct student
    {
        int studentID;
        char studentName[M];
        char studentSex;
        DATE birthday;
        float score[N];
        
    }STU;
    STU s1;
    int i,j;
    for(i=0;i<1;i++)
        printf("请输入第%d同学的学号，姓名，性别，出生年份，平时成绩，期中成绩，期末成绩:\n",i+1);
        scanf("%d,%s,%c,%d,%d,%d\n",&s1.studentID,s1.studentName,&s1.studentSex,&s1.birthday.year,&s1.birthday.month,&s1.birthday.day);
    }
    getchar();
    for(j=0;j<3;j++)
    {
        scanf("%f",&s1.score[j]);
        getchar();
    }
    printf("%d,%s,%c,%d,%d,%d,%f,%f,%f\n",s1.studentID,s1.studentName,s1.studentSex,s1.birthday.year,s1.birthday.month,s1.birthday.day,s1.score[0],s1.score[1],s1.score[2]);
    
}
 
 */

//struct no.3  结构体数组

#include <stdio.h>
#define M 100
#define N 3
#define B 50


int main()
{
typedef struct date
{
    int year;
    int month;
    int day;
}DATE;


typedef struct student
{
    int studentID;
    char studentName[M];
    char studentSex;
    DATE birthday;
    float score[N];
    
}STU;
    STU s[B];
    int n,i,j;
    printf("请输入实际人数n：\n");
    scanf("%d",&n);
    for (i=0; i<n; i++) {
        printf("请输入第%d同学的学号，姓名，性别，出生年份，平时成绩，期中成绩，期末成绩:\n",i+1);
        scanf("%d",&s[i].studentID);
        scanf("%s",s[i].studentName);
        getchar();
        scanf("%c",&s[i].studentSex);
        scanf("%d %d %d",&s[i].birthday.year,&s[i].birthday.month,&s[i].birthday.day);
        getchar();
        for (j=0; j<3; j++) {
            scanf("%f",&s[i].score[j]);
        }
    
    }
   
    for (i=0; i<n; i++) {
        printf("第%d个人的成绩为：\n",i+1);
        printf("%d,%s,%c,%d,%d,%d\n",s[i].studentID,s[i].studentName,s[i].studentSex,s[i].birthday.year,s[i].birthday.month,s[i].birthday.day);
        for (j=0; j<3; j++) {
            printf("%.2f",s[i].score[j]);
        }
    }
}



