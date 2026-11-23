# Py-SECTION 1 MISSION PROJECT — THE DIGITAL TRANSLATOR

Mission: mission-03
Squad: Solo 791

This repository was created for the Squad mission workspace.

Use this repository for the team's implementation. Commit and push all meaningful work to Gitea, then submit the Mission for inspection from TalentNation when the Squad is ready.


## Tier 1 - Basic Understanding: The Literal Assistant
### Task: Make me breakfast

#### Breakfast Order

This example uses two slices of bread, two eggs, and one cup of tea. It assumes
the ingredients and equipment listed below are available in the kitchen, and
that the person eating has no allergy or dietary restriction involving them.
Check this before starting. If an ingredient or required piece of equipment is
missing, or the dietary check fails, stop and ask what to do. Do not substitute
anything.

#### Ingredients and equipment

- 2 slices of bread
- 2 eggs
- 1 tea bag
- 1 cup (about 240 ml) of drinking water
- 1 teaspoon of butter
- 1 clean plate, 1 mug, 1 bowl, and 1 fork
- Toaster, kettle, non-stick frying pan, and spatula

#### Instructions

1. Wash your hands with soap and water. Put the plate, mug, bowl, and fork on
   the clean kitchen counter. Keep the pan handle turned away from the edge of
   the counter or stove.
2. Put both slices of bread in the toaster. Toast until golden brown. If the
   toaster has a browning control, use its medium setting. When done, put the
   toast on the plate.
3. Pour 1 cup (about 240 ml) of water into the kettle and switch it on. When it
   switches off, carefully pour the hot water into the mug. Add the tea bag and
   steep it for 3 minutes, then remove and discard the tea bag. Leave the mug
   on the counter; warn the person that the tea is hot.
4. Crack both eggs into the bowl. Check that no shell fell in; remove any shell
   with a clean utensil if needed. Beat the eggs with the fork until the yolks
   and whites are evenly mixed.
5. Put the pan on the stove and turn the burner to low-medium heat. Add 1
   teaspoon of butter. When the butter has melted, pour in the beaten eggs.
6. Stir the eggs slowly with the spatula, scraping the bottom of the pan.
   Continue until the eggs are fully set with no visible liquid egg remaining.
   Turn off the burner, then transfer the eggs to the plate beside the toast.
7. Check that the burner is off. Place the plate and mug on the kitchen table.
   Tell the person breakfast is ready and that the tea is hot. The task is
   complete when the toast and fully cooked eggs are on the plate, the tea is
   in the mug, and both are on the table.

#### Reasoning challenge

The original request did not say what foods to make, how much to prepare,
where ingredients or equipment were, what tools or cooking methods to use, in
what order to do things, where to serve the food, or what “finished” means. This example makes
those choices explicit as assumptions.

## Tier 2 — Field Exercise: Algorithm Thinking

### Task: The ATM


*** Algorithm ***

1. Insert customer's card.
2. If card cannot be read, return the card, and
   end the session without changing the account.
3. Check that the card is valid and can be used. If not, explain that the
   transaction cannot continue, return the card, and end the session.
4. Ask the customer to enter their PIN without displaying the digits. Validate
   it securely. Allow up to three attempts. If all attempts fail, cancel the
   transaction, return the card, and end the session.
5. Ask the customer to select the account to withdraw from and choose
   **Withdrawal**.
6. Ask for the withdrawal amount. If the customer cancels, cancel the
   transaction, return the card, and end the session.
7. Check that the amount is positive, within the ATM's withdrawal limits, and
   can be dispensed using the cash available in the machine. If not, explain
   why and ask for another amount or let the customer cancel.
8. Ask the bank to authorize the withdrawal. Check that the account has enough
   available funds and that the request is approved. If it is declined or the
   bank cannot be reached, do not dispense cash; explain that the withdrawal
   could not be completed, return the card, and end the session.
9. Dispense the authorized amount. Confirm that the ATM delivered the full
   amount before marking the withdrawal successful and finalizing the account
   update.
10. If the ATM cannot dispense the full amount, do not report success. Record
    what happened, request that any pending authorization be released or
    corrected, and notify the customer that the transaction needs attention.
11. Offer a receipt. Return the card and any dispensed cash and receipt. Tell
    the customer to take them. End the session when the transaction result is
    clear and the card has been returned.

### Think About Failure

- **Card cannot be read:** Return it, explain the problem, and do not start a
  transaction.
- **PIN is incorrect:** Allow up to three attempts; then cancel and return the
  card without revealing or displaying the PIN.
- **Requested amount exceeds the available balance:** Do not dispense cash.
  Explain that the request was declined and let the customer enter a different
  amount or cancel.
- **ATM does not have enough cash:** Do not send an unfulfillable withdrawal
  request. Explain that the machine cannot provide that amount and let the
  customer enter a supported amount or cancel.
- **Transaction cannot be completed:** Do not report success. If the ATM has
  already reserved funds, request that the reservation be released or
  corrected, record the failure, and explain the result to the customer.

### Key distinction

- The **problem** is the goal: withdraw money from an ATM.
- The **algorithm** is the ordered procedure, including decisions and what to
  do when a step fails.
- The **program** is executable instructions that carry out the algorithm.

The flow is: Text
Problem → Algorithm → Program

## Tier 3 — Practical Exercise: Input → Processing → Output

### The Simple Calculator

The calculator receives two numbers, `20` and `5`, and an operation to perform.
It applies that operation to the numbers and produces the result.

| Input | Processing | Output |
|---|---|---:|
| `20`, `5` | Addition: `20 + 5` | `25` |
| `20`, `5` | Subtraction: `20 - 5` | `15` |
| `20`, `5` | Multiplication: `20 × 5` | `100` |
| `20`, `5` | Division: `20 ÷ 5` | `4` |

For each calculation, the inputs are the two numbers and the selected
operation. The processing step applies that operation, and the output is its
result.

### Reasoning Challenge: Division by Zero

If the inputs are `20` and `0` and the selected operation is division, the
calculator must check the second number before dividing. Division by zero is
undefined, so the calculator should not attempt the operation or return a
misleading numeric answer. It should instead display a clear error, such as
“Cannot divide by zero.”

### Objective

The model for every calculation is: Text
INPUT → PROCESS → OUTPUT

The program receives values and an operation, processes them according to the
selected operation, and produces either a result or a clear error when the
operation cannot be performed.

## Tier 4 — Conceptual Challenge: Data Translator

### Identify the Data

| Information | Kind of information | Example representation |
|---|---|---|
| Customer name: `Victor` | Text (string) | A sequence of characters |
| Age: `30` | Whole number (integer) | An integer value |
| Account balance: `150000.50` | Decimal amount | An exact decimal value, or an integer count of minor currency units with a defined scale |
| Account active: `Yes` | True/false state (Boolean) | `true` |

The balance's currency is not specified in the example, so a real system would
also need to store or define the currency. It should use a representation and
scale that preserve the exact amount rather than accidentally rounding it.

### From Information to Stored Data

The computer must represent each value in a form it can store and process.
For example, the name is represented as characters using an encoding such as
UTF-8; numbers are represented using an appropriate numeric format; and the
account state is represented as one of two values, such as `true` or `false`.
Ultimately, these representations are encoded as bits that the computer can
store and communicate.

```text
Real-world information
↓
Data representation
↓
Digital values encoded as bits
↓
Stored and processed by the computer
```

### Reasoning Challenge: Incorrect Balance

If `150000.50` is stored or interpreted as a different amount, the system
could show an incorrect balance, allow an invalid withdrawal, reject a valid
transaction, or create inaccurate statements. Correct representation,
interpretation, and validation are necessary to process the account safely.

### Objective

Data is information represented in a form that a computer can store, process,
and communicate.

## Tier 5 — Architecture Challenge: Explain the Whole System

### The Online Store

The customer starts an order by selecting a product, entering a quantity,
providing delivery information, and choosing a payment method. The store
application receives these inputs and follows its instructions to validate
them, find the product, and check its availability.

If the information is valid and the product is available, the program
calculates the order total. For example, if one product costs `50,000` and the
customer orders two, the subtotal is `100,000` in the same currency, before any
applicable taxes or delivery charges. The system then requests payment
authorization through its payment service. It should not treat an order as
paid unless authorization succeeds.

When payment is authorized, the application records the order details, such as
the customer and product identifiers, quantity, total, delivery information,
and order status. Sensitive payment credentials should be handled by the
payment service rather than stored as ordinary order data. The store then
returns an output, such as:

```text
Order confirmed. Total: 100,000.
```

If validation, availability checks, or payment authorization fail, the
application should explain that the order was not confirmed and avoid
recording it as a completed, paid order.

The complete flow is:

```text
Customer input
↓
Application/program
↓
Instructions
↓
Data processing
↓
Stored order data
↓
Confirmation or clear failure message
```

## Final Challenge

```text
Custo
↓
Program
↓
Instructions
↓
Data processing
↓
Stored order data
↓
Result
```

The customer provides data such as the chosen product, quantity, delivery
address, and payment method. The computer runs the store's program, which
executes instructions to validate the input, check product availability,
calculate the total, and request payment authorization. It stores the order
details and status so the store can remember and fulfill the order. The output
is a confirmation with the order total if the order succeeds, or a clear
message explaining why it could not be completed.

## Final Reflection
Computer don't actually know what eggs or money or customers are, it only has data that represents them, numbers,text,true/false saved as 1s and 0s.And it follows instrustions on that data. Someone has to turn what a person wants into data and steps first, if that is wrong the computer still follows it and gives the wrong result.