## Introduction

[Object-Relational Mapping](https://en.wikipedia.org/wiki/Object-relational_mapping) (ORM) is a technique that lets you query and manipulate data from a database using an object-oriented paradigm. When talking about ORM, most people are referring to a _library_ that implements the Object-Relational Mapping technique, hence the phrase "an ORM".

An ORM library is a completely ordinary library written in your language of choice that encapsulates the code needed to manipulate the data, so you don't use SQL anymore; you interact directly with an object in the same language you're using.

For example, here is a completely imaginary case with a pseudo language:

You have a book class, you want to retrieve all the books of which the author is "Linus". Manually, you would do something like that:

```
book_list = new List();
sql = "SELECT book FROM library WHERE author = 'Linus'";
data = query(sql); // I over simplify ...
while (row = data.next())
{
     book = new Book();
     book.setAuthor(row.get('author');
     book_list.add(book);
}
```

With an ORM library, it would look like this:

```
book_list = BookTable.query(author="Linus");
```

The mechanical part is taken care of automatically via the ORM library.

## Pros and Cons

**Using ORM saves a lot of time because:**

- [DRY](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself): You write your data model in only one place, and it's easier to update, maintain, and reuse the code.
- A lot of stuff is done automatically, from database handling to [I18N](https://en.wikipedia.org/wiki/Internationalization_and_localization).
- It forces you to write [MVC](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller) code, which, in the end, makes your code a little cleaner.
- You don't have to write poorly-formed SQL (most Web programmers really suck at it, because SQL is treated like a "sub" language, when in reality it's a very powerful and complex one).
- Sanitizing; using prepared statements or transactions are as easy as calling a method.

**Using an ORM library is more flexible because:**

- It fits in your natural way of coding (it's your language!).
- It abstracts the DB system, so you can change it whenever you want.
- The model is weakly bound to the rest of the application, so you can change it or use it anywhere else.
- It lets you use OOP goodness like data inheritance without a headache.

**But ORM can be a pain:**

- You have to learn it, and ORM libraries are not lightweight tools;
- You have to set it up. Same problem.
- Performance is OK for usual queries, but a SQL master will always do better with his own SQL for big projects.
- It abstracts the DB. While it's OK if you know what's happening behind the scene, it's a trap for new programmers that can write very greedy statements, like a heavy hit in a `for` loop.

## How to learn about ORM?

Well, use one. Whichever ORM library you choose, they all use the same principles. There are a lot of ORM libraries around here:

- Java: [Hibernate](https://en.wikipedia.org/wiki/Hibernate_(Java)).
- PHP: [Propel](https://en.wikipedia.org/wiki/Propel_(PHP)) or [Doctrine](https://en.wikipedia.org/wiki/Doctrine_(PHP)) (I prefer the last one).
- Python: the Django ORM or [SQLAlchemy](https://en.wikipedia.org/wiki/SQLAlchemy) (My favorite ORM library ever).
- C#: [NHibernate](https://en.wikipedia.org/wiki/NHibernate) or [Entity Framework](https://en.wikipedia.org/wiki/Entity_Framework)

If you want to try an ORM library in Web programming, you'd be better off using an entire framework stack like:

- [Symfony](https://en.wikipedia.org/wiki/Symfony) (PHP, using Propel or Doctrine).
- [Django](https://en.wikipedia.org/wiki/Django_(web_framework)) (Python, using a internal ORM).

Do not try to write your own ORM, unless you are trying to learn something. This is a gigantic piece of work, and the old ones took a lot of time and work before they became reliable.