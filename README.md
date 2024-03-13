#include <iostream>
#include <algorithm>
#include <vector>
using namespace std;

class MangLinear
{
private:
    int N;
    int T;
public:
    void SoTest();
    void XuLiMang();
};

void MangLinear::SoTest()
{
    cin >> T;
}

void MangLinear::XuLiMang()
{
    vector<int> tongtrongsomaxs(T);
    for(int i=0; i< T; ++i)
    {
        cin >> N;
        vector<int> a(N), b(2);
        for(int j=0; j<N; ++j)
        {
            cin >> a[j];
        }

        int min = *min_element(a.begin(), a.end());
        int max = *max_element(a.begin(), a.end());

        b[0] = min;
        b[1] = max;

        int trongsob = max - min;

        a.erase(remove(a.begin(), a.end(), min), a.end());
        a.erase(remove(a.begin(), a.end(), max), a.end());

        min = *min_element(a.begin(), a.end());
        max = *max_element(a.begin(), a.end());

        int trongsoa = max - min;

        tongtrongsomaxs[i] = trongsoa + trongsob;
    }


    for(int i = 0; i < T; i++)
    {
        cout << tongtrongsomaxs[i] << endl;
    }

}

int main()
{
    MangLinear m;
    m.SoTest();
    m.XuLiMang();
    return 0;
}
