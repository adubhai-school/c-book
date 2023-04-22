# For লুপ

আমরা while লুপ এর ব্যবহার দেখেছি। এখন আমরা এর চেয়ে আরকটু বেশি ফিচারের for লুপ নিয়ে আলোচনা করব। সব ক্ষেত্রেই এই দুইটা লুপ একে অপরকে প্রতিস্থাপন করতে পারে সামান্য কিছু পরিবর্তন করে।

## for লুপের সিনট্যাক্স
for( [init-stmt] ; [condition] ; [increment-stmt] )
{
[Block]
}

লুপের [init-stmt] এর স্থানে এক বা একাধিক ভেরিয়েবলের মান অ্যাসাইন করা যায়। [condition] একটি বুলিয়ান এক্সপ্রেশন। এই এক্সপ্রেশনের মান যতক্ষন True থাকবে ততক্ষন লুপ চলবে while লুপের মতই।

শেষের [increment-stmt] এর যায়গায় এক বা একাধিক ভেরিয়েবলের মান পরিবর্তন করা যাবে। এখানে সেমিকোলন দিয়ে তিনটি অংশ আলাদা করা হয়েছে। আমরা ইচ্ছা করলে যেকোন অংশ বাদ দিতে পারি বা সবগুলোও বাদ দিতে পারি। তবে সেমিকোলন গুলো আবশ্যিক। যেমন এভাবে লেখা যাবেঃ

for( ; ; )
{
    [Block]
}
এক্ষেত্রে লুপই কখনও থামবে না। লুপ থামাতে চাইলে break ব্যবহার করতে হবে। break ব্যবহার করে for বা while লুপ যেকোন সময় থামিয়ে দেয়া যায়।

এবার আমরা আগের while লুপটাকে পরিবর্তন করব for লুপ ব্যবহার করে।

১. int num;
২. num=0;
৩.
৪. while(num<4)
৫. {
৬.     printf("%d",num);
৭.     num=num+1;
৮. }
৯.
১০.
উপরের প্রোগ্রামটা for লুপ ব্যবহার করে এভাবে লেখা যায়ঃ

১. int num;
২. num=0;
৩.
৪. for( ; num<4 ; )
৫. {
৬.     printf("%d",num);
৭.     num=num+1;
৮. }
৯.
১০.

এখানে আমরা তেমন কোন পরিবর্তন করি নাই। শুধু for লুপ ব্যবহার করেছি এবং while লুপের কন্ডিশনটা for লুপের কন্ডিশন যেখানে লেখার কথা (একটা সেমিকোলনের পর) সেখানে লিখেছি। এটা হুবহু একই কাজ করবে – যদিও এক্ষেত্রে আমরা for লুপ ব্যবহার করেছি।

এবার আমরা num=0 অংশটা for লুপের মধ্যে নিয়ে যাই।

১. int num;
২.
৩.
৪. for(num=0 ; num<4 ; )
৫. {
৬.     printf("%d",num);
৭.     num=num+1;
৮. }
৯.
১০.
num=0 টাকে আমরা লুপের [init-stmt] এর স্থানে (প্রথম সেমিকোলনের আগে) লিখেছি। এক্ষেত্রেও প্রোগ্রামটা হুবহু প্রথম প্রোগ্রামের মত কাজ করবে।

এবারে সর্বশেষ কাজ হচ্ছে num=num+1 স্টেটমেন্টটাকে for লুপর মধ্যে নিয়ে যাওয়াঃ

১. int num;
২.
৩.
৪. for(num=0 ; num<4 ; num=num+1 )
৫. {
৬.     printf("%d",num);
৭.
৮. }
৯.
১০.
এবারেও প্রোগ্রামের কাজের কোন পরিবর্তন হল না তবে অনেক সংক্ষিপ্ত হয়ে গেল।

এবার নীচের ভিডিওতে for এবং while লুপ ব্যবহার করে লেখা দুইটা প্রোগ্রামের তুলনাশূলক আলোচনা দেখুন।
