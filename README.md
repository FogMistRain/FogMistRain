#include <stdio.h>
#include <math.h>
float calculate_function_value(float x, float prev) {
    float result = 1.0f;
    float term = 1.0f;
    int n = 2;
    while (fabsf(term) > 1e-6f) {
        term *= -(n - 1) / (float)n * x;
        result += term;
        prev = term;
        n++;
    }
    return result;
}
int main() {
    float x_value = 0.5f;
    float prev_term = 0.0f;
    float result = calculate_function_value(x_value, prev_term) * exp(x_value);
    printf("znachenie %.2f: %.6f\n", x_value, result);
    return 0;
}
