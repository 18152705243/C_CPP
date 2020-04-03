1.get the offset address of structure

​	①#define offset(type, member) ((unsigned int)&((type *)0)->member)

​	Error: case ... lose precision...

​	analyze:because the compiler with 64-bit,the define return a 4-bit int  type,so when compile the file,4-bit message will be lossed.mabey the c compiler return a warning and it will get a true 

result.
​	solution:

​	#define offset(type, member) ((size_t)&((type *)0)->member)

​	#define offset(type, member) ((unsigned long long)&((type *)0)->member)

​	
