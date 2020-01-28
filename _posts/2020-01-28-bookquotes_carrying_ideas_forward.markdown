---
layout: post
title:      "BookQuotes: Carrying Ideas Forward"
date:       2020-01-28 19:16:14 +0000
permalink:  bookquotes_carrying_ideas_forward
---


Why I built it: 

For my Javascript project, I created an application entitled BookQuotes: Carrying Ideas Forward. The idea for this application was born out of a regular practice of mine which is writing down powerful excerpts from books and other media I consume. The goal of the application was to provide users with an interface to hold on to and be able to revisit interesting and powerful quotes from books they have read. 

In the current version of the application, a user has the ability to add books to their list, including the title and author. The user has the choice of including a quote from that book right from the start or not, as well as continuing to add more quotes to books as needed. They can also update the title and author of the books.  

In the future, when a user saves a book, the user will be given the option to attach tags to each quote and filter by multiple tags. This way, a user can have easy access to quotes by a single or multiple categories. For example if a user filtered by tags "power", "optimism", or "history", the user might come across:

"To be hopeful in bad times is not just foolishly romantic. It is based on the fact that human history is a history not only of cruelty, but also of compassion, sacrifice, courage, kindness. What we choose to emphasize in this complex history will determine our lives. If we see only the worst, it destroys our capacity to do something. If we remember these times and places (and here are so many) this gives us the energy to act.” Howard Zinn, You Can’t be Neutral on a Moving Train 

Ultimately, I would like for the program to include the ability to offer a drop down list for what kind of media the quote was derived from and offer a form based on the item selected. This way, the user can record noteworthy from sources beyond books, including academic journals, blog posts, court decisions, speeches, etc.

What I learned: 

This application with a raisl API backend and a javascript frontend, more than previous projects forced me to consider hone my skills in organizing information through classes and separate functions. The program utilizes a class called booksAdapter which is strictly used to communicate with the backend. While conceptualizing this class, I began thinking of it as a warehouse of machines for hire. I set up several fetch requests ready to be called on to get, modify or delete information from the database. 

The App class where most of my code lives I envisioned as the factory that borrows the machines to actually build the things that become the finished product.  In the factory, using the borrowed machines to produce the information, the information is collected and told how to be sorted and made presentable. 

As the application grows, I see the need for more specialized warehouses to hold specific machines to talk to the backend, as well as more specialized factories. Finally, investments should also be made for a CSS polishing station of the final produce. For the time being, however, the current framework works well for this small but expanding book and quote business. 

