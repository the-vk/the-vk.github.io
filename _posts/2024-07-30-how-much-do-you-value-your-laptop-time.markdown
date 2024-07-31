---
layout:     single
title:      "How Much Do You Value Your Laptop Time?"
date:       2024-07-30 18:30:00 -0700
categories: blog
tags:       hardware cloud p2p
---
My laptop CPU is idle most of the time as expected.

What could be the potential value of the CPU time if it is loaded at 100%?

<!--more-->

Idle CPU is a resource waste. CPU could be doing something useful, folding proteins 
or solving other science mysteries. Instead, it's just idle, doing nothing.

The CPU value is in number crunching. I don't pretend this is scientifically rigorous research
so, I'll do the most basic benchmark: millions integer operations per second aka MIPS.

7-Zip is a nice option to run estimations. It is a console benchmark, multi-threaded by default, and prints a nice result summary.
What's not to like?

I need to establish a baseline. Who are the best sellers of CPU time today?

## Public Cloud Providers

... of course. Public cloud providers commodized CPU time over the last few years.
Cloud is not the cheapest option, but if you need a heterogeneous zoo of various compute resources at distance of a one click, 
then it's your best bet.

I'll go with Microsoft Azure and Google Cloud Platform. Nothing wrong with AWS, I presume it will give similar data points.

Cheap tiny 2 vCPU machines are very popular. It's a crime to overlook tiny VMs for this benchmark exercise.
I should use compute-optimized VM types for variety albeit it is more expensive.

Without further ado, here are the results.

![Azure benchmack](/assets/images/2024-07-30-azure-small.png)

![Google benchmack](/assets/images/2024-07-30-google-small.png)

As of today, pricing is as following

|Provider|Machine type |Price $/hour|
|--------|-------------|------------|
|Azure   |d2s v3       |$0.096      |
|Azure   |f8s v2       |$0.3380     |
|Google  |n2-standard-2|$0.0971     |
|Google  |c2d-highcpu-8|$0.2998     |

## My Equipment

I have a laptop ThinkPad X1 Carbon Gen 8 with Intel i7 10510U, a desktop with AMD Ryzen 7 5800x,
and another desktop with Intel i7 2600K. It's not much, but it's honest work.

I use WSL on my laptop a lot in work, so let's include that in the benchmark too.

### Intel i7 10510U

The Intel i7 10510U is a low-voltage CPU for ultrabooks. I don't expect spectacular numbers.

![Intel i7 10510U Results](/assets/images/2024-07-30-intel-10510u-small.png)

Huh. 5-year-old CPU can hold its own against Azure compute optimized VM? Not too bad.
The CPU frequency stayed in range 3GHz to 3.3GHz before thermal
throttling kicked in and CPU reduced frequency to about 2.9Ghz.

The benchmark runs with 8 threads even though the CPU has just 4 cores. Behold, HyperThreading magic!
That makes me think that Azure sells virtual HyperThread cores as vCPUs because 10510U numbers are very close to f8s.

WSL numbers are about 20% less. That is reasonable; WSL is a virtualized environment a-la Hyper-V VM.

Let's move to desktop CPUs.

### Intel i7 2600K

i7 2600K was the CPU for enthusiasts back in the day. It's merely adequate today as the CPU is very old and not efficient.

![Intel i7 2600K Results](/assets/images/2024-07-30-intel-i7-2600k-small.png)

Well, well, well. Oldie but goodie 2600K is noticeable faster than 10510U.
Not a shocker, it's not restricted by thermal output.

### AMD Ryzen 7 5800X

And last but not the least, Ryzen 7 5800X. It is a beast of its own despite being 3.5 years old.

![AMD Ryzen 7 5800X Results](/assets/images/2024-07-30-amd-ryzen-7-5800x-small.png)

AMD Ryzen 7 5800X crunches integers at 96249 MIPS. What a sight to behold!
Frequency stayed steady at 4.49GHz - 4.5GHz. Combo of an efficient heat sink and a cooler prevents thermal throttling.

Okay, enough with data samples. Time for value estimations!

## My laptop CPU hour is...

... in the range $0.2115 - $0.4311. Comparable Azure f8s VM costs $0.3380.

Here are the estimations in full glory.

![CPU time value](/assets/images/2024-07-30-spreadsheet.png)

Column E has the most interest for us. It shows value of the CPU time at lowest and highest price points of the
cloud VMs. Who knew it could be that high?

One surprise for me is that 1 month of the CPU time is about 5x of the CPU price today.
5800X cost is $179 - $199 online as of 2024-07-30.

Another surprise is the lackluster benchmark numbers of the cloud VMs. Infrastructure elasticity
and lack of need to maintain physical aspects of compute resources go a long way, but the premium is quite high.

Also, notice that cost in $/MIPS goes down as I progress to beefier VM types. The adage
"a fleet of small machines is better than one big server" may not be exactly true when it comes to cloud.

If performance is all you need, just go with the largest compute-optimized cloud VM. Or rent a dedicated machine from
Hetzner or similar company. But the best option may very well be to purchase a real server and put it in a rented 
rack space of a colocation data center.

Some may say, "But, hey! Isn't it not reliable to run everything from a single machine?"

Why, yes. That's absolutely correct. If reliability and high availability is a critical factor, then you got to do
what you got to do. But that's a topic for another day.