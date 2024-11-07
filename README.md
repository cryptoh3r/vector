#include <iostream>
#include <cmath> 

class Vector {
private:
    double x, y; 

public:
    Vector(double x_val, double y_val) : x(x_val), y(y_val) {}
    Vector add(const Vector& other) const {
        return Vector(x + other.x, y + other.y);
    }
    void print() const {
        std::cout << "(" << x << ", " << y << ")" << std::endl;
    }
    void dir() const {
        double magnitude = std::sqrt(x * x + y * y);
        std::cout << "Magnitude: " << magnitude << std::endl;
    }
};

int main() {
    Vector v1(5.0, 6.0);
    Vector v2(7.0, 8.0);
    std::cout << "Vector 1: ";
    v1.print();
    std::cout << "Vector 2: ";
    v2.print();
    Vector v3 = v1.add(v2);
    std::cout << "Vector 1 + Vector 2: ";
    v3.print();
    v3.dir();
    return 0;
}
