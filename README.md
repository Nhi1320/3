#include <iostream>
using namespace std;

int ucln(int t,int m)
{
    while(m!=0)
    {
        int temp=m;
        m=t%m;
        t=temp;
    }
    return t;
}

int bcnn(int t, int m)
{
    return t/ucln(t,m)*m;
}

void quydong(int t1, int t2, int m1, int m2, int &tu1, int &tu2, int &mau)
{
    mau=bcnn(m1,m2);
    tu1=t1*(mau/m1);
    tu2=t2*(mau/m2);
}

void Ketqua(int t, int m)
{
    int g=ucln(abs(t), abs(m));
    cout<< "= "<< t/g<< "/"<<m/g;
}

int main()
{
    int t1,t2,m1,m2,chon;
    cout<< "Nhap phan so thu nhat: "<<endl;
    cin>>t1>>m1;

    cout<< "Nhap phan so thu hai: "<<endl;
    cin>>t2>>m2;

    if(m1!=0 && m2!=0)
    {
        int tu1,tu2,mau;
        quydong(t1,t2,m1,m2,tu1,tu2,mau);

        cout<< "Cong: ";Ketqua(tu1+tu2,mau);cout<<endl;
        cout<< "Tru: ";Ketqua(tu1-tu2,mau);cout<<endl;
        cout<< "Nhan: ";Ketqua(t1*t2,m1*m2);cout<<endl;

        if(t2==0)
            cout<< "Khong the chia cho 0."<<endl;
        else cout<< "Chia: ";Ketqua(t1*m2,m1*t2);cout<<endl;
    }
    else cout<< "Khong dung dinh dang.Vui long nhap lai!";
    return 0;
}
