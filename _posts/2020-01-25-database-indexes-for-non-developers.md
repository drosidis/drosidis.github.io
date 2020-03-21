---
layout: post
title:  'Database indexes for the non-developers'
image: '/assets/blog-images/database-index.jpg'
excerpt: >
  Database indexes can offer spectacular performance improvements for search queries in a database system. They achieve this by storing sorted copies of the data. They are managed by the database management software, so the effort required to use them is often negligible.
---

> **TL;DR** <br/> {{ page.excerpt }}

“How can it be so fast”? The founder of the startup I had just started working for was both surprised and excited. The most important page of their web application, a few months on the making already, had been so painfully slow. And it was just getting slower as the user numbers increased. But suddenly, the page was really flying. “I have just added an index at the table” was my reply. Which of course led to the follow-up question “What is an index”?  It is often tough to explain technical issues to non-developers, but on this occasion I think I managed to come up with a decent analogy.

<img src="{{page.image}}">

## The phone book analogy
Imagine you were given a printed phone book. It includes one entry for every mobile phone in the United Kingdom. Let’s say a hundred million of them. And for every mobile phone number, we store the last name of the owner, their first name, their phone number, and the city. As most other phone books, ours is sorted by last name. A printout of every entry in the book would look like this:

| Position    | Last name | First name | Phone number  | City       |
|------------:|-----------|------------|---------------|------------|
|           1 | Aagus     | John       | 0791 2345 678 | Manchester |
|         ... | ...       | ...        | ...           | ...        |
|      23,567 | Davies    | Mia        | 0791 3333 111 | Durham     |
|         ... | ...       | ...        | ...           | ...        |
|  65,345,343 | Smith     | Adam       | 0791 9696 999 | Edinburgh  |
|  65,345,344 | Smith     | Amelia     | 0791 4444 555 | London     |
|  65,345,345 | Smith     | Ava        | 0791 1000 000 | Canterbury |
|         ... | ...       | ...        | ...           | ...        |
| 100,000,000 | Zuel      | Jack       | 0791 2000 000 | ...        |

## Table scan
Now assume you want to find the phone number of Adam Smith from Edinburgh. A slow way to find this information is to start at the first page of the book and read all the entries one-by-one until you reach the line that reads “Smith Adam”. Obviously it would take you a veeeery long time to do so. This algorithm is known as [full table scan](https://en.wikipedia.org/wiki/Full_table_scan).

## Binary search
A faster option is to open the book in the middle. Read a random surname. If that name is alphabetically before Smith you know that Smith’s name is at the second half of the book. Otherwise it is in the first half. With one check you have eliminated 50 million entries! Then repeat. Open the phone book at the middle of the second half, read a random name and check if it is before or after “Smith”. You have just eliminated another 25 million entries! With every search you eliminate half the entries. Repeat until you find the name you are looking for. This algorithm goes by the name [binary search](https://en.wikipedia.org/wiki/Binary_search_algorithm). And it turns out that by using it, the maximum number of checks you need to do to find a name in a catalog of a 100 million people is just 27.

One important thing to remember is that this efficient searching is only possible because two conditions are met:

1. The entries are sorted by *surname*.
2. You are searching by *surname*.

## Indexes: Searching for a phone number
Now assume you want to do the reverse search. You want to find who is the owner of a specific phone number, say 0791 9696 999. So, you open the phone book again to search for the owner of this number. Alas, there is no shortcut now, no fast algorithm. The **binary search** is not applicable because the book is not sorted by phone number. Your only option is to start reading the phone book until you find the phone number above. A slow **full table scan**.

Unless of course you had an index!! In our example, this would be a separate book, that contains the phone numbers *sorted* and the position number at the original book. Like this:

| Phone number  | Position    |
|---------------|------------:|
| 0791 1000 000 |  65,345,343 |
| ...           |         ... |
| 0791 2000 000 | 100,000,000 |
| ...           |         ... |
| 0791 2345 678 |           1 |
| ...           |         ... |
| 0791 3333 111 |       23567 |
| ...           |         ... |
| 0791 4444 555 |  65,345,343 |
| ...           |         ... |
| 0791 9696 999 |  65,345,343 |

Now to answer the same question, you can do a binary search on the phone-number-index book. It would take you maximum 27 searches to find the position of the entry you’re looking for in the original phonebook and another 27 searches at the original book to find the name of the owner.

When our original data is sorted by a specific field, we call that field a **primary index**. In this case the column *surname* is the primary index of our phonebook. The column *Phone number* has a **secondary index**. There is no limitation on how many secondary indexes you can use. We could add one for city too.

## Trade offs
By maintaining two phone books, one sorted by surname and the other sorted by phone number, you gain the power to find very quickly anyone by their surname *or* by their phone number. But you need to pay a price. First, you need more paper (memory in computer databases) to store the second table. And then, every time a person changes their phone number you need to change it twice, once for every book. Note that changing the number in the index also requires a re-sorting of the table.

## Summary
We have seen that an index is a sorted partial copy of your data. It can make specific types of searching very efficient. But at the same time it increases the space you need to store the data and it makes updating the data slower. So, depending on the situation, you need to make a decision what indexes to use. A good index could increase performance spectacularly.
