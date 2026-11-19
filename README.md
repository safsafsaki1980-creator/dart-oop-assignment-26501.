# Kigali Bus Card – Dart OOP Assignment

## Student Information

- **Name:** Mustafa Eliass Abdulhalim Adlan
- **Student ID:** 26501
- **Course:** Dart Object-Oriented Programming

## Personal Assignment Values

My personal values are calculated using my student ID (26501).

- D = 01 (last two digits)
- L = 1 (last digit)
- Starting balance = 1000 + (D × 10) = **1010 RWF**
- Bus fare = 200 + D = **201 RWF**
- Student discount = 10 + L = **11%**

---

## Part 1: BusCard Class

The `BusCard` class represents a bus card. It stores the owner's name and the card balance.

The class includes:
- A constructor to initialize the owner and balance.
- Getters to read the owner and balance.
- A setter to update the owner's name.
- A `showInfo()` method to display card information.
- A `topUp()` method to add money to the card.
- A `pay()` method to pay the bus fare.

### Why is there no setter for balance?

There is no direct setter for the balance because the balance should only be changed through controlled methods such as `topUp()` and `pay()`. This prevents users from setting an invalid balance directly and helps protect the card's data.

### Program Output

```text
ERROR!
Error: name too short
Owner: Mustafa Eliass Abdulhalim Adlan | Balance: 1010 RWF
Owner: Mustafa Eliass Abdulhalim Adlan | Balance: 1010 RWF
ERROR!
Error: top-up must be 500 to 50000 RWF
Topped up 2000 RWF
Paid 201 RWF
Paid 201 RWF
Owner: Mustafa Eliass Abdulhalim Adlan | Balance: 2608 RWF
Student discount: 22 RWF
Paid 179 RWF
Owner: Mustafa Eliass Abdulhalim Adlan | Balance: 831 RWF
Student card: 11% off
```

The `ERROR!` lines are displayed by the online execution environment. The program's own error messages are shown immediately below them.

---

## Part 2: StudentCard Class

The `StudentCard` class extends the `BusCard` class using inheritance.

It adds a discount field and overrides the `showInfo()` and `pay()` methods.

The `super` keyword is used to call methods and the constructor of the parent class.

### What does `~/` do?

The `~/` operator performs integer division. It divides two numbers and returns the whole-number result without the decimal part.

For example:

- `237 * 17 / 100` gives `40.29`.
- `237 * 17 ~/ 100` gives `40`.

In this assignment, `~/` is used to calculate the discount as a whole number.

---

## Part 3: Main Program

The main program tests the functionality of both `BusCard` and `StudentCard`.

The tests include:

1. Creating a bus card with my full name and starting balance.
2. Testing the owner setter with an invalid short name.
3. Setting the correct owner name.
4. Testing an invalid top-up of 100 RWF.
5. Adding 2000 RWF to the card.
6. Paying the bus fare twice.
7. Displaying the final balance.
8. Creating a student card with an 11% discount.
9. Paying the bus fare using the student card.

### Balance Calculations

**Normal BusCard:**

1010 + 2000 - 201 - 201 = **2608 RWF**

**StudentCard:**

Discount = 201 × 11 ~/ 100 = **22 RWF**

Fare after discount = 201 - 22 = **179 RWF**

Final balance = 1010 - 179 = **831 RWF**

---

## Part 4: Bug Hunt

The original program contained five bugs. I corrected them and tested the program.

### Bugs and Fixes

| Bug | The line | Why it is wrong | My fix |
|---|---|---|---|
| 1 | `String _brand;` and `int _battery;` | These fields are not initialized, which causes errors with Dart null safety. | Initialized them with `''` and `0`. |
| 2 | `SmartPhone(String brand, int battery, String system) {` | The parent constructor is not called, so the required parent fields are not initialized. | Added `: super(brand, battery)`. |
| 3 | `@override void restart()` in `SmartPhone` | The parent class does not have a `restart()` method to override. | Added a `restart()` method to the `Phone` class. |
| 4 | `p.battery = 100;` | The battery getter has no setter, so the battery cannot be updated. | Added a setter that accepts values from 0 to 100. |
| 5 | `print(p.battery());` | `battery` is a getter, not a method, so it must not be called with parentheses. | Changed it to `print(p.battery);`. |

### Line That Looks Wrong but Is Correct

`Phone p = new Phone('Tecno', 50);`

This is valid Dart syntax. The `new` keyword is optional in Dart, but it is still allowed.

### Fixed Program Output

```text
100
```

The program successfully updates the battery value to 100 and prints it.

---

## Part 5: Predict the Output

### My Prediction

Before running the program, I predicted that the output would be:

```text
1
5
```

### Explanation

For the first object, `a` starts with 0 items. Calling `a.add()` increases the number of items to 1.

The statement `a.items = -5` is rejected because the setter only accepts values greater than or equal to 0. Therefore, the first output is 1.

For the second object, `BigBag` overrides the `add()` method and calls `super.add()` twice. Each call adds two items.

After calling `b.add()` twice, the bag contains 4 items. Then one more item is added, making the final output 5.

### Actual Output

```text
1
5
```

### Was My Prediction Correct?

Yes. My prediction was correct because the actual output matched my predicted output.

---

## Conclusion

In this assignment, I learned how to use Dart classes, constructors, encapsulation, getters, setters, inheritance, method overriding, and the `super` keyword.

I also practiced identifying and fixing errors in Dart programs and predicting program output.

The assignment helped me understand the basic concepts of Object-Oriented Programming in Dart.
