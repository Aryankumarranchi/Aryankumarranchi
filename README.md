#include<iostream>
#include<fstream>
#include<string>
using namespace std;
struct todolist{
   int id;
   string task;
};
int ID;


void banner(){
   cout<<"----------------------------------"<<endl;
   cout<<"\tMy To Do"<<endl;
   cout<<"----------------------------------"<<endl;
}
void addTask();
//void showTask();
//void searchTask();
//void deleteTask();
//void updateTask();

int main(){
   system("cls");
   banner();
   
   while(true){
    cout<<endl<<"\t1.Add Task"<<endl;
    cout<<endl<<"\t2.Show Task<"<<endl;
    cout<<endl<<"\t3.Search Task"<<endl;
    cout<<endl<<"\t4.Delete Task"<<endl;
    cout<<endl<<"\t5.Update Task"<<endl;
    int choice;
    cout<<"Enter your Choice"<<endl;
    cin>>choice;
    switch(choice){
      case 1:
            addTask();
            break;
      case 2:
          // showTask();
            break;
      case 3:
          //  searchTask();
            break;
      case 4:
            //deleteTask();
            break;
      case 5:
          //  updateTask();
            break;
       default: 
         cout<<"Wrong Choice Entered<<endl";     
                                   

    }
    }
    return 0;
}
void addTask(){
   system("cls");
   banner();
   todolist todo;
   cout<<"Enter a Task"<<endl;
   cin.get();   
   getline(cin,todo.task);
   char save;
   cout<<"save(y/n)"<<endl;
   cin>>save;
   if(save=='y'||save=='Y'){
          ID++;
          ofstream fout;
          fout.open("todo.txt");
          fout<<"\n"<<ID;
          fout<<"\n"<<todo.task;
          fout.close();

          char more;
          cout<<"Add more Task"<<endl;
          cin>>more;
          if(more=='y'||more=='Y'){
            addTask();
          }
          else{
            system("cls");
            cout<<"Added Successfully"<<endl;
            return;
          }
          system("cls");
        }
}