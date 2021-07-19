**CV Alena Veremeenko**

1.Alena Veremeenko
2.email adress: alenaveremeenko2001@gmail.com phone number: +37529577118
3.I study at BSU, Faculty of Radiophysics and Computer Technologies. My strengths are quick learning, 

communication and desire to learn.
4.Skills: Java , C++, SOLID, OOP
5.Sample code on Java:
```package entity;

import java.io.Serializable;
import java.util.Calendar;
import java.util.Date;

public class Ad implements Serializable, Identifiable {

    private static final long serialVersionUID = -1777984074044025486L;
    private int id = 0;
    private String subject = "";
    private String body = "";
    private int authorId;
    transient private User author;
    private Long lastModified;
    transient private Date lastModifiedDate;

    public Ad() {
        lastModified = Calendar.getInstance().getTimeInMillis();
    }

    public int getId() {
        return id;
    }

    public void setId(int id) {
        this.id = id;
    }

    public String getSubject() {
        return subject;
    }

    public void setSubject(String subject) {
        this.subject = subject;
    }

    public String getBody() {
        return body;
    }

    public void setBody(String body) {
        this.body = body;
    }

    public int getAuthorId() {
        return authorId;
    }

    public void setAuthorId(int authorId) {
        this.authorId = authorId;
    }

    public User getAuthor() {
        return author;
    }

    public void setAuthor(User author) {
        this.author = author;
    }

    public Long getLastModified() {
        return lastModified;
    }

    public void setLastModified(Long lastModified) {
        this.lastModified = lastModified;
        lastModifiedDate = new Date(lastModified);
    }

    public Date getLastModifiedDate() {
        return lastModifiedDate;
    }

    public int hashCode() {
        return id;
    }

    public boolean equals(Object obj) {
        if (this == obj)
            return true;
        if (obj == null)
            return false;
        if (getClass() != obj.getClass())
            return false;
        Ad other = (Ad) obj;
        if (id != other.id)
            return false;
        return true;
    }
}
```

Sample code on C++:

```#include <iostream>
#include <time.h>

using namespace std;

class list
{
private:
    class Node {
        friend class list;
        friend float addition(list* li);
    private:
        float data; // поле данных
        Node* pptr;// указатель на прошлый 
        Node* nptr;// на следующий 
    public:
        Node() {
            (*this).data = 0;
            (*this).pptr = NULL;
            (*this).nptr = NULL;
        }
        Node(float data, Node* ptr,Node* next) {
            (*this).data = data;
            (*this).pptr = ptr;
            (*this).nptr = next;
        }
    };
    Node getnode;
public:
    void show()
    {
        Node* p;
        p = &(*this).getnode;
        do {
            cout << (*p).data;
            p = (*p).nptr;// переход к следующему узлу
        } while ((*p).nptr != NULL);
    }
    void add(float data, list* last, list* next)
    {
        ((*this).getnode).data = data;
        ((*this).getnode).pptr = &(*last).getnode;
        ((*this).getnode).nptr = &(*next).getnode;
    }
    Node* search(float data)
    {
        Node* p;
        p = &((*this).getnode);
        do {
            if ((*p).data == data) {
                return p;
            }
            p = (*p).nptr;// переход к следующему узлу
        } while ((*p).nptr != NULL);
        return NULL;
    }
    char showdata()
    {
        return((*this).getnode).data;
    }
    void deleteo()
    {
        Node* f;
        f = ((*this).getnode).pptr;
        (*f).nptr = ((*this).getnode).nptr;
        delete this;
    }
    void deleteall(list* p)
    {
        delete[] p;
    }
    friend float addition(list* li);
};
float addition(list* li)// тут складываем наши Х
{
    list p;
    p.getnode = *((*li).getnode).nptr;//берем х из следующего элемента
    return (p.getnode).data + ((*li).getnode).data;
}
int main()
{
    srand(time(NULL));
    setlocale(LC_ALL, "Russuan");
    int size = 0, n;
    int L2[100];
    cout << "N:" << endl;
    cin >> n;
    list* X = new list[n];
    for (int i = 0; i < n + 1; i++)// заполняем наши х дробными числами
    {
        int v;
        float x, c;
        c = rand() % 100;
        v = rand() % 100;
        x = c / v;
        if (i == 0)X[i].add(x, &X[n - 1], &X[i + 1]);
        else if (i == n - 1)X[i].add(x, &X[i - 1], &X[0]);
        else X[i].add(x, &X[i - 1], &X[i + 1]);
    }
    int i2 = 0;
    float sum = 0;
    for (int i = n; i > 1; i--)// ищем их сумму 
    {
        sum += addition(&X[i2]) + i * X[i].showdata();
        i2++;
    }
    cout << "Сумма :" << endl;
    cout << sum;
    X[0].deleteall(X);//удаление массива структур 
}
```
6.
7.I study at BSU.
8.English level: A2+
