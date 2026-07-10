# Student-Meal-Manegment
#include <stdio.h>

struct Student {
    int id;
    char name[50];
    float cgpa;
};

int main() {

    struct Student s[100];
    int choice;
    int total = 0;
    int i, searchId;
    int found = 0;

    while(1){

        printf("\n==============================\n");
        printf(" STUDENT MANAGEMENT SYSTEM\n");
        printf("==============================\n");
        printf("1. Add Student\n");
        printf("2. View Students\n");
        printf("3. Search Student\n");
        printf("4. Update Student\n");
        printf("5. Delete Student\n");
        printf("6. Exit\n");

        printf("\nEnter Choice : ");
        scanf("%d",&choice);

        switch(choice){

        case 1:

            printf("\nHow many students : ");
            int n;
            scanf("%d",&n);

            for(i=0;i<n;i++){

                printf("\nStudent %d\n",total+1);

                printf("ID : ");
                scanf("%d",&s[total].id);

                printf("Name : ");
                scanf("%s",s[total].name);

                printf("CGPA : ");
                scanf("%f",&s[total].cgpa);

                total++;
            }

            printf("\nStudents Added Successfully.\n");

            break;

        case 2:

            if(total==0){

                printf("\nNo Student Found.\n");
            }

            else{

                printf("\n------Student List------\n");

                for(i=0;i<total;i++){

                    printf("\nStudent %d\n",i+1);
                    printf("ID : %d\n",s[i].id);
                    printf("Name : %s\n",s[i].name);
                    printf("CGPA : %.2f\n",s[i].cgpa);

                }

            }

            break;

        case 3:

            found=0;

            printf("\nEnter ID : ");
            scanf("%d",&searchId);

            for(i=0;i<total;i++){

                if(s[i].id==searchId){

                    printf("\nStudent Found\n");
                    printf("ID : %d\n",s[i].id);
                    printf("Name : %s\n",s[i].name);
                    printf("CGPA : %.2f\n",s[i].cgpa);

                    found=1;
                }

            }

            if(found==0){

                printf("\nStudent Not Found.\n");
            }

            break;

        case 4:

            found=0;

            printf("\nEnter ID to Update : ");
            scanf("%d",&searchId);

            for(i=0;i<total;i++){

                if(s[i].id==searchId){

                    printf("New Name : ");
                    scanf("%s",s[i].name);

                    printf("New CGPA : ");
                    scanf("%f",&s[i].cgpa);

                    printf("\nUpdated Successfully.\n");

                    found=1;

                }

            }

            if(found==0){

                printf("\nStudent Not Found.\n");
            }

            break;

        case 5:

            found=0;

            printf("\nEnter ID to Delete : ");
            scanf("%d",&searchId);

            for(i=0;i<total;i++){

                if(s[i].id==searchId){

                    int j;

                    for(j=i;j<total-1;j++){

                        s[j]=s[j+1];

                    }

                    total--;

                    printf("\nDeleted Successfully.\n");

                    found=1;

                    break;

                }

            }

            if(found==0){

                printf("\nStudent Not Found.\n");
            }

            break;

        case 6:

            printf("\nThank You.\n");

            return 0;

        default:

            printf("\nInvalid Choice.\n");

        }

    }

}
