# lab4_cpp
#include <stdlib.h>
#include <stdio.h>
#include <iostream>

using namespace std;

struct Node       //Структура являющаяся звеном списка
{
        int x = NULL;
        int y = NULL;
        Node *next, *prev; //Указатели на адреса следующего и предыдущего элементов списка
};


struct List   //Создаем тип данных Список
{
        Node *head;
        Node *tail;  //Указатели на адреса начала списка и его конца
};


void add( List *list, int x, int y )
{
        Node *temp = new Node(); // Выделение памяти под новый элемент структуры
        temp->next = NULL;       // Указываем, что изначально по следующему адресу пусто
        temp->x = x;             // Записываем значение в структуру
        temp->y = y;
        if ( list->head != NULL ) // Если список не пуст
        {
                temp->prev = list->tail; // Указываем адрес на предыдущий элемент в соотв. поле
                list->tail->next = temp; // Указываем адрес следующего за хвостом элемента
                list->tail = temp;       //Меняем адрес хвоста
        }
        else //Если список пустой
        {
                temp->prev = NULL; // Предыдущий элемент указывает в пустоту
                list->head = list->tail = temp;    // Голова=Хвост=тот элемент, что сейчас добавили
        }
}

void print( List * list )
{
        Node * temp = list->head;  // Временно указываем на адрес первого элемента
        while( temp != NULL )      // Пока не встретим пустое значение
        {
                cout <<"("<< temp->x <<","<< temp->y<<")";
                 //Выводим значение на экран
                temp = temp->next;     //Смена адреса на адрес следующего элемента
        }
        cout<<"\n";
}

void lookfor( List * list, int x, int y)
{
    temp->head;
    while (temp != tail)
    {
        if (temp->x == x and temp->y == y)
        {
            return (&temp);
        }
        else {temp == temp->next}

    }

}
int main() {
        List list;
        list.head = list.tail = NULL;
    int i=0;
    while (i<20){
         add( &list, rand() % 2,rand() % 2 );
             i++;}
        print( &list );
        return 0;
    cout << lookfor(&list, 1, 1);
}
