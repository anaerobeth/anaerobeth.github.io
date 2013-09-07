---
layout: post
title: "All the buzz about Fizzbuzz"
date: 2013-09-07 15:12
comments: true
categories:
---
### Do companies still use [Fizzbuzz](http://c2.com/cgi/wiki?FizzBuzzTest) to find programmers who can code?

The test may be [old news](http://imranontech.com/2007/01/24/using-fizzbuzz-to-find-developers-who-grok-coding/) but the answer still seem to be Yes, with some interesting observations: Global nerdy found that only [40% of the candidates](http://www.globalnerdy.com/2012/11/15/fizzbuzz-still-works/) he interviewed could write FizzBuzz, LosTechies believe it provides [an accurate window into coding skills](http://lostechies.com/jimmybogard/2013/01/29/fizzbuzz-is-dead-long-live-fizzbuzz/), while [some engineers think it is plain boring](http://rtigger.com/blog/2013/07/23/the-shortcomings-of-fizzbuzz).

StackExchange has suggestions on [what to do after you fail the test](http://programmers.stackexchange.com/questions/152745/learn-programming-backwards-or-so-i-failed-the-fizzbuzz-test-now-what) in an interview.
* [Project Euler](http://projecteuler.net/)
* [99 Prolog Puzzles](http://www.ic.unicamp.br/~meidanis/courses/mc336/2009s2/prolog/problemas/index.html)
* [TopCoder](http://www.topcoder.com/)
*[Google Code Jam](https://code.google.com/codejam)
Find [more programming exercises](http://programmers.stackexchange.com/questions/756/where-can-i-find-programming-puzzles-and-challenges) on StackExchange.

### FizzBuzz test:
Write a program that prints out the numbers from 1 through 100, but…
  For numbers that are multiples of 3, print “Fizz” instead of the number.
  For numbers that are multiples of 5, print “Buzz” instead of the number
  For numbers that are multiples of both 3 and 5, print “FizzBuzz” instead of the number.

### Shortest Fizzbuzz Scripts

Implemented in Python

    for i in range(1,101):print"FizzBuzz"[i*i%3*4:8--i**4%5]or i
    for i in range(1,101):print"Fizz"*(i%3<1)+"Buzz"*(i%5<1)or i
    for x in range(100): print x%3/2*'Fizz'+x%5/4*'Buzz' or x+1

    via  http://koichitamura.blogspot.com/2009/05/python-fizzbuzz.html
    and tested on Python v2.7.2


Implemented in Ruby

    (1..100).map{|n|puts"FizzBuzz#{n}"[n%3<1?0:n%5<1?4:8,n%15<1?8:4]}
    1.upto(100){|i|p"FizzBuzz#{i}"[i%3<1?0:i%5<1?4:8,i%15<1?8:4]}
    100.times{|i|p"FizzBuzz#{i}"[i%3<1?0:i%5<1?4:8,i%15<1?8:4]}

    via http://golf.shinh.org/p.rb?FizzBuzz and tested on Ruby v2.0.0


Implemented in Perl

    perl -le'print(($_%3?"":Fizz).($_%5?"":Buzz)or$_)for 1..100'
    perl -M5.01 -e 'say+(Fizz)[$_%3].(Buzz)[$_%5]||$_,for 1..100'

    via http://www.perlmonks.org/?node_id=602901 tested on v5.12.4

Implemented in PHP
    while(++$i<100)echo($i%15?$i%3?$i%5?$i:Buzz:Fizz:FizzBuzz)."\n";

    via http://jakespurlock.com/2012/11/php-fizzbuzz-test/ tested on PHP 5


### Statistics on Shortest FizzBuzz codes
http://golf.shinh.org/p.rb?FizzBuzz

Language  User  Size  Time  Date  Statistics
Ruby  ksk 50  0.0162  11/02/15 00:33:41 0B / 25B / 24B
Perl  shmem 48  0.0918  07/03/02 03:15:54 0B / 22B / 25B
Python  Defenestrator 56  0.1151  07/04/20 06:07:37 0B / 35B / 20B
Clojure youz  77  2.7364  11/06/01 17:38:52 0B / 47B / 24B
JavaScript  ozy4dm  56  0.0450  07/02/25 11:49:44 0B / 30B / 26B
AWK nn  57  0.0024  08/10/27 18:16:48 0B / 32B / 24B
Bash  daishi  41  0.0152  11/02/26 19:02:54 0B / ?B / ?B
Scala lyrical_logical 66  7.8083  11/07/12 02:19:22 0B / 36B / 29B
