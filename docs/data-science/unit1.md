# introduction to R

- open source
- used as statistical software and data analysis tool
- comes with command line interface

## Importance

- well-developed,simple,effective -includes loop and recursive functions - input output facilities
- provides graphical interface
- flexible language-allows tool like c and c++
- has effective data handling and storage facility
- provides-extensive-coherent-integrated collection of tools for analysis
- includes `package system`-allows user to add their functionality
- used for statistical computing and design

## data types

6 datatype

- logical
- numeric
- integer
- complex
- character
- raw
  - values as raw bytes
  - charToRaw()
  - rawToChar()
- format: variable<- value

    ```r
    raw_variable <- charToRaw("Welcome to Programing)
    char_variable <- rawToChar(raw_variable)

    ```

```r
complex_value <- 3+2i
print(class(complex_value)) // "complex"
```

## Operators in R

- Arithmetic operators
- Assignment operators
- Comparison operators(==,!=,>,<,>=,<=)
- Login operators (&,&&,|,||,!)
- Miscellaneous operators

![arithmetic operators](2022-10-18-09-55-42.png)
![Assignment operators](2022-10-18-09-58-18.png)
![Miscellaneous operators](2022-10-18-10-00-53.png)

## Loops

- for loops
- while loops
- repeat loops
  - it has no condition to terminate loop
  - place condition within loop body and declare break

![for loop](2022-10-18-13-14-25.png)
![while loop](2022-10-18-13-14-58.png)
![repeat loop](2022-10-18-13-17-49.png)

## function in R

```r
my_function<- function(){
  statement
}
my_fun<- function(name){
  paste(name,"lol")
}

```

## R script

- file with extension .R
