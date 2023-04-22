সি ল্যাংগুয়েজে আমরা বিভিন্ন সময় স্ট্রিং ব্যবহার করি। সি ল্যাংগুয়েজে স্ট্রিং বলতে সাধারনত বোঝায় এক বা একাধিক অক্ষরের সমন্বয়ে গঠিন একটা শব্দ বা বাক্য যার শেষে একটা NULL ক্যারেকটার (যেটা আসলে শূন্য) থাকে।

নিচে কয়েকটি স্ট্রিং এর উদাহরণ দেখি-

“আমার সোনার বাংলা”
“Hello World”
“Sirajganj”
“I”

একটা অক্ষর থাকলেও সেটা স্ট্রিং হতে পারে। সিংগেল কোট দিয়ে ‘I’ এভাবে লিখরে সেটা স্ট্রি হবে না।

এই স্ট্রিংগুলা আমরা সরাসরি কনসলে প্রিন্ট করতে পারি-

printf(“Hello World”);

ব্যবহারকারী থেকে একটা স্ট্রিং ইনপুট নেয়ার জন্য আমরা scanf বা gets ফাংশন দুটি ব্যবহার করি। একটা শব্দ ইনপুট নেয়ার জন্য scanf এবং পুরো লাইন ইনপুট নেয়ার জন্য gets ব্যবহার করা সুবিধাজনক। scanf ব্যবহার করে অবশ্য যে কোন ধরণের ইনপুট নেয়া সম্ভব। নীচে আমরা দুটি য়াংশনেরই কয়েকটি উদাহরণ দেখব।

প্রথমে আমরা দেখি স্টিং এর ইনপুট আউটপুট।

#include "stdio.h"

int main(int argc, char* argv[])
{
    char name[50];

    printf("Enter your name: ");
    scanf("%s", name);
    printf("Hello %sn", name);

    return 0;
}
নীচে প্রোগ্রিমটি ২ বার রান করে প্রথমবার Manir এবং দ্বিতীবার Maruf Maniruzzaman ইনপুট হিসাবে কিবোর্ডে টাইপ করা হয়েছে। দ্বিতীয় ক্ষেত্রে শুধু প্রথম শব্দটি ইনপুটে এসেছে।

Enter your name: Manir
Hello Manir

Enter your name: Maruf Maniruzzaman
Hello Maruf
এখন আমরা চাই পুরো লাইন ইনপুট নিতে-

#include "stdio.h"

int main(int argc, char* argv[])
{
    char name[50];

	printf("Enter your name: ");
	gets(name);
	printf("Hello %sn", name);

	return 0;
}
একবার রান করে আউটপুট দেখি

Enter your name: Maruf Maniruzzaman
Hello Maruf Maniruzzaman
stpcpy
একটা স্ট্রিংকে আরেকটা স্টিং ভেরিয়েবলের মধ্যে কপি করার জন্য আমরা stpcpy ব্যবহার করি

এই ফাংশনের প্রোটোটাইপ এরকমঃ

char *stpcpy (const char *dest,const char *src)
উদাহরণঃ

#include "stdio.h"
#include "string.h"

int main(int argc, char* argv[])
{
    char str1[50], str2[100];

    printf("Enter something: ");
    gets(str1);
    strcpy(str2, str1);
    printf("You entered: %sn", str2);
    return 0;
}
রান করে আউটপুট দেখি

Enter something: Hello world.
You entered: Hello world.
strcmp
দুইটা স্ট্রিং এর তুলনা করতে আমরা ব্যবহার strcmp করি

এই ফাংশনের প্রোটোটাইপ এরকমঃ

int strcmp(const char *string1,const char *string2)
উদাহরণঃ

#include "stdio.h"
#include "string.h"

int main(int argc, char* argv[])
{
    char str1[50], str2[100];

    printf("Enter first string: ");
    gets(str1);
    printf("Enter second string: ");
    gets(str2);

    int comp = strcmp(str1, str2);

    if(comp == 0)
    {
        printf("The strings are same.n");
    }
    else if(comp < 0)
    {
        printf("First string  < second string.n)
    }
    else
    {
        printf("First string > second string.n");
    }

    return 0;
}
রান করে আউটপুট দেখি।

দুইবার বার করা হয়েছে। প্রথমবার দুইবারই একই স্ট্রিং ইনপুট দিয়েছি। দ্বিতীয়বার দুাইটা আলাদা স্ট্রিং ইনপুট দিয়েছি-

Enter first string: test string
Enter second string: test string
The strings are same.

Enter first string: apple
Enter second string: banana
First string second string.

strlen
একটা স্ট্রিং এর দৈর্ঘ্য কত সেটা বের করার জন্য আমরা strlen ব্যবহার করি
এই ফাংশনের প্রোটোটাইপ এরকমঃ

int strlen(const char *string)
উদাহরণঃ

#include "stdio.h"
#include "string.h"

int main(int argc, char* argv[])
{
    char str1[50];

    printf("Enter something: ");
    gets(str1);

    int length = strlen(str1);

    printf("You entered a string of length %dn", length);

    return 0;
}
Enter something: I love Bangladesh.
You entered a string of length 18
একটা স্ট্রিংকে আরেকটা স্ট্রিং এর সাথে জোড়া লাগানোর জন্য আমরা ব্যবহার করি

এই ফাংশনের প্রোটোটাইপ এরকমঃ

char *strncat(const char *string1, char *string2, size_t n)
উদাহরণঃ

#include "stdio.h"
#include "string.h"

int main(int argc, char* argv[])
{
    char str1[150], str2[100];

    printf("Enter first string: ");
    gets(str1);
    printf("Enter second string: ");
    gets(str2);

    int len = strlen(str2);

    strncat(str1, str2, len);

    printf("%sn", str1);

    return 0;
}
Enter first string: Hello
Enter second string:  World!!
Hello World!!
আরও কিছু ফাংশন আছে যেগুলো আপনারা নিজেরা চেষ্টা করে দেখতে পারেন। প্রথমবার না করলেও সমস্যা নাই। তবে শুধো মনে রাখুন এরকম কয়েকটা ফাংশন আছে।

দুইটা স্ট্রিংকে তুলনা করার সময় প্রথম n অক্ষর তুলনা করার জন্য আমরা strncmp ব্যবহার করি
int strncmp(const char *string1, char *string2, size_t n)

একটা স্ট্রিংয়ের প্রথম n অক্ষর আরেকটা স্ট্রিং এর সাথে জোড়া লাগানোর জন্য আমরা strncpy ব্যবহার করি
char *strncpy(const char *string1,const char *string2, size_t n)

দুইটা স্ট্রিং এর তুলনা করতে আমরা strcasecmp ব্যবহার করি যখন আমরা ছোট বা বড় হাতের অক্ষরকে আলাদা করে বিবেচনা করতে চাই না
int strcasecmp(const char *s1, const char *s2)

দুইটা স্ট্রিংকে তুলনা করার সময় প্রথম n অক্ষর তুলনা করার জন্য আমরা strncasecmp ব্যবহার করি যখন আমরা ছোট বা বড় হাতের অক্ষরকে আলাদা করে বিবেচনা করতে চাই না
int strncasecmp(const char *s1, const char *s2, int n)
