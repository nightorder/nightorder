> [!CAUTION]  
> Everything I publish on this profile and outside of it is a demonstration of technology for informational purposes only, and is not intended to violate the laws of your region, country, or the world. Any actions you take are done at your own risk.


<br>

```cpp
#include <iostream>
#include <vector>
using namespace std;

double f(double x, double t) {
    return -0.5 * x + 2.0; 
}

vector<double> euler(double x0, double t0, double tf, double dt) {
    vector<double> x_values;
    double x = x0;
    double t = t0;

    while (t <= tf) {
        x_values.push_back(x);
        x = x + dt * f(x, t); 
        t += dt;
    }

    return x_values;
}

int main() {
    double x0 = 0.0;
    double t0 = 0.0;
    double tf = 10.0;  
    double dt = 0.1;   

    vector<double> result = euler(x0, t0, tf, dt);

    for (size_t i = 0; i < result.size(); ++i)
        cout << "t=" << i*dt << " x=" << result[i] << endl;

    return 0;
}

}
```



