# tushuguanli
#include <iostream>
#include <iomanip>
#include <string.h>
#include <fstream>
#include<cstdlib>
using namespace std;

int count1=0;//纸质书总数 
int count2=0;//电子书总数 
int count3=0;//论文总数
int count4=0;//用户总数

class pbook//纸质书
{
private:
	string name; //书名 
	string author;//作者 
	string id;//编号 
	string publisher;//出版社 
	int tab;//出借状态（1为在库，0为借出） 
	string path;//文件路径 
	
public:
	 pbook() {} 
	 pbook(string name_,string author_,string id_,string publisher_,string path_, int tab_ = 1)
	  {
		name = name_;
		author = author_;
		id = id_;
		publisher = publisher_;
		path = path_;
		tab = tab_;
  	  } 
  	void getname() {cin>>name;}
	string returnname() {return name;}
		 
	void getauthor() {cin>>author;}
	string returnauthor() {return author;}
		 
    void getid() {cin>>id; }
	string returnid() {return id;}
		 
	void getpublisher() {cin>>publisher;}
	string returnpublisher() {return publisher;}
		 
	void getpath() {cin>>path;}
	string returnpath() {return path;}
	
	void addpbook()
		{
			cout<<"请输入你要录入的纸质书的书名："<<endl;
			getname();
			cout<<"请输入该书作者："<<endl;
			getauthor();
			cout<<"请输入该书编号："<<endl;
			getid();
			cout<<"请输入该书出版社："<<endl;
			getpublisher();
			cout<<"请输入该书路径："<<endl;
			getpath();
			tab=1;
			count1++;
			string a=returnid();
			a = a + ".txt";
			ofstream file(a.c_str(),ios::out|ios::app);
			file<<returnname()<<endl;
			file<<returnauthor()<<endl;
			file<<returnpublisher()<<endl;
			file<<returnid()<<endl;
			file<<returnpath()<<endl;
			file.close();
		}		 
		~pbook() {}
 } ;
 
 class ebook//电子书 
{
private:
	string name; //书名 
	string author;//作者 
	string id;//编号 
	string publisher;//出版社 
	string path;//文件路径 

public:
	 ebook() {} 
	 ebook(string name_,string author_,string id_,string publisher_,string path_)
	  {
		name = name_;
		author = author_;
		id = id_;
		publisher = publisher_;
		path = path_;
  	  } 
  	void getname() {cin>>name;}
	string returnname() {return name;}
		 
	void getauthor() {cin>>author;}
	string returnauthor() {return author;}
		 
    void getid() {cin>>id; }
	string returnid() {return id;}
		 
	void getpublisher() {cin>>publisher;}
	string returnpublisher() {return publisher;}
		 
	void getpath() {cin>>path;}
	string returnpath() {return path;}
	
	void addebook()
		{
			cout<<"请输入你要录入的电子书的书名："<<endl;
			getname();
			cout<<"请输入该书作者："<<endl;
			getauthor();
			cout<<"请输入该书编号："<<endl;
			getid();
			cout<<"请输入该书出版社："<<endl;
			getpublisher();
			cout<<"请输入该书路径："<<endl;
			getpath();
			string a=returnid();
			count2++;
			a = a + ".txt";
			ofstream file(a.c_str(),ios::out|ios::app);
			file<<returnname()<<endl;
			file<<returnauthor()<<endl;
			file<<returnpublisher()<<endl;
			file<<returnid()<<endl;
			file<<returnpath()<<endl;
			file.close();
		}		 
		~ebook() {}
 } ;
 
 class paper
 {
 	private:
	string name; //标题 
	string author;//作者 
	string id;//编号 
	string publication;//刊物
	string time;//时间 
	string path;//文件路径 

public:
	 paper() {} 
	 paper(string name_,string author_,string id_,string publication_,string time_,string path_)
	  {
		name = name_;
		author = author_;
		id = id_;
		publication = publication_;
		time = time_;
		path = path_;
  	  } 
  	void getname() {cin>>name;}
	string returnname() {return name;}
		 
	void getauthor() {cin>>author;}
	string returnauthor() {return author;}
		 
    void getid() {cin>>id; }
	string returnid() {return id;}
		 
	void getpublication() {cin>>publication;}
	string returnpublication() {return publication;}
		 
	void gettime() {cin>>time;}
	string returntime() {return time;}
	
	void getpath() {cin>>path;}
	string returnpath() {return path;}
	
	void addpaper()
		{
			cout<<"请输入你要录入的论文的标题："<<endl;
			getname();
			cout<<"请输入该书作者："<<endl;
			getauthor();
			cout<<"请输入该书编号："<<endl;
			getid();
			cout<<"请输入该书刊物："<<endl;
			getpublication();
			cout<<"请输入该论文时间："<<endl;
			gettime();
			cout<<"请输入该书存放位置："<<endl;
			getpath();
			string a=returnid();
			count3++;
			a = a + ".txt";
			ofstream file(a.c_str(),ios::out|ios::app);
			file<<returnname()<<endl;
			file<<returnauthor()<<endl;
			file<<returnpublication()<<endl;
			file<<returnid()<<endl;
			file<<returntime()<<endl;
			file<<returnpath()<<endl;
			file.close();
		}		 
		~paper() {}
 }; 

pbook pb[1000];
ebook eb[1000];
paper pa[1000];

class user //用户     
{   
private:
	int tab;  //删除标记 1：管理员0：普通用户 
	string id;   //用户名 
	string name;  //读者姓名
	string code;//密码 
	string managerid="123456";//管理员用户名
	string managercode="123456a";//管理员密码 
    
public:
	
	void getname() {cin>>name;}
    string returnname() {return name;}
		 
    void getid() {cin>>id; }
	string returnid() {return id;}
		 
	void getcode() {cin>>code;}
	string returncode() {return code;}
		 
	void adduser()
		{
			cout<<"请输入新增用户姓名："<<endl;
			getname();
			cout<<"请输入新增用户名："<<endl;
			getid();
			cout<<"请输入用户密码："<<endl;
			getcode();		
			tab=0;
			string a=returnname();
		 	a = a + ".txt";
		 	ofstream file(a.c_str(),ios::out|ios::app);
		 	file<<returnname()<<endl;
		 	file<<returncode()<<endl;
		 	file<<returnid()<<endl;
			file.close();
		}		 
		
		void deleteuser()//删除用户
		 {
			
         }
       
	    void borrowbook()//借阅书籍 
        {
        	cout<<"请选择要查询的资源类型"<<endl;
			cout<<"1、纸质书"<<endl;
			cout<<"2、电子书"<<endl;
			cout<<"3、论文"<<endl;
			int s;
			cin>>s;
			switch(s)
			{
			case 1:
			{
				string pbookname;
				cout<<"请输入你想要查找的书名："<<endl;
				cin>>pbookname;
				for(int i=0;i<count1;i++)
				{
				    if(strstr(pb[i].returnname().c_str(),pbookname.c_str())!=NULL)
				    {
						cout<<"查询成功！"<<endl;
						
						cout<<"书名："<<endl;
						cout<<pb[i].returnname()<<endl;
						
						cout<<"作者："<<endl;
						cout<<pb[i].returnauthor()<<endl;
						
						cout<<"编号：";
						cout<<pb[i].returnid()<<endl;
						
						cout<<"出版社："<<endl;
						cout<<pb[i].returnpublisher()<<endl;
						
						cout<<"储存路径："<<endl;
						cout<<pb[i].returnpath()<<endl;
						int k=i;
						cout<<"请问是否借阅该书籍？"<<endl;
						cout<<"1、是"<<endl;
						cout<<"2、否"<<endl;
						int a;
						cin>>a;
						    if(a==1)
						    {
							    a++;
							    cout<<"借阅成功！"<<endl;
							    break;
						    }
						    else{continue;}	
			            }
			        }
			       
	        	}
			break;
		    
			case 2:	
		    {
				string ebookname;
				cout<<"请输入你想要查找的书名："<<endl;
				cin>>ebookname;
				for(int i=0;i<count2;i++)
				{
				    if(strstr(eb[i].returnname().c_str(),ebookname.c_str())!=NULL)
				    {
					    
						cout<<"查询成功！"<<endl;
						
						cout<<"书名："<<endl;
						cout<<eb[i].returnname()<<endl;
						
						cout<<"作者："<<endl;
						cout<<eb[i].returnauthor()<<endl;
						
						cout<<"编号：";
						cout<<eb[i].returnid()<<endl;
						
						cout<<"出版社："<<endl;
						cout<<eb[i].returnpublisher()<<endl;
						
						cout<<"储存路径："<<endl;
						cout<<eb[i].returnpath()<<endl;
						int k=i;
						cout<<"请问是否借阅该书籍？"<<endl;
						cout<<"1、是"<<endl;
						cout<<"2、否"<<endl;
						int a;
						cin>>a;
						    if(a==1)
						    {
							    a++;
							    cout<<"借阅成功！"<<endl;
							    break;
						    }
						    else{continue;}	
			        }
			        else {cout<<"查找不到该书"<<endl;} 
	        	}
		    }
			break;
			
			case 3:	
		    {
				string ebookname;
				cout<<"请输入你想要查找的书名："<<endl;
				cin>>ebookname;
				for(int i=0;i<count2;i++)
				{
				    if(strstr(eb[i].returnname().c_str(),ebookname.c_str())!=NULL)
				    {
					    
						cout<<"查询成功！"<<endl;
						
						cout<<"书名："<<endl;
						cout<<eb[i].returnname()<<endl;
						
						cout<<"作者："<<endl;
						cout<<eb[i].returnauthor()<<endl;
						
						cout<<"编号：";
						cout<<eb[i].returnid()<<endl;
						
						cout<<"出版社："<<endl;
						cout<<eb[i].returnpublisher()<<endl;
						
						cout<<"储存路径："<<endl;
						cout<<eb[i].returnpath()<<endl;
						int k=i;
						cout<<"请问是否借阅该书籍？"<<endl;
						cout<<"1、是"<<endl;
						cout<<"2、否"<<endl;
						int a;
						cin>>a;
						    if(a==1)
						    {
							    a++;
							    cout<<"借阅成功！"<<endl;
							    break;
						    }
						    else{continue;}	
			        }
			        else {cout<<"查找不到该书"<<endl;} 
	        	}
		    }
			break;
	        }
	};
		void returnbook()//还书 
		{
			
		}
};

class user_
{
	private:
		string name;
		string code;
	public:
		 void getname() {cin>>name;}
	 	 string returnname() {return name;}
		 
		 void getcode() {cin>>code;}
		 string returncode() {return code;}
};

user user2[100];
int main()
{
	user_ user1 ;
	cout<<"请选择登录身份："<<endl;
	cout<<"1、管理员"<<endl; 
	cout<<"2、用户"<<endl; 
	cout<<"0、退出"<<endl;
	int a;
	cin>>a;
	while(a!=0)
	{
		if(a==1)
		{
			cout<<"请输入你的用户名："<<endl;
			user1.getname();
			cout<<"请输入你的密码"<<endl;
			user1.getcode();
			if(strcmp(user1.returnname().c_str(),"123456")==0&&strcmp(user1.returncode().c_str(),"123456a")==0)
			{
				cout<<"登录成功！"<<endl;
				cout<<"请选择你录入的资源类型"<<endl; 
				cout<<"1、纸质书"<<endl;
				cout<<"2、电子书"<<endl;
				cout<<"3、论文"<<endl;
				cout<<"0、返回"<<endl; 	
				int b;
				cin>>b;	
				while(b!=0)
				{
	
					if(b==1)
					{
						pb[count1].addpbook();
					}
					else if(b==2)
					{
						eb[count2].addebook();
					}
					else
					{
						count3++;
						pa[count3].addpaper();
					}	
					
				}	
			}
			else 
			{
				cout<<"已退出"<<endl; 
			}
		}
		else
		{
			cout<<"1、用户登录"<<endl;
			cout<<"2、新用户注册"<<endl;
			cout<<"0、返回"<<endl; 
			int c;
			cin>>c;
			while(c!=0)
			{
				if(c==2)
				{
					count4++;
					user2[count4].adduser();
				}
				else
				{
					string name1;
					string code1;
					cout<<"请输入你的用户名："<<endl;
					cin>>name1;
					cout<<"请输入你的密码"<<endl;
					cin>>code1;
					int n=0;
					for(int i=0;i<count4;i++)
					{
						if(strcmp(name1.c_str(),user2[i].returnname().c_str())==0&&strcmp(code1.c_str(),user2[i].returncode().c_str())==0)
						{
							cout<<user2[i].returnname()<<endl;
							continue;
						}
					}
					if(n==0)
					{
						cout<<"登录失败，用户名或密码有误！"<<endl;
							
					}
					cout<<"请选择下列操作："<<endl;
					cout<<"1、用户注销"<<endl;
					cout<<"2、资源查询借阅"<<endl;
					cout<<"3、资源归还"<<endl;
					cout<<"4、在线阅读"<<endl; 
					cout<<"0、返回"<<endl;
					int d;
					cin>>d;
					while(d!=0)
					{
							switch(d)
						{
							 case 1:
								 {
									user user2;
									user2.deleteuser();
									count4--;				 	
								 } 
						 	  	break;
							case 2:
								{
									user user2;
									user2.borrowbook();					
								}
								break;
							case 3:
								{
									user user2;
									user2.returnbook();						
								}
			
								break;
						 }			
						cout<<"请选择你要进行的操作："<<endl;
						cout<<"1、用户注销"<<endl;
						cout<<"2、资源查找借阅"<<endl;
						cout<<"3、资源归还"<<endl;
						cout<<"4、在线阅读或下载"<<endl; 
						cout<<"0、返回"<<endl;
					 	scanf("%d",&d);
					}
					 
				}
				cout<<"1、用户登录"<<endl;
				cout<<"2、新用户注册"<<endl;
				cout<<"0、返回"<<endl; 	
				cin>>c;
			}
		}
		cout<<"请选择登录身份："<<endl;
		cout<<"1、管理员"<<endl; 
		cout<<"2、用户"<<endl; 
		cout<<"0、退出"<<endl;
		cin>>a;
	}
return 0;
}
