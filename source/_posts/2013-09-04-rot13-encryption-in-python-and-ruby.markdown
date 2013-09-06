---
layout: post
title: "ROT13 encryption in Python and Ruby"
date: 2013-09-04 15:58
comments: true
categories:
---

A program to encrypt a message in ROT13 by shifting a letter through the alphabet (an exercise from Chapter 8 of Think Python by Allen Downey)

ASCII numbers
ord('a') => 97
ord('z') => 122
ord('A') = > 65
ord('Z') = > 90
chr(97) => 'a'
Key is the number of places the letters of the message should be moved during encryption

### Solution in Python
    def rotate_word(message, key):
        new_message = ''
        s = message.lower()
        for letter in s:
            new_ord = key + ord(letter)
            if new_ord > 122:
                new_ord = new_ord - 26
                new_letter = chr(new_ord)
            else:
                new_letter = chr(new_ord)

            new_message = new_message + new_letter
        return new_message.lower()

    words = ['abc', 'python', 'ruby', 'unladen swallow']

    print "*** Messages encrypted in ROT13 ***"
    for word in words:
        print "%s: %s" % (word, rotate_word(word, 13))

### Solution in Ruby
    def rotate_word(message, key)
      new_message = ''
      message.downcase!
      message_array = message.split('')
      message_array.each do |m|
        new_ord = key + m[0].ord
        if new_ord > 122
          new_ord = new_ord - 26
          new_letter = new_ord.chr
        else
          new_letter = new_ord.chr
        end
        new_message = new_message + new_letter
      end
      return new_message.downcase
    end

    words = ['abc', 'python', 'ruby', 'unladen swallow']

    puts "*** Messages encrypted in ROT13 ***"
    words.each do |word|
        puts "#{word}: #{rotate_word(word, 13)}"
    end

Outputs:
    *** Messages encrypted in ROT13 ***
    abc: nop
    python: clguba
    ruby: ehol
    unladen swallow: haynqra-fjnyybj
