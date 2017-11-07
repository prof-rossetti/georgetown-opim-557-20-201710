# Project 1 - Retirement Savings Calculator

> Adapted from a deliverable created by Professor Dillon-Merrill.

You own and operate a financial planning business which helps customers plan for retirement.

Your objective is to build yourself a tool to automate the common calculations required to provide your clients with retirement savings advice.

Specifically, the system should accept a number of information inputs representing the client's savings goals, and should produce an information output representing the amount of money the client can expect to have saved upon reaching retirement age.

## Prerequisites

  + ["All the Controls" Exercise](/exercises/all-the-controls/exercise.md) (and all of its prerequisites)
  + [The `InputBox` function](/notes/visual-basic/functions/input-box.md)
  + [String Formatting](/notes/visual-basic/datatypes/strings.md#string-formatting)
  + Data Quality - [Validations](/notes/visual-basic/datatypes.md#checking-a-variables-type)
  + Control Flow - [Loops](/notes/visual-basic/loops.md) and [Functions](/notes/visual-basic/functions.md)

## Learning Objectives

  + Design and build a tool to aid a decision-making process.
  + Use ActiveX Controls and VBA to capture and validate user inputs.
  + Use VBA to perform programmatic calculations to arrive at a final system output.







## Information Requirements

### Information Inputs

Your system should accept the following user inputs:

  + The client's current age.
  + The client's desired retirement age.
  + The client's current amount of savings (a.k.a. initial savings balance). Assume the client does not have any debt.
  + The amount of money the client plans to contribute to savings each year. Assume contributions are made at the end of each year, after interest has been accrued.
  + A projected annual growth rate for the client's savings (a.k.a the interest rate). Assume interest will compound on an annual basis (at the end of each year), not on a monthly basis.

The table below provides a framework for you to translate these information inputs into VBA variables.

info input | suggested variable name | variable datatype | example value
--- | ---  | ---  | ---
Current Age | `Age` | `Integer` | `60`
Desired Retirement Age | `RetirementAge` | `Integer` | `65`
Initial Savings Balance | `InitialBalance` | `Double` | `50000.00`
Annual Savings Contribution | `AnnualContribution` | `Double` | `18000.00`
Annual Savings Growth Rate (Interest Rate) | `InterestRate` | `Double` | `0.05`

### Information Outputs

Your system should produce the following outputs:

  + The final savings balance at the end of the year when the client reaches the specified retirement age.
  + The portion of the final savings balance which was contributed directly by the client.
  + The portion of the final savings balance resulting from accrued interest on the principal.

The table below provides a framework for you to translate these information inputs into VBA variables.

info output | suggested variable name | variable datatype | example value
--- | ---  | ---  | ---
Final Savings Balance | `SavingsBalance` | `Double` | `189439.21`
Total Savings Contribution | `TotalContribution` | `Double` | `158000.00`
Total Interest Accrued | `InterestAccrued` | `Double` | `31439.21`

See the "Calculation Requirements" section below for more information about how to calculate these information outputs.

## Interface Requirements

Provide written instructions which explain how to use the tool.

Use cells and/or input boxes and/or ActiveX Controls to capture user inputs. You are encouraged to use ActiveX Controls because they can provide a better user experience and can ease the validation process. If using ActiveX Controls, use them only as appropriate.

Regardless of how you choose to capture user inputs, make sure the user sees only properly-formatted values. Rates should be formatted with a percent sign (`%`) and dollar amounts should be formatted as USD with a dollar sign (`$`) and two decimal places.

Use an ActiveX `CommandButton` control that when clicked will read and validate the inputs, perform the calculations, and produce the outputs. Outputs should also be properly formatted (see above).

The figure below depicts an example interface:

![a screenshot depicting an example user interface which includes cell inputs and a "Calculate" button](example-interface-cells-only.png)

## Validation Requirements

Prevent the user from inputting invalid values (i.e. entering a value of the wrong data type, entering a value outside of a reasonable range of accepted values, etc.).

If a user enters an invalid input, exit from the program and display a friendly message describing what went wrong and how the user can fix the problem.

## Calculation Requirements

The figure below depicts an example of the system's desired calculations. It is NOT meant to depict the user interface, the way the system captures inputs, or the way the system produces outputs. It is also NOT meant to depict the manner in which the system performs calculations, because the calculations should be performed using VBA, not cell formulae. For clarification, the program does not need to write cell values like this. Again, this is just an example to help you test to make sure your calculations are producing the expected results.

![a screenshot depicting some example inputs, example annual calculations, and example final outputs](example-calculation-results.png)

### Annual Calculations

The savings balance at the end of any given year is equal to the initial savings balance for that year, plus the amount of accrued interest for that year, plus the end-of-year contribution.

The amount of accrued interest for any given year is equal to the initial savings balance for that year times the annual interest rate. Note: the end-of-year contribution does not accrue interest during the year it is contributed.

The initial savings balance for any given year is equal to the ending savings balance from the previous year.

### Final Outputs

The final savings balance output by the system should reflect the balance at the end of the year when the client hits the desired retirement age. For example, if the desired retirement age is 65, the program should output the savings balance at the end of that year, after that year's interest accrual and savings contribution are calculated (see "Annual Calculations" above).

The final amount of interest accrued is equal to the sum of interest accrued during each year.

The final amount of principal contributed is equal to the very first savings balance input by the user, plus the sum of all end-of-year contributions. The amount of principal is also alternatively equal to the final savings balance, less the final amount of accrued interest.





















## Submission Instructions

Submit a single macro-enabled excel file to [Blackboard](https://campus.georgetown.edu/webapps/assignment/uploadAssignment?content_id=_4454661_1&course_id=_745457_1&assign_group_id=&mode=cpview). The file should be named **project-1-`NETID`.xlsm**, where `NETID` represents your own university-issued Net Id (e.g. **project-1-abc123.xlsm**).

## Evaluation Methodology

Full credit for a properly-named file containing a user-friendly interface which properly validates all user inputs and performs the proper calculations to produce the correct output value.

Else partial credit to highlight areas of improvement.

Note: The professor reserves the right to award extra credit in recognition of particularly-effective user experiences.
