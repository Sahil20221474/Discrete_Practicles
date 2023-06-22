#include <iostream>
#include <set>
using namespace std;

class Set {
private:
    set<int> elements;

public:
    void addElement(int element) {
        elements.insert(element);
    }

    bool isMember(int element) {
        return elements.find(element) != elements.end();
    }
};

int main() {
    Set mySet;

    mySet.addElement(25);
    mySet.addElement(50);
    mySet.addElement(75);

    int element ;
    cout<<"Enter the element : ";
    cin>>element;
   

    if (mySet.isMember(element))
        cout << element << " TRUE " << std::endl;
    else
        cout << element << " FALSE " << std::endl;

 
    return 0;
}
