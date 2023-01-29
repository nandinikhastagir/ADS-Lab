#include <iostream>
#include <vector>
#include <cstdint>
using namespace std;
 

struct Node
{
    int data;
    Node* link;
};
 

Node* XOR(Node* x, Node* y) {
    return (Node*)((uintptr_t)(x) ^ (uintptr_t)(y));
}
 

void traverse(Node* head)
{
    Node* curr = head;
    Node* prev = nullptr;
    Node *next;
 
    while (curr != nullptr)
    {
        cout << curr->data << " —> ";
 

        next = XOR(prev, curr->link);
 

        prev = curr;
        curr = next;
    }
 
    cout << "nullptr\n";
}
 

void push(Node* &headRef, int data)
{
   
    Node* newNode = new Node();
    newNode->data = data;
 
   
    newNode->link = XOR(headRef, nullptr);
 
  
    if (headRef)
    {
        
        headRef->link = XOR(newNode, XOR(headRef->link, nullptr));
    }
 
    
    headRef = newNode;
}
 
int main()
{
    int choice, data;
    Node* head = nullptr;
    do{
        cout<<"Enter choice\n 1.Insert\n 2.Traverse\n 3.Exit\n";
        cin>>choice;
        switch(choice){
            case 1: cout<<"Enter data\n";
                    cin>>data;
                    push(head,data);
                    break;
            case 2: traverse(head);
                    break;
        }
        
    }while(choice != 3);
    
    return 0;
}
