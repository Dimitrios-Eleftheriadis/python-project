Program computeSales.py

Write a program computeSales.py in Python that reads files with product sales receipts, can do validation, and can then print
statistics requested. In more detail:
Input Files:
Each input file will be a text file of the format:
----------------------------------------
VAT number: YYYYYYYY
PRODUCT_NAME: QUANTITY UNIT_PRICE TOTAL_PRICE
...
PRODUCT_NAME: QUANTITY UNIT_PRICE TOTAL_PRICE
TOTAL: AMOUNT_WITH_TOTAL_RECEPTION
----------------------------------------
VAT number: BBBBBBBBBBB
PRODUCT_NAME: QUANTITY UNIT_PRICE TOTAL_PRICE
...
PRODUCT_NAME: QUANTITY UNIT_PRICE TOTAL_PRICE
TOTAL: AMOUNT_WITH_TOTAL_RECEPTION
----------------------------------------
An example of a receipt is the following:
----------------------------------------
VAT number: 0123456789
HORIATIKI: 3 7.00 21.00
TZATZIKI: 1 3.50 3.50
VARIETY: 2 14.20 28.40
TOTAL: 52.90
----------------------------------------
1) Each file contains 1 or more receipts (but at least 1)
2) Each receipt starts and ends with lines containing only the character '-'.
3) Receipts are separated from each other by lines containing only the character '-'.
4) The first line of each receipt contains the company's VAT number (10-digit number).
5) The last line of each receipt contains the total purchases for that receipt.
6) In one file there can be receipts of different companies (VAT numbers).
7) Each receipt includes the sale of multiple products (1 or more).
8) A product can appear on a receipt more than once. For example, in the receipt
for example, the product "HORIATIKI" may appear again later in the same
receipt.
9) The number of spaces in the lines between the fields is variable and your program
must not make assumptions about the number of blank characters.
10) Any receipt containing an error should be omitted, but the rest
receipts in the file should be read and saved. There may be a lot of errors, such as not having the VAT number on the 1st line of the receipt,
there is an incorrect VAT number, not having all the fields in each product, not having
correctly calculated the total price of a product (the multiplication of quantity
* unit_value), the "TOTAL" line might not be present as the last line, the "TOTAL" might not be correct, etc.

PROGRAM FUNCTIONALITY
Your program should reprint the following user menu:
Give your preference: (1: read new input file, 2: print statistics for a specific product, 3: print
statistics for a specific AFM, 4: exit the program)

- If the user enters 1, then the file name should be prompted. If invalid is given
file, then we return to the main menu (Give your preference...).
- If the user enters 2, then the product name should be prompted and printed
the total sales amount of the product per VAT number. 1 line should be printed
for each VAT number (and only for those) in which there is at least one sale of it
product. VAT numbers should be displayed in ascending order. Each line will
contains 2 data only (without any text): the VAT number and the total amount
sales (space separated). If there has been no sale of the specific product
from any VAT number, nothing should be printed (not even an error message).
- If the user enters 3, then the VAT number must be requested and the sum will be printed
of sales per product for the specific VAT number. 1 line should be printed for
every product that has been sold by the specific VAT number. The products should
they appear in ascending alphabetical order. Each line will contain 2 numbers only
(without any text): the "PRODUCT_NAME" and the total amount (separated by
space). If there has been no sale of any product from the specific VAT number, it will not
nothing should be printed (no error message).
- If the user enters 4, then the program will be exited.
- If the user taps anything else, they should be prompted for login again

IMPORTANT NOTES:
1. Data from different files are combined. When we press option 1,
then the receipts of each company are added to those we had read from
previous files.
2. You should think about what data structures you will use to answer
as quickly as possible the queries in options 2 and 3 of the user menu. Importance
not only the correctness of the results, but also whether it was efficient
implementation. No one uses a program that is too slow. The check on
your program will be made using very large files that will contain hundreds of thousands
lines. You should have no memory problems and be able to answer them efficiently
these questions.
3. Input data and data in receipts are NOT case-sensitive. The product
"HORIATIKI" is the same as the "horiatiki" product. I suggest converting all the
products in capital letters.
4. Within the week you will be given a small file with few receipts, which no
contain errors as well as a file with user input. If the program
your doesn't even run on the specific simple and given user input for it
specific file, then a maximum of 20% of that assignment will be graded
(ie with a maximum grade of 20% of the 32% of the total grade of all projects).
5. To read Greek characters from the file, you need to open it properly,
declaring the encoding. Eg open(filename, read_write_flags, encoding=’utf-8’)