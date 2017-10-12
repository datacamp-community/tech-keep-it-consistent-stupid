[If Hemingway Wrote JavaScript](https://www.amazon.com/Hemingway-Wrote-JavaScript-Angus-Croll/dp/1593275854) I bet he would keep it consistent for the whole codebase. When reading a book, you do not think about style inconsistencies as books are written in one manner. It makes them easy to read and understand. You don't have to focus on looking for punctuation marks, you know when new sentences start, you know that commas split a sentence into logical parts.

What if that wouldn't be the case? How about reading something like:

```
"cYBERSPACE - A Cconsensual Hallucination. experienced Daily by Billions,
of legitimate operators - in eVERY nation
- by children being, taught, mATHEMATICAL concepts - a graphic representation,
of data abstracted, from banks of every cOMPUTER in the human system
. unthinkable complexity. lines of, light ranged in the nonspace of the mind
, cLUSTERS and cONSTELLATIONS of data like city lights, receding..."
```

A bit hard isn't it? You still understand everything but it takes some effort to map this text into grammar rules to which we are used to.

And what about this one:

```
"Cyberspace.
A consensual hallucination experienced daily by billions of legitimate operators,
in every nation, by children being taught mathematical concepts...
A graphic representation of data abstracted from banks of every computer in the human system.
Unthinkable complexity.
Lines of light ranged in the nonspace of the mind, clusters and constellations of data. Like city lights, receding..."
```

I bet it is much easier to read now.

I believe reading a good codebase is similar to reading a well written book. If the whole codebase is written in the same style, it is much easier to understand abstractions without switching contexts between different coding styles. Therefore, we should follow a rule to **K**eep **I**t **C**onsistent **S**tupid! Hence **KICS** (the resemblance to [KISS](https://en.wikipedia.org/wiki/KISS_principle) intended).

Codebase can have as many coding styles, as there are developers in a team. That is why it is important to agree on some rules as we do read code much more often than we write it.

When writing new code, I often ask myself simple questions like:
1. Even if I am used to particular coding style, would it be applicable in the current file, would it make it easy to read?
1. Even if I am not a fan of a particular coding style, would it make sense to force my approach here?
1. What have we used in other files?

Of course, we shouldn't copy-paste code and duplicate badly written blocks: it is a developer's responsibility to detect things like that and refactor it in two places if needed.

Let's see a simple Ruby example:

```ruby
def check_alive?
  return false if zombie?
  true
end

def check_zombie?
  zombie? ? true : false
end
```

and now a consistent one:

```ruby
def check_alive?
  return false if zombie?
  true
end

def check_zombie?
  return true if zombie?
  false
end
```

another approach:

```ruby
def check_alive?
  alive? ? true : false
end

def check_zombie?
  zombie? ? true : false
end
```

It does not really matter to which one we agree on. It is important to keep it consistent not only in context of one file but also in context of the whole codebase.
As in the book analogy - you wouldn't like to have text consistent only in context of single pages and read different styles when you go to the next one.

Good design is the best indicator of your identity and skills as a developer, coding style is next in line.
Same as a great author is a great story teller and then he can be a great writer.

KICS and let everyone enjoy reading your code.
