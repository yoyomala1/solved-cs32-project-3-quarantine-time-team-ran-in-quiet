Download Link: https://assignmentchef.com/product/solved-cs32-project-3-quarantine-time-team-ran-in-quiet
<br>
<span class="kksr-muted">Rate this product</span>




Project 3: Quarantine Time? Team Ran in Quiet.

2020 continues to do a number on our psyche. Even though we can go outside for a little bit and take walks around the neighborhood, go the Costco, or even hike and bike, most of our time has been spent indoors staring at the same walls and the same faces. I know, I’m making it sound grim. However, it’s allowed us some benefits, including learning a new skill, not having to dress up for school or work, and actually eating meals with family and roommates. It also has allowed us to have some game nights again. It could be Cranium, Apples to Apples, or even Cards Against Humanity.

There are also word games, like Scrabble, that require rearranging a combination of letters to make a word. This type of arrangement is generally referred to as an anagram, while it’s known as a permutation in mathematics. This assignment will give you some experience thinking about and writing recursive functions. Write a C++ program that searches for “anagrams” in a dictionary. An anagram is a word obtained by scrambling the letters of some string. For example, the word “pot” is an anagram of the string “otp.” A sample run of the program is given below. Your output does not have to be formatted exactly the same as that shown in the sample, but it should be in a similar style. You can use words.txt as your dictionary file and anagrams.cpp as an example of a main program.

Since the purpose of this assignment is to give you experience using recursion, you may not use any of C++’s iteration constructs (do, while, for, and goto) or any STL algorithms (if you have no idea what this means, you’re OK). In fact, similar to homework #2, you may only use the substr() and size()/length() functions in the string class. All repetition must be accomplished using recursion. This applies to every operation in the program, even file operations. Obviously, you would never write a program like this in industry but as an exercise it should be useful to gain experience with recursion.

Sample Runs

Here are two examples of how the program might work:

<pre>Please enter a string for an anagram: ratMatching word artMatching word ratMatching word tar</pre>

<pre>Please enter a string for an anagram:  regardlessNo matches found</pre>

Requirements

You must write these three functions with the exact same function signature (include case):

<pre>int createDict(istream &amp;dictfile, string dict[]);</pre>

Puts each string in dictfile into the array dict. Returns the number of words read into dict. This number should not be larger than MAXDICTWORDS since that is the size of the array.

<pre>int characterMixer(string word, const string dict[], int size,string results[]);</pre>

Puts all the possibilities of word which are found in dict into results. Returns the number of matched words found. This number should not be larger than MAXRESULTS since that is the size of the array. The size is the number of words inside the dict array.

void viewAnswers(const string results[], int size);Displays size number of strings from results. The results can be printed in

any order.

For words with double letters you may find that different permutations match the same word in the dictionary. For example, if you find all the permutations of the string kloo using the algorithm we’ve discussed you may find that the word look is found twice. The o’s in kloo take turns in front. Your program should ensure that matches are unique, in other words, the results array returned from the characterMixer function should have no duplicates. A nice way to test this, and your function in general, might be to use the assert facility from the standard library. If done properly the following code should run without a runtime error being generated.

<pre>      string exampleDict[] = {"kool", "moe", "dee"};</pre>

<pre>      int numResults = characterMixer("kloo", exampleDict, 3,results);</pre>

<pre>      assert(numResults == 1 &amp;&amp; results[0] == "kool");</pre>

Again, your solution must not use the keywords while, for, or goto or any STL algorithm functions. You must not use global variables or variables declared with the keyword static, and you must not modify the function parameter lists. You must use the integer constants MAXRESULTS and MAXDICTWORDS, as the declared sizes of your arrays, as in the anagrams.cpp example provided to you.

Helpful Tips

In this project you will also have to deal with one of the drawbacks of using recursive functions. Repeated recursive calls may exhaust the stack space (we will talk about stacks soon) that’s been allocated for your program. If you use the sample dictionary file

provided, you are almost guaranteed to have a default stack size that is not large enough. Here is how to change the stack size on different platforms:

Visual Studio

In the Property Pages dialog, in the left panel, select Configuration Properties / Linker / System. In the right panel, select Stack Reserve Size, and in the drop-down list to its right, type in a new stack size (8000000 is approximately 8MB). Click OK.

Xcode

Click on the Project Name, Select Build Settings at the top then scroll below to find the Linker subsection. Add -Wl,-stack_size,8000000 to the Other Linker Flags field.

Linux

Run the command ulimit -s 8000 before compiling your program.

While completing this assignment you may find it helpful to review file operations and using the substr function.