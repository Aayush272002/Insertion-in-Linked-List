#include<iostream>
using namespace std;

class Node{
    
    public:
    int data;
    Node* next;

    //Constructor
    Node(int data){
        this -> data = data;
        this -> next = NULL;
    }

};


void insertatHead(Node* &head , int d){
    Node* temp = new Node(d);
    temp -> next = head;
    head = temp;
}


void insertatTail(Node* &tail , int d){
    Node* temp = new Node(d);
    tail -> next = temp;
    tail = temp;
}

void insertinMiddle(Node* &head , int position , int d){
    Node* temp = head;
    int cnt = 1;

    while(cnt < position-1){
        temp = temp -> next;
        cnt++;
    }

    //creating a node for d
    Node* nodetoInsert = new Node(d);
    nodetoInsert -> next = temp -> next;
    temp -> next = temp;

}


void print(Node* &head){
    Node* temp = head;

    while(temp != NULL){
        cout<< temp -> data << " ";
        temp = temp -> next;
    }
    cout << endl;
}

int main(){
    //creating a new node
    Node* Node1 = new Node(10);
    cout << Node1 -> data << endl;
    cout<< Node1 -> next <<endl;

    //inserting a new node at head
    Node* head = Node1;
    /*insertatHead(head , 12);
    print(head);

    insertatHead(head , 15);
    print(head);*/

    //inserting a new node at tail
    Node* tail = Node1;
    print(head);

    insertatTail(tail , 12);
    print(head);

    insertatTail(tail, 15);
    print(head);

    //Inserting a new Node in the middle 
    insertinMiddle(head , 3 , 20);
    print(head);
}
