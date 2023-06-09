# while লুপ

আমরা যদি একই কাজ কম্পিউটার কে দিয়ে অনেক বার করাতে চাই তাহলে আমরা লুপ (চক্র?) ব্যবহার করি। বেশ কয়েক ধরনের লুপ আছে সি ল্যাংগুয়েজে – while, for, do-while ইত্যাদি। আজকে আমরা while লুপ নিয়ে আলোচনা করব।

নাম দেখেই নিশ্চয়ই বুঝতে পারছেন কম্পিউটারকে আমরা বলতে পারি “যতক্ষন” এই শর্ত পূরণ হবে “ততক্ষন” এই কাজ গুলো করতে থাক।

এটা কিভাবে লেখা হয় সেটা প্রথমে দেখে নেইঃ

## While Loop Syntax
প্রথমে আমরা লুপ এর স্ট্রাকচার দেখি

while([expression])
{
    [Statement Block]
}
এখানে একটি বুলিয়ান এক্সপ্রেশন আছে যেটা ঠিক করে দিবে যে লুপের স্টেটমেন্ট ব্লকের স্টেটমেন্ট গুলো এক্সিকিউট হবে কিনা। লুপের শুরুতেই কম্পিউটার এক্সপ্রেশন এর মান বের করবে। এটা যদি True হয় তাহলে ব্লকের স্টেটমেন্ট গুলো এক্সিকিউট হবে। ব্লকের স্টেটমেন্ট গুলো এক্সিকিউট করে তারপর কম্পিউটার .
আবার এক্সপ্রেশনের মান নতুন করে বের করবে। মান যদি আবারও True হয় তাহলে ব্লকের স্টেটমেন্ট গুলো আবার এক্সিকিউট হবে। এভাবে যতক্ষন এক্সপ্রেশনের মান True হবে ততক্ষন এই লুপ বা চক্র চলবে। এক্সপ্রেশনের মান যখন False হবে তখন লুপ থেমে যাবে এবং কম্পিউটার লুপের পরে যা আছে সেটা নিয়ে কাজ শুরু করবে।

### While loop example
এবারে লুপের একটা উদাহরণ দেখিঃ

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
এখানে আমরা ২ নম্বর লাইনে num ভেরিয়েবলের মধ্যে 0 রাখছি। এর পর ৪ নম্বর লাইনে লুপ শুরু হয়েছে। এই লুপটি আমরা কয়েকটি ধাপে কিভাবে কাজ করবে তা দেখব।

১ম ধাপঃ
৪ নম্বর লাইনে num ভরিয়েবলের মান 0 সুতরাং (num<4) এক্সপ্রেশনের মান True. সুতরাং ৫-৮ লাইনগুলো এক্সিকিউট হবে।
৫ নম্বর লাইনে লুপের ব্লক শুরু
৬ নম্বর লাইনের জন্য আমরা 0 আউটপুট দেখতে পাব।
৭ নম্বর লাইনে num এর মান শূণ্য থেকে 1 বেড়ে num=1 হবে।
৮ নম্বর লাইনে while লুপের ব্লক শেষ সুতরাং কম্পিউটার ৪ নম্বর লাইনে ফিরে যাবে।

২য় ধাপঃ
৪ নম্বর লাইনে num ভরিয়েবলের মান 1 সুতরাং (num<4) এক্সপ্রেশনের মান True. সুতরাং ৫-৮ লাইনগুলো এক্সিকিউট হবে।

৬ নম্বর লাইনের জন্য আমরা 1 আউটপুট দেখতে পাব।
৭ নম্বর লাইনে num এর মান 1 থেকে 1 বেড়ে num=2 হবে।
৮ নম্বর লাইনে কম্পিউটার এসে দেখবে while লুপের ব্লক শেষ সুতরাং ৪ নম্বর লাইনে ফিরে যাবে।

৩য় ধাপঃ
৪ নম্বর লাইনে num ভরিয়েবলের মান 2 সুতরাং (num<4) এক্সপ্রেশনের মান True. সুতরাং ৫-৮ লাইনগুলো এক্সিকিউট হবে।

৬ নম্বর লাইনের জন্য আমরা 2 আউটপুট দেখতে পাব।
৭ নম্বর লাইনে num এর মান 2 থেকে 1 বেড়ে num=3 হবে।
৮ নম্বর লাইনে কম্পিউটার এসে দেখবে while লুপের ব্লক শেষ সুতরাং ৪ নম্বর লাইনে ফিরে যাবে।

৪র্থ ধাপঃ
৪ নম্বর লাইনে num ভরিয়েবলের মান 3 সুতরাং (num<4) এক্সপ্রেশনের মান True. সুতরাং ৫-৮ লাইনগুলো এক্সিকিউট হবে।

৬ নম্বর লাইনের জন্য আমরা 3 আউটপুট দেখতে পাব।
৭ নম্বর লাইনে num এর মান 3 থেকে 1 বেড়ে num=4 হবে।
৮ নম্বর লাইনে কম্পিউটার এসে দেখবে while লুপের ব্লক শেষ সুতরাং ৪ নম্বর লাইনে ফিরে যাবে।

৫ম ধাপঃ
৪ নম্বর লাইনে num ভরিয়েবলের মান 4 সুতরাং (num<4) এক্সপ্রেশনের মান False. সুতরাং ৫-৮ লাইনগুলো এবার আর এক্সিকিউট হবে না।
কম্পিউটার ৯ নম্বর লাইনে চলে যাবে পরবর্তী কাজগুলো (যদি থাকে) করার জন্য এবং লুপ এভাবে শেষ হল।


## Infinite loop

আমরা দেখেছি while লুপের এক্সপ্রেশনের মান False হয়ে গেলে লুপ শেষ হয়। কিন্তু যদি আমরা এমনভাবে এক্সপ্রেশন লিছি যে এর মান কখনও False হবে না তাহলে while লুপ আসলৈ কখনও থামবে না। উপরের উদাহরণে আমরা দেখেছি num ভেরিয়েবলের মান পরিবর্তন করতে থাকার ফলে এক সময় লুপের এক্সপ্রেশনের মান False হয়ে লুপ থেমে যায়। কিন্তু আমরা যদি নীচের মত করে লিখি-

১. int num;
২. num=0;
৩.
৪. while(num<4)
৫. {
৬.     printf("%d",num);
৭.
৮. }
৯.
১০.
তাহলে এখন num ভেরিয়েবলের মান পরিবর্তন হওয়ার কোন সম্ভবনা নাই এবং লুপও থামবে না। এটা একটা সহজ উদাহরণ। কিন্তু অনেক সময় প্রোগ্রামে বাগ থাকার কারনে এরকম অবস্থার সৃষ্টি হতে পারে। বা অনেক সময় এরকম করার দরকার হতে পারে।
