---
layout: post
title: "Palindrome checker in Python and Ruby"
date: 2013-09-02 09:18
comments: true
categories:
---

Write a function that takes a string argument and returns
True if it is a palindrome and False otherwise (an exercise from Chapter 6 of Think Python by Allen Downey).

### Solution in Python

    def first(word):
        return word[0]

    def last(word):
        return word[-1]

    def middle(word):
        return word[1:-1]

    def is_palindrome(word):
        if len(word) <=1:
            return True
        if first(word) != last(word):
            return False
        return is_palindrome(middle(word))

    words = ['cat', 'noon', 'radar', 'swallows', 'racecar']

    for word in words:
      print '%s: %s' % (word, is_palindrome(word))

### Solution in Ruby

    def first_letter(word)
      word[0]
    end

    def last_letter(word)
      word[-1]
    end

    def middle(word)
      word.byteslice(1..-2)
    end

    def is_palindrome?(word)
      if word.length <= 1
        return 'True'
      elsif first_letter(word) != last_letter(word)
        return 'False'
      else
        return is_palindrome?(middle(word))
      end
    end

    puts "Palindrome Detector"

    array = %w[cat noon radar swallows racecar]
    array.each do |word|
      puts "#{word}: #{is_palindrome?(word)}"
    end

Outputs:

    Palindrome Detector
    cat: False
    noon: True
    radar: True
    swallows: False
    racecar: True
