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

<h4>TESTING THE PROGRAM</h4>
<p>To run the program, you are required to first compile it on your Linux terminal: </p>
<ul>
<li><em>$ ./hsh</em></li>
<li><em>($) $ /bin/ls</em></li>
<li><em>($) $ exit </em> # The interactive shell</li>
<li><em>echo "/bin/ls" | ./hsh</em> # The non-interactive shell.</li>
<li><em>($) $ cat test_ls_2</em></li>
<li><em>($) $ exit</em></li>
</ul>

<h2>Files Summary</h2>
<ol>
<li>
<h4>_atoi.c</h4>
<p>The functions under this file and their function.</p>
<ul>
<li>interactive: Returns true(1) if shell is in interactive mode.</li>
<li>is_delim: checks if character is delimiter. SYNTAX: int is_delim(char c, char *delim)*</li>
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
<h4>builtin.c</h4>
<p>The functions in this file: </p>
<ul>
<li>\_myexit: exits the shell</li>
<li>\_mycd: changes current working directory of the process</li>
<li>\_myhelp: shows the help prompt</li>
</ul>
<p>This file contains some of the builtin functions of the shell. It handles four of the commands.</p>
</li>

<li>
<h4>builtin1.c</h4>
<p>The functions used for this file: </p>
<ul>
<li>\_myhistory: displays history list, one command by line, and are indexed.</li>
<li>unset\_alias: sets alias to a string.</li>
<li>set\_alias: sets alias to a string.</li>
<li>print\_alias: prints alias string.</li>
<li>\_myalias: mimics alias shell function builtin.(<i>man alias</i>)</li>
</ul>

<p>This file handles the above shell commands. on the terminal they are applied as: <i>history, alias</li></p>
</li>

<li>
<h4>environ.c</h4>
<p>The following functions are found in the file, and their brief description: </p>
<ul>
<li>_myenv: prints current environment of the shell program.</li>
<li>_getenv: gets the value of the environ variable.</li>
<li>_mysetenv: used to initialize the new environment variable or modify existing one.</li>
<li>_myunseten: used to remove an environment variable.</li>
<li>populate_env_list - used to populate environment list.</li>
</ul>
<p>This shows the characteristics and special features of our current terminal program. Ensure to have compiled the program and run it to test this function for environment by: </p>
<ul>
<li><i>env</i> command on the running program to get its environment.</li>
</ul>
</li>

<li>
<h4>errors.c<h4>
<p>The following functions are found in the <i>errors.c</i> file: </p>
<ul>
<li>_eputs: prints an input string.</li>
<li>_eputchar: writes character 'c' to stderr.</li>
<li>_putfd: writes the character c to a given file descriptor. </li>
<li>_putsfd: prints an input string</li>
</ul>
<p>This parses errors from the terminal and prints the error message for any command run on the shell terminal.</p>
</li>

<li>
<h4>error1.c</h4>
<p>This file has functions that together with the _error.c_ file functions handle errors.</p>
<p>The following functions are found in the file: </p>
<ul>
<li>\_erratoi: converts a string to and integer. SYNTAX: <em>int _erratoi(char *s)</em> where 's' id the string to convert.</li>
<li>print\_error: prints error message. SYNTAX: void print\_error(info\_t \*info, char \*estr).
<ul>
<li>@info: the parameter & return info struct</li>
<li>@estr: string containing specified error.</li>
</ul></li>
<li>print\_d: prints a decimal number. SYNTAX: <em>int print\_d (int input, int fd);</em>
<ul>
<li>@input: the input.</li>
<li>@fd: the file descriptor to write to.</li>
</ul></li>
<li>convert\_number: a clone of itoa. Returns the converted string. SYNTAX: <em>char *convert_number(long int num, int base, int flags);</em>
<ul>
<li>@num: number</li>
<li>@base: base of number.</li>
<li>@flags: argument flags.</li>
</ul></li>
<li>remove\_comments: used to replace first instance of '#' to '\0'. SYNTAX: <em>void remove\_comments(char *buf)</em>
<ul>
<li>@buf: address the string to modify.</li>
</ul></li>
</ul>
</li>
<!--End of file 6 of my program-->

<li>
<h4>exits.c</h4>
<p>This file has functions that aide the user to exit the shell prompt of our running program.</p>
<p>The following functions are found in the <em>exits.c</em> file: </p>
<ul>
<li>\_strncpy: copies a string. Clone of strncpy function. SYNTAX: <em>char *_strncpy(char *dest, char *src, int n);</em>
<ul>
<li>@dest: the destination string to be copied to.</li>
<li>@src: the source string.</li>
<li>@n: the amount of characters to be copied.</li>
</ul></li>
<li>\_strncat: concatenates two strings. SYNTAX: <em>char *_strncat(char *dest, char *src, int n);</em>
<ul>
<li>@dest: Destination string to be copied to.</li>
<li>@src: Source string.</li>
<li>@n: number of bytes to copy.</li>
</ul></li>
<li>\_strchr: locates a character in a string. SYNTAX: <em>char *_strchr(char *s, char c);</em>
<ul>
<li>@s: the string to be parsed.</li>
<li>@c: character to look for.</li>
<li>Return: (s) a pointer to the memory area s.</li>
</ul></li>
</ul>
</li>

<li>
<h4>getLine.c</h4>
<p>This function reads input from the user. It clones the getline function.</p>
<p>The functions in this <em>getLine.c</em> file are: </p>
<ul>
<li>input\_buf: buffers chained commands.SYNTAX: <em>ssize_t input_buf(info_t *info, char **buf, size_t *len);</em>
<ul>
<li>@info: parameter struct</li>
<li>@buf: address of buffer.</li>
<li>@len: address of len var</li>
<li>Return: bytes read.</li>
</ul></li>
<li>get\_input: gets a line minus newline character. SYNTAX: <em>ssize_t get\_input(info_t *info);</em> Returns: read buf</li>
<li>read\_buf: reads a buffer. SYNTAX: <em>ssize_t read_buf(info_t *info, char *buf, size_t *i);</em>
<ul>
<li>@info: parameter struct</li>
<li>@buf: buffer</li>
<li>@i: size</li>
<li>Return: read buffer, r filedescriptor</li>
</ul></li>
<li>\_getline: gets the next line to input from STDIN. SYNTAX: <em>int \_getline(info\_t *info, char **ptr, size\_t *length);</em>
<ul>
<li>@info: Parameter Struct</li>
<li>@ptr: address of pointer to buffer, preallocated or NULL</li>
<li>@length: size of preallocated ptr buffer if not NULL</li>
<li>Return: s, length of string read from STDIN</li>
</ul>
<li>sigintHandler: blocks ctrl-C. SYNTAX: <em>void sigintHandler(__attribute__((unused))int sig_num</em>
<ul>
<li>sig\_num: The signal number.</li>
<li>Return: void</li>
</ul></li>
</ul>
</li>


</ol>
