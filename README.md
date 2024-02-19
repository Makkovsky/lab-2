
#include <stdio.h> 
 
double calculate_ln(double x) { 
    double a = 0.0; 
    double b = x; 
    double c = x; 
    double d = 1.0; 
 
    for (int i = 1; i <= 100; i++) { 
        a += b; 
        c *= x; 
        d += 1.0; 
        b = c / d * ((i % 2 == 0) ? -1 : 1); 
    } 
 
    return a; 
} 
 
int main() { 
    double x; 
    printf("znachenie x (-1 < x <= 1): "); 
    scanf("%lf", &x); 
 
    if (x <= -1 || x > 1) { 
        return 0; 
    } else { 
        double a = calculate_ln(x); 
        printf("ln(1 + %.2lf) = %lf\n", x, a); 
    } 
 
    return 0; 
}
