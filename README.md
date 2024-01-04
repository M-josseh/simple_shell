<h1>SIMPLE SHELL TEAM PROJECT</h1>
<h2><i>AUTHORS</i></h2>
<ul>
<li>Dan Njuguna, Software Engineering student Multimedia University and at ALX.</li>
<li>Joseph Mutinda, Software Engineer.</li>
</ul>
<h2>REQUIREMENTS</h2>
<ol>
<li>Allowed editors: vi, vim, emacs</li>
<li>All your files will be compiled on <b>Ubuntu 20.04 LTS</b> using <em>gcc</em>, using the options <em>-Wall -Werror -Wextra -pedantic -std=gnu89</em></li>
<li>All your files should end with a new line(<i>\n</i>)</li>
<li>A <b>README.md</b> file, at the root of the folder of the project is mandatory</li>
<li>Your code should use the <i>Betty style</i>.</li>
<li>Your shell should not have any memory leaks. (We used <b>Valgrind</b> to check for memory leaks.)</li>
<li>No more than 5 functions per file. To comply with the standard C rules hence ensure readability.</li>
<li>All your header files should be include guarded</li>
<li>Use system calls only when you need to</li>
<li>Write a README with the description of your project</li>
<li>You should have an <b>AUTHORS</b> file at the root of your repository, listing all individuals having contributed content to the repository.</li>
</ol>

<h4><b>COMPILATION</b></h4>
<p><i>gcc -Wall -Werror -Wextra -pedantic -std=gnu89 *.c -o hsh</i></p>
<ul>
<li>Debuggs the code: our code successfully compiles with no errors.</li>
<li>The program is written to standard C format.</li>
<li>All the functions compiled with no return errors.</li>
</ul>

<h4>Testing the Program</h4>
<p>To run the program, you are required to first compile it on your Linux terminal: </p>
<ul>
<li><i>$ ./hsh</i></li>
<li><i>($) $ /bin/ls</i></li>
<li><i>($) $ exit </i> The interactive shell</li>
<li><i>echo "/bin/ls" | ./hsh</i> The non-interactive shell.</li>
<li><i>($) $ cat test_ls_2</i></li>
<li><i>($) $ exit</i></li>
</ul>

<h2>Files Summary</h2>
<ol>
<li>
<h4>_atoi.c</h4>
<p><i>The functions under this file and their function.</i></p>
<ul>
<li>interactive: Returns true(1) if shell is in interactive mode.</li>
<li>is\_delim: checks if character is delimiter. <i>SYNTAX:</i>int is\_delim(char c, char *delim)*</li>
<li>\_isalpha: check for alphabetic character.</li>
<li>\_atoi: converts string to integer.
</ul>
<p>This file performs functions for the interactive shell to ensure it is interactive, and that the arguments to it are parsed in the integer formart.</p>
<p>The info\_t structure used is to create variables in the global scope that can be used in any file. The <i>info_t</i> opens the integer data <i>readfd</i> a filedescriptor to the shell into the function <i>interactive</i></p>
<p>The delimiter is looped over untile the condition where the character checked is equal to the delimeter to return true.</p>
<p>The character is then passed to the \_isalpha function to check whether it is an alphabet or not.</p>
<p>The strings are converted to integer using the <b>Parsing Algorithm</b>. Simple explanation:</p>
<ul>
<li>Iterates through the characters of  a string.</li>
<li>Converting each character into its numerical.</li>
<li>Values and combining the values to form the integer representation.</li>
<li>Handling negative signs and decimal points.</li>
</ul>
</li>

<li>
<h4></h4>
</li>

