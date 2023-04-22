কম্পিউটার ব্যবহারকারী মাত্রই ফাইল বিষয়ে ধারণা রাখেন। এই ফাইলগুলো বিভিন্ন প্রগ্রাম তৈরি করে থাকে। আমারা আমাদের প্রোগ্রাম থেকে অনুরুপ ফাইল তৈরি এবং সেগুলো পরে ব্যবহার বা পরিবর্তন করতে পারি।

ফাইল আমরা মূলতঃ তিন ধাপে ব্যবহার করি-

১. ফাইল খোলা
২. ফাইল থেকে কোন কিছু পড়া বা ফাইলে কিছু লেখা
৩. ফাইল বন্ধ করা

ফাইল ব্যবহারের জন্য আমাদের একটা ফাইল handle দরকার। এটার মাধ্যমে আমরা একটা ফাইরকে চিহ্নিত করি। এটা FILE টাইপের একটা পয়েন্টার যেটাকে এভাবে ডিক্লেয়ার করতে হয়ঃ

```c
FILE *fp;
```

`fopen` দিয়ে একটা ফাইল খুললে আমরা এটা রিটার্ন পাই।

## fopen
fp = fopen(filename, mode);

একটা ফাইল খোলার জন্য এই ফাংশনটা ব্যবহার কারা হয়। এই ফাংশনের দুইটি প্যারামিটার আছে। প্রথমটা ফাইলের নাম এবং দ্বিতীয়টা ফাইল খোলার পর কিভাবে ব্যবহার করা হবে সেটা প্রথমেই বলে দিতে হবে।

r – read মোডে ফাইল খোলা হবে। ফাইল আগে থেকে না থাকলে এভাবে ব্যবহার করলে FILE পয়েন্টার রিটার্ন করবে না।
w – read মোডে ফাইল খোলা হবে। ফাইল না থাকলে নতুন একটা ফাইল তৈরি হবে। ফাইল আগে থেকে থাকলে ফাইলের সব ডাটা মুছে যাবে এবং ফাইলের প্রথম থেকে লেখে হবে।
a – append- আগে থেকে আছে এরকম ফাইলের শেষে থেকে লেখা শুরু করার জন্য এই মোড ব্যবহার করা হয়। ফাইল না থাকলে নতুন একটা ফাইল তৈরি হবে।

+ ব্যবহার করে একই সাথে read এবং write করা যায়। এরপর ব্যবহার করে কিভাবে বা হবে সেটা ঠিক করা যায়।

r+ – একই সাথে লেখা এবং পড়ার দরকার হলে এবং ফাইলের শুরু থেকে পড়া শুরু করার জন্য এই মোড ব্যবহার করা হয়।
w+ – একই সাথে লেখা এবং পড়ার দরকার হলে এবং ফাইলের শুরু থেকে লেখা শুরু করার জন্য এই মোড ব্যবহার করা হয়। ফাইল না থাকলে নতুন একটা ফাইল তৈরি হবে।
a+ – একই সাথে লেখা এবং পড়ার দরকার হলে এবং ফাইলের শেষে লেখা শুরু করার জন্য এই মোড ব্যবহার করা হয়। ফাইল না থাকলে নতুন একটা ফাইল তৈরি হবে।

নীচে কয়েকটি উদাহরণ দেখি।

একটা ফাইল খুলে কোন কিছু লেখার জন্য এভাবে ফাইল ওপেন করা যায়ঃ

```c
fp = fopen("myfile.txt", "w");
```

তাহলে myfile.txt নামে একটি ফাইল তৈরি হবে যেটার মধ্যে আমরা লিখতে পারব।

read মোডে ফাইল খোলার জন্য এভাবে লিখতে হবেঃ
```c
fp = fopen("names.txt", "r");
```
এখানে names.txt ফাইলটি থাকতে হবে। তাহলে আমরা এখন এই ফাইল থেকে পড়তে পারব।

## fprintf

এই ফাংশনটি printf এর মত তবে এটা ফাইলে লেখার জন্য ব্যবহার করা হয়।

যেমন আমরা যদি এভাবে লিখি
```c
printf("Hello, World!");
```

তাহলে কনসোলে Hello, World! লেখা হবে।

fprintf এর ক্ষেত্রেও তাই- শুধু ফাইল handle টা দিয়ে দিতে হবে।

```c
fprintf(fp, "Hello, World!");
```
তাহলে ফাইলে Hello, World! লেখা হবে।

## fscanf

এই ফাংশনটি scanf এর মত তবে এটা ফাইল থেকে পড়ার জন্য ব্যবহার করা হয়।

যেমন আমরা যদি এভাবে লিখি

```c
int num;
scanf(“%d”, &num);
```

তাহলে কিবোর্ড থেকে একটা পুর্ণসংখ্যা ইনপুট নিয়ে num ভেরিয়েবলে রাখা হবে।

fscanf এর ক্ষেত্রেও তাই- শুধু ফাইল handle টা দিয়ে দিতে হবে।

```c
int num;
fscanf(fp, “%d”, &num);
```
তাহলে ফাইল থেকে একটা পুর্ণসংখ্যা পড়ে নিয়ে num ভেরিয়েবলে রাখা হবে।

## fclose
ফাইল ব্যবহার শেষে ফাইলটি বন্ধ করার জন্য এই ফাংশন ব্যবহার করতে হবে।

এভাবে লিখলে ফাইল বন্ধ হবেঃ
```c
fclose(fp);
```
একটা সম্পুর্ণ উদাহরণ দেখিঃ

```c
#include "stdio.h"

int main()
{
    FILE *fp;

    fp = fopen("myfile.txt", "w");

    fprintf(fp, "Hello, World!n");

    fclose(fp);

    return 0;
}
```
এটা রান করলে একটা ফাইল তৈরি হবে এবং তাতে Hello, World! লেখা হবে। আপনারা ফাইলটি খুলে দেখতে পারেন ঠিকমত লেখা হল কিনা।

আরও কয়েকটি ফাংশনের নাম জেনে রাখুন যেগুলো দিয়ে ফাইল থেকে পড়া বা ফাইলে লেখা যায়।
```c
fputc
fgetc
fread
fwrite
ftell
fseek
fflush
```