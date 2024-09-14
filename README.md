# Program-CPP_TLS24
#include <iostream>
#include <vector>   // To store the data of the subtraction process
#include <iomanip>  // For formatting the output

// Function to display the graph of the subtraction process
void printGraph(const std::vector<int>& data) {
    for (int i = 0; i < data.size(); i++) {
        std::cout << std::setw(2) << i << ": ";
        for (int j = 0; j < data[i]; j++) {
            std::cout << "*";
        }
        std::cout << " (" << data[i] << ")\n";
    }
}

int main() {
    std::vector<int> data;
    int initialValue = 51;  // Initial odd value to start subtracting from
    int subtractor = 7;     // Subtracting an odd number
    int limit = 1;          // Minimum limit must be odd

    std::cout << "Subtraction process starts from " << initialValue << " with subtractor " << subtractor << "\n";

    // Subtraction process for odd numbers
    while (initialValue >= limit) {
        data.push_back(initialValue);
        initialValue -= subtractor;

        // Conditional statement: if the value goes below or equal to 15, change the subtractor
        if (initialValue <= 15) {
            subtractor = 3;  // Switch to subtracting a smaller odd number
        }
    }

    // Display the graph of the subtraction process
    printGraph(data);

    return 0;
}
