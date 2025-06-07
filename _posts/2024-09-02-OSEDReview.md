---
title:  "My Offensive Security OSED Review"
published: true
tag: Security
category: Course Review
---
## The Breakthrough

On December 19th, 2023, at 5:30 PM, I nervously began my second attempt at the OSED exam. My first attempt on October 31st had ended in disappointment, but I had spent the following months working tirelessly to prepare. To my surprise, by the eight-hour mark, I had already earned enough points to pass the exam, having successfully completed 2 out of the 3 challenges.

The hard work paid off. I submitted my report on December 22nd at 2:30 AM, and after two anxious days of waiting, I woke up on the morning of December 24th at 7:00 AM to find an email that changed everything:

![OSED](../images/osed.png)

I couldn't believe it—I had just passed my first cybersecurity certification! At 19, I am one of the youngest Indians to pass the exam. After months of sleepless nights and relentless preparation, I had finally achieved my goal. It was the perfect Christmas Eve gift, and a moment I will never forget.

I will walk through my entire journey of preperation for OSED in this post.

## OSED Overview (according to Offsec)

The OffSec Exploit Developer (OSED) exam is a challenging, proctored 48-hour assessment that simulates a live network containing several vulnerable systems. You are tasked with exploiting these systems and providing proof of exploitation. Offsec's <ins>Windows user mode exploit development course (EXP-301)</ins> provides a comprehensive understanding of modern exploit development techniques. Successful completion of the online training course and passing the associated exam earns the OffSec Exploit Developer (OSED) certification. This certification validates expertise in advanced exploit development techniques, including reverse engineering, writing shellcode, and bypassing modern mitigations, making certified professionals invaluable for identifying and addressing vulnerabilities in software applications.

## What to expect !?

You can expect to learn the basics of Windows Userland Exploit Development, from Reverse Engineering to Bypassing protections and creating full-fledged exploits, and even writing your own custom shellcode.

## What not to expect !?

You will not be a crazy zero-day hunter after completing the course. It will only provide you with foundational knowledge required to get started with exploit development. Also, no Heap exploitation techniques, fuzzing, or Kernel exploitation. These topics are reserved for the AWEE (Advanced Windows Exploitation Expert) Exam.

## My Background

Before buying my Learn-One voucher, I had some background with binary exploitation on Linux through CTF challenges. I had been participating in CTFs for years, hence I had some prerequisite knowledge about buffer overflows and memory corruption vulnerabilities. I was quite well-versed with the Pwntools library and was very comfortable using a debugger like GDB. So, I was not new to memory corruption vulnerabilities, and hence, I thought this cert would be a cakewalk for me (I was very wrong 😭).

## How I prepared for the Exam 

In the initial months, I started working on the prerequisites for the course, i.e., x86 assembly. I learned assembly from Open Security Training. Thanks to Xeno Kovah for this amazing course! In a month, studying part-time (alongside my college), I was able to complete the entire course on x86 assembly (The entire course is a bit of an overkill; you probably need only a few lectures to jump onto the EXP-301 course).

Then, I moved on with the course curriculum, which is well-structured and covers all the topics in detail. I recommend creating your own Windows x86 VM for practicing everything locally before jumping onto the course.


1. **Windows User Mode Exploit Development: General Course Information:** General information about the course and exam.

2. **WinDbg and x86 Architecture:**  This is a foundational chapter covering x86 assembly and WinDbg commands. Make sure to take good notes of the WinDbg commands, as we are going to use them throughout the course.

3. **Exploiting Stack Overflows:** This chapter covers vanilla stack overflows and is overall a great introduction to binary exploitation and buffer overflows.

4. **Exploiting SEH Overflows:** This section goes in-depth about SEH and its mechanism and structure, followed by exploiting an SEH overflow. They also introduce you to extensions in WinDBG.

5. **Introduction to IDA Pro:** It's a great introduction to IDA Free (It's actually IDA Free; IDA Pro is not even allowed in the exam). Anyway, this chapter introduces you to IDA and how to use it.

6. **Overcoming Space Restrictions: Egghunters:** In-depth chapter on egghunters, also a great introduction to the Keystone Engine library.

7. **Creating Custom Shellcode:** This one is my absolute favorite. There are not many good resources to study custom shellcode online, and this chapter covers how to create your own shellcode really well.

8. **Reverse Engineering for Bugs:** This was a follow-along chapter where they guide you through how to find bugs while performing Reverse Engineering.

9. **Stack Overflows and DEP Bypass:** This chapter is a great introduction to ROP (Return Oriented Programming) and how to create ROP chains. (Make sure to take good notes on this chapter).

10. **Stack Overflows and ASLR Bypass:** Excellent module on multiple ways to bypass ASLR.

11. **Format String Specifier Attack Part I:** Didn't actually complete this chapter before my exam, reviewed it after my exam, and it's a fair introduction to format string vulnerabilities (I wish there was more content).

12. **Format String Specifier Attack Part II:** his is a follow-up chapter to the previous one. We complete the exploit chain of bypassing all protections and getting code execution.

## The Exam

Can't reveal much about the exam, but it was great. It's fairly challenging and requires you to "Try Harder." I failed my first attempt because I didn't practice much and did not complete any of the extra miles. But in the second attempt, I completed nearly all the extra miles and solved 2 of the 3 challenge labs, which I definitely recommend doing before starting the examination. Before you attempt the exam, make sure:

- You are very comfortable creating ROP chains. (Good notes are the key).
- You are comfortable writing custom shellcode using the Keystone Engine. (Practice calling multiple different Windows APIs).
- Your Reverse Engineering is on point. (Practice Practice Practice).

## Additional Resources

Thanks to these resources and their respective authors, who made my life easier and helped me pass the exam:

[Nop's OSED Notes](https://github.com/nop-tech/OSED): A great compilation of learning resources.

[Epi's OSED Scripts](https://github.com/epi052/osed-script): Saved a lot of time during the exam and practice.

[Readable WinDBG Theme](https://github.com/nextco/windbg-readable-theme): Highly recommended for efficiency.

[CodeCaver Script](https://github.com/nop-tech/code_caver): Automatically finds code caves in a binary.


## The Community

The OffSec Discord community is awesome. If you have any questions or are stuck somewhere, you can post your questions on the Discord server, and someone will generously help you out. If you have any doubts or need help with the challenge labs, feel free to DM me on Discord <ins>(Username: ap425q)</ins>.

## Conclusion

To conclude my final thoughts, OSED is great if you want to start your vulnerability research and exploit development journey. It will help you build the basics required to get started in vulnerability research. Although I would have loved if OffSec added more topics like x64 exploitation and fuzzing to the curriculum as well. Overall, it's a very enjoyable and great certification.

## What Next !?

After completing this certification, I plan to dive deeper into advanced topics like kernel exploitation and start hunting vulnerabilities in modern software using the skills I've gained along the way. On top of that, I'm currently preparing for the PNPT exam to further expand my knowledge of Active Directory(PS : I passed PNPT on Dec 28, 2024 😁)

{% include comment.html %}