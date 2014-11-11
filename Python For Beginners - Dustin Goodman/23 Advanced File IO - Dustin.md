Last week, we discussed [the basics of File I/O in Python][1]. In this review, you learned how to `open()`, `close()`, `read([bytes])` from, and `write(string)` to files. This week we�re going to learn a few more tricks built on these concepts as well as explore some tools that will assist in learning making these methods more efficient.

The `read` method was useful for obtaining information from files but was unhelpful when trying to read data from a file we were writing to or when we had already read the file. What would happen if we wanted to work on each line of a file individually using `read`? Well, you would have to save the input to a variable (let�s call it `data`) and perform a `split` operation on the newline character. This would give us a list of all the strings on each line that we would then have to iterate. You can see an example in the first code example in [PythonIO2.py][2]. Wouldn�t it be nice if we could just iterate each line quickly or just snag a single line of the file? Fortunately, we can!

The first method we can use is the `readline()` method that reads in each line of the file. The `readline` method reads a file until it reads the newline character, `\n`, at which point it returns an empty string. Example 2 in [PythonIO2.py][2] demonstrates how to read a file using this method. However, this is Python and that algorithm is just unacceptable so the developers made an even simpler and more efficient algorithm. You can just iterate the file object. Example 3 of [PythonIO2.py][2] demonstrates this method. This being said you can also read all the lines of a file into a list by either calling `list(f)` or `f.readlines()` where `f` is the file object. You can take your pick of your preferred method.

Now, if you recall from last week, we had to close and reopen a file to read from the beginning once we reached the end of the file. Well not anymore! File objects have a method called `seek(offset, [mode])` that allows us to move our file pointer to any position in the file we choose. The offset parameter is the number of bytes to move in the file. This is an integer so we can move forward with positive numbers except for moving past the end of the file or backwards with negative numbers except for going past the beginning of the file. The mode parameter tells us from where to start moving. There are three options: 0, 1 and 2. 0 tells `seek` to start from the beginning of the file and is the default mode. 1 tells `seek` to move from your current position in the file and 2 tells `seek` to start at the end of file. So if we wanted to read through our file twice or move to a specific position in our file, we could use seek in order to do said operation. Example 4 shows how to read the file twice. We�ll explore more advanced I/O features next week that use `seek` in detail. Another helpful tool when using `seek` is `tell` which returns your position in the file in bytes. Example 4 also demonstrates this method.

The last thing we�ll discuss this week is `with` blocks. In Python, it is good practice to use `with` blocks to work on files because it handles all the necessary close operations for you once the block exits and most error exceptions that occur. Example 5 in [PythonIO2.py][2] demonstrates how to use blocks. When using blocks, make sure all of your file related code exists in the correct indentation level or the scope of your file will be lost and you won�t be able to use this method correctly. 

Enjoy and next week we�ll discuss database file structures!


  [1]: http://www.codecademy.com/groups/python-fro-beginners/discussions/518873868f6395e068000ac4
  [2]: https://gist.github.com/sharocko/5564735