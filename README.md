
#!/bin/bash

# Prompt the user to enter employee name, hours worked, and rate per hour
read -p "Enter employee name: " name
read -p "Enter hours worked: " hours
read -p "Enter rate per hour: " rate

# Calculate the basic pay
basic_pay=$(echo "$hours * $rate" | bc)

# Calculate the tax based on basic pay
if [ $(echo "$basic_pay > 70000" | bc) -ne 0 ]; then
  tax=$(echo "$basic_pay * 0.25" | bc)
elif [ $(echo "$basic_pay >= 15000 && $basic_pay <= 70000" | bc) -ne 0 ]; then
  tax=$(echo "$basic_pay * 0.15" | bc)
else
  tax=0
fi

# Calculate the net pay
net_pay=$(echo "$basic_pay - $tax" | bc)

# Output the results
echo "Employee Name: $name"
echo "Basic Pay: $basic_pay"
echo "Tax: $tax"
echo "Net Pay: $net_pay" 





#!/bin/bash

# Prompt the user for input
read -p "Enter Customer ID: " customerID
read -p "Enter Customer Name: " customerName
read -p "Enter Units Consumed: " unitsConsumed

# Initialize bill as zero
bill=0

# Determine the bill amount based on units consumed
if [ $unitsConsumed -le 199 ]; then
    bill=$((unitsConsumed * 120))
elif [ $unitsConsumed -lt 400 ]; then
    bill=$((unitsConsumed * 150))
elif [ $unitsConsumed -lt 600 ]; then
    bill=$((unitsConsumed * 180))
else
    bill=$((unitsConsumed * 200))
fi

# Display the total bill
echo "Customer ID: $customerID"
echo "Customer Name: $customerName"
echo "Units Consumed: $unitsConsumed"
echo "Total Bill: Ksh $bill"






#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <fcntl.h>

int main() {
    // Define a buffer to read the data back into
    char buffer[12]; // "Hello World" + '\0'
    
    // Open a file for writing (creates it if it doesn't exist)
    int file_descriptor = open("example.txt", O_WRONLY | O_CREAT, 0600);
    if (file_descriptor < 0) {
        perror("open");
        return EXIT_FAILURE;
    }

    // Write the string "Hello World" to the file
    if (write(file_descriptor, "Hello World", 11) != 11) {
        perror("write");
        close(file_descriptor);
        return EXIT_FAILURE;
    }

    // Close and then open the file for reading
    close(file_descriptor);
    file_descriptor = open("example.txt", O_RDONLY);
    if (file_descriptor < 0) {
        perror("open");
        return EXIT_FAILURE;
    }

    // Read the content back from the file
    if (read(file_descriptor, buffer, 11) != 11) {
        perror("read");
        close(file_descriptor);
        return EXIT_FAILURE;
    }
    buffer[11] = '\0'; // Null-terminate the string

    // Print the content read from the file
    printf("File content: %s\n", buffer);

    // Close the file
    close(file_descriptor);
    
    return EXIT_SUCCESS;
}
   
   
   
   
   
   
   
   
   
   
  - 👋 Hi, I’m @walucy
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
walucy/walucy is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
