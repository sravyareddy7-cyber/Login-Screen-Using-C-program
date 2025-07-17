# Login-Screen-Using-C-program
# 🔐 Simple Login Screen in C

This is a basic C program that simulates a login screen with username and password verification. It allows the user a limited number of attempts before denying access.

## 📋 Features

- Command-line login interface
- Hardcoded credentials (`admin` / `1234`)
- Maximum of 3 login attempts
- Simple `strcmp`-based authentication
- Beginner-friendly C code

---

## 🧑‍💻 How It Works

1. Program prompts for username and password.
2. Compares input with hardcoded credentials.
3. If they match, login is successful.
4. If not, the user gets 3 chances before the program exits.

---

## 🔧 How to Compile and Run

### Step 1: Save the Code

Save the following code in a file named `login.c`:

```c
#include <stdio.h>
#include <string.h>

int main() {
    char correctUsername[] = "admin";
    char correctPassword[] = "1234";

    char username[30], password[30];
    int attempt, maxAttempts = 3;

    printf("=== Login System ===\n");

    for (attempt = 1; attempt <= maxAttempts; attempt++) {
        printf("\nAttempt %d of %d\n", attempt, maxAttempts);

        printf("Username: ");
        scanf("%s", username);

        printf("Password: ");
        scanf("%s", password);

        if (strcmp(username, correctUsername) == 0 && strcmp(password, correctPassword) == 0) {
            printf("\n✅ Login successful! Welcome, %s.\n", username);
            return 0;
        } else {
            printf("❌ Invalid username or password.\n");
        }
    }

    printf("\n🚫 Too many failed attempts. Exiting...\n");
    return 1;
}
