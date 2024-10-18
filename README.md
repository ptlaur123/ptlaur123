
#include <stdio.h>

int main() {
    int a1 = 1000, a2 = 2000, a3 = 3000, choice, acc, amount;

    while (1) {
        printf("\nBanking System\n");
        printf("1. Deposit\n");
        printf("2. Withdraw\n");
        printf("3. Check Balance\n");
        printf("4. Exit\n");
        scanf("%d", &choice);

        printf("Enter account number (1/2/3): ");
        scanf("%d", &acc);

        switch (choice) {
            case 1:
                scanf("%d", &amount);
                if (acc == 1) a1 += amount;
                else if (acc == 2) a2 += amount;
                else if (acc == 3) a3 += amount;
                break;

            case 2:
                scanf("%d", &amount);
                if (acc == 1 && a1 >= amount) a1 -= amount;
                else if (acc == 2 && a2 >= amount) a2 -= amount;
                else if (acc == 3 && a3 >= amount) a3 -= amount;
                break;

            case 3:
                if (acc == 1) printf("Balance: %d\n", a1);
                else if (acc == 2) printf("Balance: %d\n", a2);
                else if (acc == 3) printf("Balance: %d\n", a3);
                break;

            case 4:
                return 0;

            default:
                printf("Invalid choice.");
        }
    }
}
