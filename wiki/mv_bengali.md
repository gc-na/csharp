# [লিনাক্স] C Shell (csh) mv ব্যবহার: ফাইল স্থানান্তর করা

## Overview
`mv` কমান্ডটি ফাইল এবং ডিরেক্টরি স্থানান্তর বা নাম পরিবর্তনের জন্য ব্যবহৃত হয়। এটি একটি খুবই গুরুত্বপূর্ণ এবং সাধারণভাবে ব্যবহৃত কমান্ড।

## Usage
`mv` কমান্ডের মৌলিক সিনট্যাক্স হলো:

```csh
mv [options] [arguments]
```

## Common Options
- `-i`: যদি গন্তব্যে একই নামের ফাইল থাকে, তাহলে ব্যবহারকারীকে নিশ্চিতকরণ করতে বলে।
- `-f`: যদি গন্তব্যে একই নামের ফাইল থাকে, তাহলে তা বিনা অনুমতিতে মুছে ফেলে।
- `-u`: শুধুমাত্র তখনই ফাইল স্থানান্তর করে যখন উৎস ফাইলটি গন্তব্য ফাইলের চেয়ে নতুন হয় বা গন্তব্য ফাইলটি নেই।

## Common Examples
- একটি ফাইল স্থানান্তর করা:

```csh
mv file1.txt /home/user/documents/
```

- একটি ফাইলের নাম পরিবর্তন করা:

```csh
mv oldname.txt newname.txt
```

- একটি ডিরেক্টরি স্থানান্তর করা:

```csh
mv /home/user/folder1 /home/user/folder2/
```

- নিশ্চিতকরণ সহ ফাইল স্থানান্তর করা:

```csh
mv -i file.txt /home/user/documents/
```

## Tips
- ফাইল স্থানান্তরের আগে সবসময় নিশ্চিত করুন যে গন্তব্যের পাথ সঠিক।
- `-i` অপশন ব্যবহার করা ভাল, বিশেষ করে যখন আপনি নিশ্চিত নন যে গন্তব্যে একই নামের ফাইল আছে কিনা।
- ফাইল স্থানান্তরের পরে, নিশ্চিত করুন যে ফাইলটি সঠিক স্থানে স্থানান্তরিত হয়েছে।