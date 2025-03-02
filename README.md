#include <stdio.h>

int main() {
    double balance = 0, transactions[100];
    char transaction_types[100];
    int transaction_count = 0, choice;
    double amount;

    printf("Enter initial balance: ");
    scanf("%lf", &balance);

    while (1) {
        printf("\nBank Account System\n");
        printf("==========================\n");
        printf("1. Deposit Money\n");
        printf("2. Withdraw Money\n");
        printf("3. Check Balance\n");
        printf("4. View Transaction History\n");
        printf("5. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        if (choice == 1) {
            printf("Enter deposit amount: ");
            scanf("%lf", &amount);
            if (transaction_count < 100) {
                balance += amount;
                transactions[transaction_count] = amount;
                transaction_types[transaction_count] = 'D';
                transaction_count++;
                printf("Amount successfully deposited!\nUpdated Balance: $%.2f\n", balance);
            } else {
                printf("Transaction history is full!\n");
            }
        } else if (choice == 2) {
            printf("Enter withdrawal amount: ");
            scanf("%lf", &amount);
            if (amount > balance) {
                printf("Insufficient funds! Transaction failed.\n");
            } else {
                if (transaction_count < 100) {
                    balance -= amount;
                    transactions[transaction_count] = amount;
                    transaction_types[transaction_count] = 'W';
                    transaction_count++;
                    printf("Amount successfully withdrawn!\nUpdated Balance: $%.2f\n", balance);
                } else {
                    printf("Transaction history is full!\n");
                }
            }
        } else if (choice == 3) {
            printf("Current Balance: $%.2f\n", balance);
        } else if (choice == 4) {
            printf("Transaction History:\n");
            printf("----------------------\n");
            for (int i = 0; i < transaction_count; i++) {
                if (transaction_types[i] == 'D') {
                    printf("Deposit: +$%.2f\n", transactions[i]);
                } else {
                    printf("Withdrawal: -$%.2f\n", transactions[i]);
                }
            }
        } else if (choice == 5) {
            printf("Exiting the system...\nThank you for using our banking service!\n");
            break;
        } else {
            printf("Invalid choice! Please try again.\n");
        }
    }
    return 0;
}



































#include <stdio.h>

#define MAX_TRANSACTIONS 100

int main() {
    double balance = 0, transactions[MAX_TRANSACTIONS];
    char transaction_types[MAX_TRANSACTIONS];
    int transaction_count = 0, choice;
    double amount;

    printf("Enter initial balance: ");
    scanf("%lf", &balance);

    while (1) {
        printf("\nBank Account System\n");
        printf("==========================\n");
        printf("1. Deposit Money\n");
        printf("2. Withdraw Money\n");
        printf("3. Check Balance\n");
        printf("4. View Transaction History\n");
        printf("5. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        if (choice == 1) {
            printf("Enter deposit amount: ");
            scanf("%lf", &amount);
            if (transaction_count < MAX_TRANSACTIONS) {
                balance += amount;
                transactions[transaction_count] = amount;
                transaction_types[transaction_count] = 'D';
                transaction_count++;
                printf("Amount successfully deposited!\nUpdated Balance: $%.2f\n", balance);
            } else {
                printf("Transaction history is full!\n");
            }
        } else if (choice == 2) {
            printf("Enter withdrawal amount: ");
            scanf("%lf", &amount);
            if (amount > balance) {
                printf("Insufficient funds! Transaction failed.\n");
            } else {
                if (transaction_count < MAX_TRANSACTIONS) {
                    balance -= amount;
                    transactions[transaction_count] = amount;
                    transaction_types[transaction_count] = 'W';
                    transaction_count++;
                    printf("Amount successfully withdrawn!\nUpdated Balance: $%.2f\n", balance);
                } else {
                    printf("Transaction history is full!\n");
                }
            }
        } else if (choice == 3) {
            printf("Current Balance: $%.2f\n", balance);
        } else if (choice == 4) {
            printf("Transaction History:\n");
            printf("----------------------\n");
            for (int i = 0; i < transaction_count; i++) {
                if (transaction_types[i] == 'D') {
                    printf("Deposit: +$%.2f\n", transactions[i]);
                } else {
                    printf("Withdrawal: -$%.2f\n", transactions[i]);
                }
            }
        } else if (choice == 5) {
            printf("Exiting the system...\nThank you for using our banking service!\n");
            break;
        } else {
            printf("Invalid choice! Please try again.\n");
        }
    }
    return 0;
}
