# Receipt Formatter
## Overview

In this assignment, you will write a program that creates a formatted store receipt.

Your program will ask the user how many different items are being purchased. Then it will use a loop to ask for each item’s information, print that item on the receipt, and keep a running subtotal.

This assignment gives you practice with:

- `Scanner` objects
- `String` object methods
- methods with parameters and return values
- `for` loops
- cumulative totals
- formatted output with `printf`

---

## Program Requirements

1. Ask the user how many different items are on the receipt.
2. Use a loop to process that many items.
3. For each item, ask for:
   - item name
   - item category
   - quantity
   - price per item
4. Print one receipt line for each item.
5. Print the receipt subtotal, tax, and total **after** all items have been entered.

Use this tax rate:

```java
public static final double TAX_RATE = 0.085;
```


---

## Required Concepts

Your solution should use:

- `Scanner`
- a loop
- `String` object methods
- methods with parameters
- at least one method with a return value
- a cumulative variable for the receipt subtotal
- `printf` for money formatting

---

## Item Code Requirement

For each item, create an item code using:

- the first 3 letters of the item name
- the first 3 letters of the category
- the quantity

The item code should be uppercase.

For example:

```text
Item name: mechanical pencil
Category: school supplies
Quantity: 3
```

The item code should be:

```text
MECSCH3
```

You may assume the item name and category will each have at least 3 characters.

---

## Output Format

Your receipt should follow this general format:

```text
========== RECEIPT ==========
ITEMCODE  ITEM NAME  xQUANTITY  $PRICE_EACH  $ITEM_SUBTOTAL
ITEMCODE  ITEM NAME  xQUANTITY  $PRICE_EACH  $ITEM_SUBTOTAL

Subtotal: $SUBTOTAL
Tax: $TAX
Total: $TOTAL
=============================
```

You do not need to make the columns line up perfectly, but the receipt should be easy to read.

---

## Sample Run

```text
How many items? 2

Enter item name: mechanical pencil
Enter item category: school supplies
Enter quantity: 3
Enter price per item: 1.49

Enter item name: notebook
Enter item category: school supplies
Enter quantity: 2
Enter price per item: 4.50

========== RECEIPT ==========
MECSCH3  MECHANICAL PENCIL  x3  $1.49  $4.47
NOTSCH2  NOTEBOOK  x2  $4.50  $9.00

Subtotal: $13.47
Tax: $1.14
Total: $14.61
=============================
```

---

##  Method Organization

You may choose your own method names, but your program should be organized into helper methods.

A short `main` might look as simple this:

```java
public static void main(String[] args) {
    Scanner input = new Scanner(System.in);

    runReceiptProgram(input);

    input.close();
}
```

Or, `main` may coordinate at a lower level like this:

``` java
public static void main(String[] args) {
    Scanner input = new Scanner(System.in);

    int numberOfItems = getNumberOfItems(input);

    printReceiptHeader();

    double subtotal = processItems(input, numberOfItems);

    double tax = calculateTax(subtotal);
    double total = calculateTotal(subtotal, tax);

    printReceiptTotals(subtotal, tax, total);

    input.close();
}

```

Possible helper methods:

```java
getNumberOfItems
getItemName
getCategory
getQuantity
getPricePerItem
calculateSubtotal
calculateTax
calculateTotal
formatItemName
createItemCode
printItemLine
printReceiptTotals
```

---

## Submission

Submit a link to your Feedback PR to the Canvas assignment.
