#include <stdio.h>
//#define METHOD
//#define METHOD_1
#define METHOD_2
// functions declaration
int  strindex(char str[], char pattern[]);
int  get_line(FILE * file, char s[], int lim);
void print_getline(void);
void print_strindex(char pattern[]);
int  str_len(char ptr[]);

// main function to start the program from
int main()
{
//	printf("%d\n", '\n');
//	print_getline();
//	print_strindex("a");
	FILE * file = fopen("text.txt", "r");
	char line[1000];
	char pattern[] = "mohammed";

	while(get_line(file, line, 100) != -1)
	{
		if(strindex(line, pattern) != -1)
		{
			printf("%s\n", line);
		}
	}
	return 0;
}




/*
 *
 * GOTO THE FUNCTION BELOW >>>>>>>>>>>>>>>>>>>>>>|||||||||||||||
 *
 *
 * */
void print_getline(void)
{
	//#if 0
	char str[1000];
		int num_scanned = 0;
		FILE * file = fopen("text.txt", "r");
		num_scanned = get_line(file, str, 100);
	#ifdef METHOD
		while(num_scanned != 0)
	#else
			while( num_scanned != -1 )
	#endif /* METHOD */
			{
				printf("%s\n", str);
				printf("Number of chars = %d\n", num_scanned);
				num_scanned = get_line(file, str, 100);

			}
	//#endif
}

/*
 *
 *
 *
 *
 * */
#if 0
void print_pattern(void)
{
	//#if 0
	char str[1000];
		int num_scanned = 0;
		FILE * file = fopen("text.txt", "r");
		num_scanned = get_line(file, str, 100);
	#ifdef METHOD
		while(num_scanned != 0)
	#else
			while( num_scanned != -1 )
	#endif /* METHOD */
			{
				printf("%s\n", str);
				printf("Number of chars = %d\n", num_scanned);
				num_scanned = get_line(file, str, 100);
			}
	//#endif
}

#endif



/*
 *
 * GOTO THE FUNCTION BELOW >>>>>>>>>>>>>>>>>>>>>>|||||||||||||||
 *
 *
 * */
void print_strindex(char pattern[])
{
	char str[] = "Mohammed Ali Ba4a Alkabeer";
	int x = strindex(str, pattern);
	printf("%d", x);
}



/*Function that print the index of where the pattern is.

GOTO THE FUNCTION BELOW >>>>>>>>>>>>>>>>>>>>>>|||||||||||||||

*/
int strindex(char str[], char pattern[])
{
	int i =0 ;
	int j =0 ;
	while(str[i] != '\0' )
	{
		while(pattern[j] == str[i] && pattern[j] != '\0' &&str[i] != '\0')
		{
//			printf("%c", pattern[j]);
//			printf("The word in the index = %d\n", i);
			i++;
			j++;
		}
		if ( j == str_len(pattern) )
		{
		return i - str_len(pattern);
		}
		i++;
	}
	return -1 ;
}

// get the length of any string
int str_len(char ptr[])
{
	int i = 0;
	while (ptr[i] != '\0')
	{
		++i;
	}
	return i;
}

/* Function that get line and print it on the console
GOTO THE FUNCTION BELOW >>>>>>>>>>>>>>>>>>>>>>|||||||||||||||

*/
int get_line(FILE * file, char s[], int lim)
{

	char c = getc(file);
	int i = 0;
	while(c != EOF && c != '\n')
	{
		s[i] = c;
		// Update
		// 1. Character (get next character)
		c = getc(file);
		// 2. index i
		i++;
	}
	s[i] = 0; // s[i] = '\0'; // Null character, indicates the end of the string
/*
 * Methods for printing the empty lines
 */
	/*------------ 1. return 1 if it's an empty line ------------*/
#ifdef METHOD_1
	if( c == '\n' && i==0 ) // Empty line
	{
		i = 1;
	}
#endif /* METHOD_1 */
#ifdef METHOD_2
	/*------------ 2. return -1 if it's the EOF ------------*/
	// issue : EOF at the end of non-empty line i=-1 (wrong)
	// Fix : EOF is returned by getc() even after an error in reading, meaning i==0 this will fix the problem
	// If c == EOF and the line is empty
	if(c == EOF && i==0)
	{
		i = -1;
	}
#endif /* METHOD_2 */
	return i;
}
