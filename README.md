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

<li>
<h4>getenv.c</h4>
<p>The <em>getenv.c</em> file contains the following functions that help configure the current working environment for our program: </p>
<ul>
<li>get\_environ: returns the sring array copy of our environment. SYNTAX: <em>char **get_environ(info_t *info);</em>
<ul>
<li>@info: Parameter struct</li>
<li>Return: Always 0</li>
</ul></li>
<li>\_unsetenv: Remove the environment variable. SYNTAX: <em>int _unsetenv(info_t *info, char *var);</em>
<ul>
<li>@info: Parameter structure, maintains constant function prototype</li>
<li>@var: the string variable environment property.</li>
<li>ReturnL 1 0n delete, 0 if otherwise</li>
</ul></li>
<li>\_setenv: initialize new environment variable, modify existing one. SYNTAX: <em>int _setenv(info_t *info, char *var, char *value);</em>
<ul>
<li>@info: Maintains constant prototype for functions.</li>
<li>@var: the string environment variable property.</li>
<li>@value: the string environment value.</li>
<li>Return: Always 0</li>
</ul></li>
</ul>
</li>

<li>
<h4>getinfo.c<h4>
<p>The following functions and their description are found in our <em>getinfo.c</em> file: </p>
<ul>
<li>clear_info: initializes info_t struct. SYNTAX: <em>void clear_info(info_t *info);</em>
<p>This function initializes arg, argv, and path to NULL while argc is initialized to 0</p></li>
<li>set_info: initializes info_t struct. SYNTAX: <em>void set_info(info_t *info, char **av);</em></li>
<li>free_info: frees info_t struct fields. SYNTAX: <em>void free_info(info_t *info, int all)</em>
<ul>
<li>@info: struct address</li>
<li>@all: true if freeing all fields.</li>
</ul>
<p>The info_t struct is initialized, set and modified and memory freed to prevent memory leaks.</p>
</ul>
</li>

<li>
<h4>history.c<h4>
<p>This program handles history of commands that have been run on the current child process of the shell program.</p>
<p>The program contains the following functions: </p>
<ul>
<li>get_history_file: gets the history file. SYNTAX: <em>char *get_history_file(info_t *info);</em>
<ul>
<li>Return: allocated string containing history file.</li>
</ul></li>
<li>write_history: creates a file or appends to an existing one. SYNTAX: <em>int write_history(info_t *info);</em>
<p>The file created by the filedescriptor has read and write permissions for the owner and read only permission for group and global users.</p></li>
<li>read_history: reads history from file. SYNTAX: <em>int read_history(info_t *info);</em>
<p>Returns history count on success.</p></li>
<li>build_history_list: adds entry to history linked list. SYNTAX: <em>int build_history_list(info_t *info, char *buf, int linecount);</em>
<ul>
<li>@info: structure containing potential arguments. Maintains constant function prototype.</li>
<li>@buf: buffer</li>
<li>@linecount: the history linecount, histcount</li>
<li>Return: Always 0</li>
</ul></li>
<li>renumber_history: renumbers the history linked listafter changes. SYNTAX: <em>int renumber_history(info_t *info)</em> Returns the new histcount</li>
</ul>
</li>

<li>
<h4>lists.c</h4>
<p>This program handles data structures. Creating lists to be utilized in various parts of the program, including the history.c file.</p>
<p>The functions in this file are included below for understanding: </p>
<ul>
<li>add\_node: adds a node to the start of a list. SYNTAX: <em>list_t *add_node(list_t **head, const char *str, int num);</em>
<ul>
<li>@head: address of pointer to head node.</li>
<li>@str: str field node.</li>
<li>@num: node index used by history.</li>
<li>Return: size of list</li>
</ul></li>
<li>add\_node\_end: adds a node to the end of the list. SYNTAX: <em>list_t *add_node_end(list_t **head, const char *str, int num);</em>
<ul>
<li>@head: address to pointer to head node.</li>
<li>@str: str field of node</li>
<li>@num: node index used by history</li>
<li>Return: size of list.</li>
</ul></li>
<li>print\_list\_str: prints only the str element of a list\_t linked list. SYNTAX: <em>size_t print_list_str(const list_t *h);</em>
<ul>
<li>@h: pointer to first node.</li>
<li>Return: size of list.</li>
</ul></li>
<li>delete\_node\_at\_index: deletes node at given index. SYNTAX: <em>int delete_node_at_index(list_t **head, unsigned int index);</em>
<ul>
<li>@head: address of pointer to first node.</li>
<li>@index: index of node to delete.</li>
<li>Return: 1 on success, 0 on failure.</li>
</ul></li>
<li>free\_list: frees all nodes of a list. SYNTAX: <em>void free_list(list_t **head_ptr);</em>
<ul>
<li>@head\_ptr: address to pointer of head node.</li>
<li>Return: Nothing</li>
</ul></li>
</ul>
</li>

<li>
<h4>lists1.h</h4>
<p>The following functions r=are used in the file: </p>
<ul>
<li>list\_len: determines length of linked list. SYNTAX: <em>size_t list_len(const list_t *h);</em>
<ul>
<li>@h: pointer to first node.</li>
<li>Return: size of list.</li>
</ul></li>
<li>list\_to\_strings: returns an array of strings to the list-\>str. SYNTAX: <em>char **list_to_strings(list_t *head);</em>
<ul>
<li>@head: pointer to first node</li>
<li>Return: array of strings</li>
</ul></li>
<li>print\_list: prints all elements of a list\_t linked list. SYNTAX: <em>size_t print_list(const list_t *h);</em>
<ul>
<li>Return: length of list</li>
</ul></li>
<li>node\_start\_with: returns node whose string starts with prefix. SYNTAX: <em>list_t *node_start_with(list_t *node, char *prefix, char c);</em>
<ul>
<li>@node: pointer to list head.</li>
<li>@prefix: string to match</li>
<li>@c: the next character after the prefix to match.</li>
<li>Return: match node or null</li>
</ul></li>
<li>get\_node\_index: gets index of node. SYNTAX: <em>ssize_t get_node_index(list_t *head, list_t *node);</em>
<ul>
<li>@head: pointer to list head.</li>
<li>@node: pointer to the node.</li>
<li>Return: index of node or -1</li>
</ul></li>
</ul>
</li>

<li>
<h4>parser.c</h4>
<p>This file had functions which help the terminal to parse data.</p>
<p>The functions under this file include: </p>
<ul>
<li>is\_cmd: determines if a file is an executable command. SYNTAX: <em>int is_cmd(info_t *info, char *path);</em>
<ul>
<li>@info: the info struct</li>
<li>@path: path to the file.</li>
<li>Return: 1 if true, 0 if otherwise</li>
</ul></li>
<li>dup\_chars: duplicates characters. SYNTAX: <em>char *dup_chars(char *pathstr, int start, int stop);</em>
<ul>
<li>@pathstr: the PATH string</li>
<li>@start: starting index</li>
<li>@stop: stopping index</li>
<li>Return: pointer to a new buffer</li>
</ul></li>
<li>find\_path: finds this cmd in the PATH string. SYNTAX: <em>char *find_path(info_t *info, char *pathstr, char *cmd);</em>
<ul>
<li>@info: the info struct</li>
<li>@pathstr: the PATH string</li>
<li>@cmd: command to find</li>
<li>Return: full path of cmd if found or NULL</li>
</ul></li>
</ul>
</li>

<li>
<h4>realloc.c</h4>
<p>The memory is reallocated through calling the <em>_realloc</em> function. Among othe functions in this file are: </p>
<ul>
<li>@\_memset: fills memory with a constant byte. SYNTAX: <em>char *_memset(char *s, char b, unsigned int n);</em>
<ul>
<li>@s: the pointer to the memory area</li>
<li>@b: the byte to fill *s* with.</li>
<li>@n: the amount of bytes to be filled</li>
<li>Return: (s) a pointer to the memory area s</li>
</ul></li>
<li>ffree: frees a string of strings. SYNTAX: <em>void ffree(char **pp);</em>
<ul>
<li>@pp: string of strings</li>
<li>Return: Nothing</li>
</ul></li>
<li>\_realloc: reallocates a block of memory. SYNTAX: <em>void *_realloc(void *ptr, unsigned int old_size, unsigned int new_size);</em>
<ul>
<li>@ptr: pointer to previous allocated block of memory</li>
<li>@old\_size: byte size of previous block</li>
<li>@new\_size: byte size of new block</li>
<li>Return: Pointer to the new block of memory allocated</li>
</ul></li>
</ul> 
</li>

<li>
<h4>shell_loop.c</h4>

</li>

</ol>
