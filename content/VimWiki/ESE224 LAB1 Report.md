## ESE224 Lab1 
Hunter Zhong
113003581
ESE224 SEC 1 L03

### Problem 1
Point.cpp

![[Pasted image 20220830133354.png]]
Point.h
![[Pasted image 20220830133529.png]]
main.cpp
![[Pasted image 20220830133833.png]]
Running
![[Pasted image 20220830133935.png]]
## Problem 2

Rectangle.h
```cpp
#pragma once

#include<iostream>

class Rectangle

{

    private:

        double xCoord;

        double yCoord;

        double width;

        double height;

    public:

        double getXCoord() const { return xCoord; }

  

        double getYCoord() const { return yCoord; }

  

        double getWidth() const { return width; }

  

        double getHeight() const { return height; }

        Rectangle();

        Rectangle(double x, double y, double w, double h);

        double getArea() const {return width*height; }

        Rectangle makeMirrorX();

        Rectangle makeMirrorY();

        Rectangle makeMirrorOrigin();

        friend std::ostream& operator<<(std::ostream &strm, const Rectangle &r) {

            return strm << "X: " << r.getXCoord() << " Y:"<<r.getYCoord()<< " Width: "<< r.getWidth()<< " Height: "<<r.getHeight();

        }

};
```

Rectangle.cpp
```cpp
#include"Rectangle.h"

  

Rectangle::Rectangle(){

    xCoord = 0;

    yCoord = 0;

    width = 2;

    height = 2;

  

}

Rectangle::Rectangle(double x, double y, double w, double h){

    xCoord = x;

    yCoord = y;

    width = w;

    height = h;

}

Rectangle  Rectangle:: makeMirrorX(){

    return Rectangle(-xCoord,yCoord,width,height);

  
  

}

Rectangle  Rectangle:: makeMirrorY(){

    return Rectangle(xCoord,-yCoord,width,height);

  
  

}

Rectangle  Rectangle:: makeMirrorOrigin(){

    return Rectangle(-xCoord,-yCoord,width,height);

  
  

}
```

main.cpp
```cpp
#include<iostream>

#include"Rectangle.h"

  

using namespace std;

int main(){

    cout<<"Test default constructor: "<<endl;

    Rectangle r1;

    cout<<r1;

    cout<<"Test prameterized constructor: "<<endl;

    double x,y,w,h;

    cin>>x>>y>>w>>h;

    Rectangle r2(x,y,w,h);

    cout<<r2<<endl;

    cout<<"Compute the area of r2"<<endl;

    cout<<r2.getArea();

  

    cout<<"Test mirrored x axis rectangle"<<endl;

    cout<<r2.makeMirrorX()<<endl;

  

    cout<<"Test mirrored y axis rectangle"<<endl;

    cout<<r2.makeMirrorY()<<endl;

  

    cout<<"Test mirrored origin rectangle"<<endl;

    cout<<r2.makeMirrorOrigin()<<endl;

}
```
running
![[Pasted image 20220830134504.png]]
## Problem 3
```cpp
#pragma once

#include<string>

#include<iostream>

using namespace std;

  

class Student{

    private:

    string ID;

    string Name;

    string Major;

    string Email;

    public:

    Student();

    Student(string ID, string N, string M, string E);

  
  

    string getID() const { return ID; }

  

    void setID(const string &i) { ID = i; }

  

    string getName() const { return Name; }

  

    void setName(const string &name) { Name = name; }

  

    string getEmail() const { return Email; }

  

    void setEmail(const string &email) { Email = email; }

  

    string getMajor() const { return Major; }

  

    void setMajor(const string &major) { Major = major; }

  

    friend std::ostream& operator<<(std::ostream &strm, const Student &s) {

        return strm << "ID: " <<s.getID() << "  Name: "<<s.getName()<< "    Email: "<< s.getEmail()<< " Major: "<<s.getMajor();

        }

  
  

};
```
Student.cpp
```cpp
#include"Student.h"

  

Student::Student(){

    ID = "1234567890";

    Name = "ESE224 TA";

    Major = "Electrical Engineering";

    Email = "ese224TA@stonybrook.edu";

}

  

Student::Student(string i, string n, string m, string e){

    ID = i;

    Name = n;

    Major = m;

    Email = e;

}
```

main.cpp
```cpp
#include"Student.h"

using namespace std;

  

int main(){

    cout<<"Test Default Constructor: "<<endl;

    Student s1;

    cout<<s1<<endl;

  
  

    cout<<"Test Parametered contructor"<<endl;

    string i,n,m,e;

    getline(cin,i);

    getline(cin,n);

    getline(cin,m);

    getline(cin,e);

    Student s2(i,n,m,e);

    cout<<s2<<endl;

  

    cout<<"Change Student Name:"<<endl;

    getline(cin,n);

    s2.setName(n);

    cout<<"Change Student ID:"<<endl;

    getline(cin,n);

    s2.setID(n);

    cout<<"Change Student Major:"<<endl;

    getline(cin,n);

    s2.setMajor(n);

    cout<<"Change Student Email:"<<endl;

    getline(cin,n);

    s2.setEmail(n);

    cout<<"s2 after the change: "<<endl;

    cout<<s2<<endl;

  
  

}
```

Running Screen
![[Pasted image 20220830135012.png]]
## Problem 4
```cpp
class Grade{

    private:

        double homework = 0;

        double lab = 0;

        double project = 0;

        double exam = 0;

    public:

        double getHomework() const { return homework; }

        void setHomework(double homework_) { homework = homework_; }

  

        double getLab() const { return lab; }

        void setLab(double lab_) { lab = lab_; }

  

        double getProject() const { return project; }

        void setProject(double project_) { project = project_; }

  

        double getExam() const { return exam; }

        void setExam(double exam_) { exam = exam_; }

  
  

        Grade();

        double calculateFinal();

};
```

Grade.cpp
```cpp
#include"Grade.h"

  
  

Grade::Grade(){

  

}

  

double Grade::calculateFinal(){

    return 0.2*homework + 0.15*lab + 0.35*project+ 0.3*exam;

}
```

main.cpp
```cpp
#include"Grade.h"

#include<iostream>

  

using namespace std;

  

int main(){

    Grade g1;

    double x;

    cout<<"Enter hw grade:"<<endl;

    cin>>x;

    g1.setHomework(x);

    cout<<"Enter lab grade:"<<endl;

    cin>>x;

    g1.setLab(x);

    cout<<"Enter project grade:"<<endl;

    cin>>x;

    g1.setProject(x);

    cout<<"Enter exam grade:"<<endl;

    cin>>x;

    g1.setExam(x);

  

    cout<<"The final score is: "<<g1.calculateFinal();

}
```

Running Screen
![[Pasted image 20220830135334.png]]
## Problem 5
```cpp
class WaterLevelMonitor{

    private:

        double current;

        double average;

        double highest;

        double lowest;

        double total;

        int counter;

    public:

        WaterLevelMonitor();

        void receiveData(double x);

  
  

        double getCurrent() const { return current; }

  

        double getHighest() const { return highest; }

  

        double getAverage() const { return average; }

  

        double getLowest() const { return lowest; }

  
  
  

};

```

```cpp
#include"WaterLevelMonitor.h"

  

WaterLevelMonitor::WaterLevelMonitor(){

    current = -1.0;

    average = -1.0;

    highest = -1.0;

    lowest = 1000000000;//although the instruction said to set to -1.0, I changed it to a big number for easier use

    total = 0;

    counter = 0;

  

}

  

void WaterLevelMonitor::receiveData(double x){

    current = x;

    total += current;

    counter++;

    average = total/double(counter);

    if (current>highest) highest = current;

    if (current<lowest) lowest = current;

  

}
```
main.cpp
```cpp
#include "WaterLevelMonitor.h"

#include <iostream>

using namespace std;

int main()

{

WaterLevelMonitor monitor;

cout << "Current water level: " << monitor.getCurrent() << endl;

cout << "Average water level: " << monitor.getAverage() << endl;

cout << "Highest water level: " << monitor.getHighest() << endl;

cout << "Lowest water level: " << monitor.getLowest() << endl << endl;

double level;

// assume there are 10 data back per day

for (int i = 0; i < 10; i++)

{

cout << "input the " << i + 1 << "th data: ";

cin >> level;

monitor.receiveData(level);

cout << "Current water level: " << monitor.getCurrent() << endl;

cout << "Average water level: " << monitor.getAverage() << endl;

cout << "Highest water level: " << monitor.getHighest() << endl;

cout << "Lowest water level: " << monitor.getLowest() << endl << endl;

}

system("pause");

return 0;

}
```


Running Screen
![[Pasted image 20220830140109.png]]![[Pasted image 20220830140135.png]]
