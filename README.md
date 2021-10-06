# Lab-2
This lab uses classes collect a data and stores them. 

//Question 1:: 
#include <iostream>
#include <string>
using namespace std;

class Student 
{ 
    private:
        int admno;
        string sname;
        float eng, math, science;
        float total;
        
        float ctotal(float eng, float math, float science)
        {
            float total;
            total= eng + math + science;
            return total;
        }
        
    public:
        void takeData(int a, string n, float e, float m, float s)
        {
            admno= a;
            sname= n;
            eng= e;
            math= m;
            science= s;
            total= ctotal(e,m,s); 
        }
        
        void showdata()
        {
            cout << "Student Info: " << "#" << admno << " " << sname << " \nEnglish Grade: " << eng << " \nMath Grade: " << math << " \nScience Grade: " << science << " \nTotal: " << total << endl; 
        }
};



int main()
{
    Student stu;
    
    stu.takeData(2010, "Hannah", 88.7, 79.6, 80);
    
    stu.showdata();
    
    return 0;
}

//Question 2:: 
#include <iostream>
#include <string>
using namespace std;

class BOOK 
{ 
    private:
        int BOOK_NO;
        string BOOKTITLE;
        float PRICE;
        
        float TOTAL_COST (float PRICE, int num)
        {
            float ans;
            ans= PRICE * num;
            return ans;
        }
        
    public:
        void INPUT(int b_n, string t, float p)
        {
            BOOK_NO= b_n;
            BOOKTITLE= t;
            PRICE= p;
        }
        
        float PURCHASE ()
        {
            int num;
            float total;
            
            cout << "\nPlease enter the number of books purchased: ";
            cin >> num;
            total= TOTAL_COST(PRICE, num);
            //return total; 
        }
};



int main()
{
    BOOK noval;
    
    noval.INPUT(2010, "Twilight",9.01);
    
    cout << noval.PURCHASE() << endl;
    return 0;
}

//Question 3:: 
#include <iostream>
#include <string>
using namespace std;

class Distance 
{ 
    private:
        int feet;
        float inches;
        
    public:
        void set(int f, float i)
        {
            feet= f;
            inches= i;
        }
        
        void disp()
        {
            cout << "The Distance is:: " << feet <<"' " << inches << endl; 
        }
    
    Distance add(Distance newDistance)
        {
            Distance result;
            
            //sum up current and new one 
            result.feet= feet + newDistance.feet;
            result.inches= inches + newDistance.inches;
            
            return result; 
        }
};

int main()
{
    Distance dis, newDis, result; 
    
    dis.set(6, 11.5);
    
    dis.disp();
    
    newDis.set(10, 4.5);
    
    
    result= dis.add(newDis);
    
    result.disp();
    
    
    return 0;
}
