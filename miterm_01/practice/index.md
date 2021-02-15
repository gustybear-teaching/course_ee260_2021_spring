---
title: "Practice Midterm 01"
date: 2021-02-12
type: book
commentable: true

summary: "The practice exam for midterm 01, EE260, spring, 2021."

tags:
- teaching
- ee260
- midterms
---

**Multiple Choices Questions (8 pts)**

1) (2 pts) Which of the following statements is not true of a hardware description language (HDL) simulator?
 - a. Input values are determined automatically by the HDL simulator
 - b. A designer provides input values intended to test the system
 - c. Output values are determined automatically by the HDL simulator
 - d. An HDL's key purpose is to support simulation

2) (2 pts) Which of the following statements is true of Verilog?
 - a. Verilog is an HDL that originated in 1985 at a company called Gateway Design Automation
 - b. Verilog is an HDL that was first published in 1987 as an IEEE standard
 - c. Verilog was developed at the behest of the U.S. Dept. of Defense
 - d. Verilog's syntax is borrowed largely from Ada, an earlier DoD language for software programming

3) (2 pts) Which of the following is true of an assignment statement p = x & y & z?
 - a. The assignment operator must be <=
 - b. The assignment operator must be ==
 - c. An assignment statement assigns the right-side variable with the result of the left-side expression
 - d. An assignment statement assigns the left-side variable with the result of the right-side expression

4) (2 pts) Identify the example that represents the accurate conversion of a Boolean expression to Verilog.
 - a. x = a'bc' is converted to x = a & b & c
 - b. x = a + b + c’ is converted to x = a | b | c
 - c. x = (pq) (rs) + a is converted to x = (p & q) (r & s) + a
 - d. x = (pq) + (rs) + a’ is converted to x = (p & q) | (r & s) | ~a

**Short-Answer Questions (40 pts)**

1) (5 pts) Perform the following number-system conversions (show your work):
  - a. $129_{10} = ()_{2}$
  - b. $0011010_{2} = ()_{10}$
  - c. $0F100_{16} = ()_{2}$
  - d. $1001101101101_{2} = ()_{16}$

2) (5 pts) Draw the NAND(x,y) gate CMOS transistor circuit. Show the conduction path and output value when: 
  - a. x = 1 and y = 0
  - b. x = 1 and y = 1

3) (5 pts) Convert the following equation directly to gate-level circuits: F = a + bcd’ + a'e + f’

4) (5 pts) Expand F(w,y,z) = wy to 
  - a. sum-of-minterms form
  - b. product-of-maxterms form

5) (5 pts) A car has a fuel-level detector that outputs the current fuel-level as a 3-bit binary number, with 000 meaning empty and 111 meaning full. Create a circuit that illuminates a “low fuel” indicator light (by setting an output L to 1) when the fuel level drops below level 3.

6) (5 pts) Convert the function F shown in the truth table in Table below to an *product-of-sum* equation. Don’t minimize the equation.

{{< figure src="https://raw.githubusercontent.com/gustybear-teaching/course_ee260_2021_spring/main/miterm_01/practice/images/problem_6.png" width=150 >}}

7) (5 pts) Use the theorems of boolean algebra to simplify the following logic function: F = m·n·o + q’·p’·n’ + p·r·m + q’·o·m·p’ + m·r (hint, the result has three terms. Don't spend too much time on this one. If stuck, move on first)

8) (5 pts) Implement a 4-to-2 priority encoder using only NOR gates.
  - a. Derive the truth table.
  - b. Derive the sum-of-product expression.
  - c. Derive the product-of-sum expression.
  - d. Convert the product-of-sum circuit into NOR gate implementation.
