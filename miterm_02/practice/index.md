---
title: "Practice Exam"
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

1) (2 pts) Which of the following statements is true of testbench?
 - a. A testbench consists of one main element named a module.
 - b. A testbench provides a sequence of input values to test a module.
 - c. A testbench is a module with inputs and outputs.
 - d. A testbench creates an instance of a module named with the extension
   ''#tb''.

> - b.

2) (2 pts) The testbench for the given Verilog code snippet generates the waveform shown in the figure. Which of the following statements holds true in this case?
 - a. y_tb is set to 1 at 30 ns.
 - b. y_tb after 30 ns retains a value of 0 until y_tb is assigned a new value.
 - c. b_tb is set to 1 at 50 ns.
 - d. b_tb after 30 ns retains a value of 0 until b_tb is assigned a new value.

```
`timescale 1 ns/ 1 ns
module SetTimer (a, b, y);
   input a, b; 
   output reg y;


   always @ (a, b) begin
      y = a & b;
   end
endmodule


module Testbench ();
   reg a_tb, b_tb;
   wire y_tb;
   SetTimer SetTimer_tb (a_tb, b_tb, y_tb);
 
   Initial begin
      a_tb = 0;
      b_tb = 0;
      #20 b_tb = 1;
      #10 a_tb = 1;
      b_tb = 0;
      #10 a_tb = 0;
      #10 a_tb = 1;
    end
endmodule
```
> - d.

3) (2 pts) Which of the following is true of an assignment statement p = x & y & z?
 - a. The assignment operator must be <=
 - b. The assignment operator must be ==
 - c. An assignment statement assigns the right-side variable with the result of the left-side expression
 - d. An assignment statement assigns the left-side variable with the result of the right-side expression

> - d.

4) (2 pts) Identify the example that represents the accurate conversion of a Boolean expression to Verilog.
 - a. x = a'bc' is converted to x = a & b & c
 - b. x = a + b + c’ is converted to x = a | b | c
 - c. x = (pq) (rs) + a is converted to x = (p & q) (r & s) + a
 - d. x = (pq) + (rs) + a’ is converted to x = (p & q) | (r & s) | ~a

> - d.

**Short-Answer Questions (40 pts)**

1) (5 pts) Perform the following number-system conversions (show your work):
  - a. $129_{10} = ()_{2}$
  - b. $0011010_{2} = ()_{10}$
  - c. $0F100_{16} = ()_{2}$
  - d. $1001101101101_{2} = ()_{16}$

>  - a. $129_{10} = (10000001)_{2}$
>  - b. $0011010_{2} = (26)_{10}$
>  - c. $0F100_{16} = (0000 1111 0001 0000 0000)_{2}$
>  - d. $1001101101101_{2} = (136D)_{16}$

2) (5 pts) Draw the NAND(x,y) gate CMOS transistor circuit. Show the conduction path and output value when: 
  - a. x = 1 and y = 0
  - b. x = 1 and y = 1

> {{< figure src="https://raw.githubusercontent.com/gustybear-teaching/course_ee260_2021_spring/main/miterm_01/practice/images/solution_3.jpg" width=250 >}}

3) (5 pts) Convert the following equation directly to gate-level circuits: F = a + bcd’ + a'e + f’

> {{< figure src="https://raw.githubusercontent.com/gustybear-teaching/course_ee260_2021_spring/main/miterm_01/practice/images/solution_4.png" width=250 >}}

4) (5 pts) Expand F(w,y,z) = wy to 
  - a. sum-of-minterms form
  - b. product-of-maxterms form

> a. F(w,y,z) = wyz' + wyz
> b. F(w,y,z) = (w + y + z)(w + y + z')(w + y' + z)(w + y' + z')(w' + y + z)(w' + y +z')

5) (5 pts) A car has a fuel-level detector that outputs the current fuel-level as a 3-bit binary number, with 000 meaning empty and 111 meaning full. Create a circuit that illuminates a “low fuel” indicator light (by setting an output L to 1) when the fuel level drops below level 3.

> Step 1: Capture the function (truth table)  
> {{< figure src="https://raw.githubusercontent.com/gustybear-teaching/course_ee260_2021_spring/main/miterm_01/practice/images/solution_5a.png" width=250 >}}
> Step 2A: Create equation (canonical form)  
> L = F2'F1'F0' + F2'F1'F0 + F2'F1F0'  
> Step 2B: Create circuit  
> {{< figure src="https://raw.githubusercontent.com/gustybear-teaching/course_ee260_2021_spring/main/miterm_01/practice/images/solution_5b.png" width=250 >}}

6) (5 pts) Convert the function F shown in the truth table in Table below to an *product-of-sum* equation. Don’t minimize the equation.

{{< figure src="https://raw.githubusercontent.com/gustybear-teaching/course_ee260_2021_spring/main/miterm_01/practice/images/problem_6.png" width=250 >}}

> F = (a + b + c)(a + b' + c)(a + b' + c')(a' + b + c)(a' + b + c')

7) (5 pts) Use the theorems of boolean algebra to simplify the following logic function: F = m·n·o + q’·p’·n’ + p·r·m + q’·o·m·p’ + m·r (hint, the result has three terms. Don't spend too much time on this one. If stuck, move on first)

> F = m·n·o + q’·p’·n’ + q’·o·m·p’ + m·r + p·r·m (rearrange)  
> F = m·n·o + q’·p’·n’ + q’·o·m·p’ + m·r (drop p·r·m)  
> F = n·(m·o) + (q’·p’)·n’ + (q’·p’)·(o·m) + m·r (associative)  
> F = n·(m·o) + (q’·p’)·n’ + m·r (consensus, a·b + a’·c + b·c = a·b + a’·c)  
> F = n·m·o + q’·p’·n’ + m·r

8) (5 pts) Implement a 4-to-2 priority encoder using only NOR gates.
  - a. Derive the truth table.
  - b. Derive the sum-of-product expression.
  - c. Derive the product-of-sum expression.
  - d. Convert the product-of-sum circuit into NOR gate implementation.

> a.  
> | X3   | X2   | X1   | X0   | Y1   | Y0   |
> | :--: | :--: | :--: | :--: | :--: | :--: |
> | 0    | 0    | 0    | X    | 0    | 0    |
> | 0    | 0    | 1    | X    | 0    | 1    |
> | 0    | 1    | X    | X    | 1    | 0    |
> | 1    | X    | X    | X    | 1    | 1    |

> - b. Y1 = X3 + X3'X2; Y0 = X3 + X3'X2'X1
> - c. Y1 = (X3 + X2); Y0 = (X3 + X2 + X1)(X3 + X2')
> - d. Y1 = {(X3 + X2)' + 0}'; Y0 = {(X3 + X2)'' + X1)' + (X3 + X2')'}'  