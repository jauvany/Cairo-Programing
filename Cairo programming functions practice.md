# code 10 programming exercises to practice writing smart contract functions in Cairo programming language

Here are ten programming exercises designed to help you practice writing smart contract functions in the Cairo programming language:

## 1. Hello World
**Objective:** Create a simple function that returns "Hello, World!".
- **Function:** `fn hello() -> felt252`

## 2. String Reversal
**Objective:** Write a function that takes a string and returns it reversed.
- **Input:** A string of characters.
- **Output:** The reversed string.

## 3. Phone Number Cleanup
**Objective:** Clean up user-entered phone numbers by removing non-numeric characters.
- **Input:** A string representing a phone number.
- **Output:** A cleaned string of digits.

## 4. Largest Product of Substring
**Objective:** Given a string of digits, calculate the largest product for a contiguous substring of length `n`.
- **Input:** A string of digits and an integer `n`.
- **Output:** The largest product.

## 5. Basic Arithmetic Operations
**Objective:** Implement functions for basic arithmetic operations (addition, subtraction, multiplication, division).
- **Functions:**
  - `fn add(a: felt252, b: felt252) -> felt252`
  - `fn subtract(a: felt252, b: felt252) -> felt252`
  - `fn multiply(a: felt252, b: felt252) -> felt252`
  - `fn divide(a: felt252, b: felt252) -> felt252`

## 6. Simple Voting Contract
**Objective:** Create a contract that allows users to vote for candidates and count the votes.
- **Functions:**
  - `fn vote(candidate_id: felt252)`
  - `fn get_votes(candidate_id: felt252) -> felt252`

## 7. ERC20 Token Implementation
**Objective:** Implement a basic ERC20 token contract with functions for transferring tokens and checking balances.
- **Functions:**
  - `fn transfer(to: felt252, amount: felt252)`
  - `fn balance_of(owner: felt252) -> felt252`

## 8. Access Control with Roles
**Objective:** Create a contract that manages user roles (e.g., admin, user) and restricts access to certain functions based on roles.
- **Functions:**
  - `fn add_role(user_id: felt252, role: Role)`
  - `fn has_role(user_id: felt252, role: Role) -> bool`

## 9. Event Logging
**Objective:** Implement a contract that logs events when certain actions are performed (e.g., token transfers).
- **Function:** 
  - `fn emit_transfer_event(from: felt252, to: felt252, amount: felt252)`

## 10. Multi-signature Wallet
**Objective:** Create a multi-signature wallet where multiple signatures are required to execute transactions.
- **Functions:**
  - `fn submit_transaction(to: felt252, amount: felt252)`
  - `fn confirm_transaction(transaction_id: felt252)`
  
These exercises will provide you with practical experience in writing smart contracts using Cairo while reinforcing your understanding of its syntax and features. For more structured practice, consider using platforms like Exercism which offer guided exercises and mentorship in Cairo programming [1][6].

Citations:
[1] https://exercism.org/tracks/cairo
[2] https://www.youtube.com/watch?v=Z9guya4W4iw
[3] https://www.cairo-lang.org
[4] https://www.cairo-lang.org/tutorials/
[5] https://reilabs.io/blog/introducing-hints-in-cairo-programming-language/
[6] https://exercism.org/tracks/cairo/exercises
[7] https://github.com/exercism/cairo
[8] https://github.com/morkeltry/Some-Cairo-execrcies

# code 10 programming exercises to practice writing smart contract functions in the Cairo programming language

Here are 10 programming exercises to help practice writing smart contract functions in the Cairo programming language, focusing on various fundamental concepts:

### 1. **Basic Arithmetic Function**
Write a Cairo smart contract function that takes two unsigned integers and returns their sum, difference, product, and quotient.

```python
@external
func basic_arithmetic(x: felt, y: felt) -> (sum: felt, difference: felt, product: felt, quotient: felt):
    let sum = x + y
    let difference = x - y
    let product = x * y
    let quotient = x / y
    return (sum, difference, product, quotient)
end
```

### 2. **Conditional Statement**
Write a function that takes an integer `x` and returns whether it is even or odd.

```python
@external
func is_even(x: felt) -> (result: felt):
    let result = if x % 2 == 0 then 1 else 0
    return (result)
end
```

### 3. **Fibonacci Sequence**
Write a Cairo smart contract function that returns the Nth Fibonacci number using recursion.

```python
@external
func fibonacci(n: felt) -> (result: felt):
    if n == 0:
        return (0)
    elif n == 1:
        return (1)
    else:
        let (a) = fibonacci(n - 1)
        let (b) = fibonacci(n - 2)
        return (a + b)
    end
end
```

### 4. **Factorial Calculation**
Write a Cairo function that calculates the factorial of a given number using recursion.

```python
@external
func factorial(n: felt) -> (result: felt):
    if n == 0:
        return (1)
    else:
        let (fact) = factorial(n - 1)
        return (n * fact)
    end
end
```

### 5. **Maximum of Two Numbers**
Write a function that takes two numbers as input and returns the maximum.

```python
@external
func max_of_two(a: felt, b: felt) -> (max: felt):
    let max = if a > b then a else b
    return (max)
end
```

### 6. **Simple Voting System**
Write a basic voting system where users can vote for candidate `A` or `B`. The function should update vote counts and return the current standings.

```python
@storage_var
func votes_A() -> (count: felt):
end

@storage_var
func votes_B() -> (count: felt):
end

@external
func vote(candidate: felt):
    if candidate == 1:
        let (current_votes) = votes_A.read()
        votes_A.write(current_votes + 1)
    else:
        let (current_votes) = votes_B.read()
        votes_B.write(current_votes + 1)
    end
end
```

### 7. **Array Sum**
Write a function that calculates the sum of all elements in a fixed-size array.

```python
@external
func array_sum(arr: felt*) -> (sum: felt):
    let length = len(arr)
    let mut total_sum = 0
    let mut i = 0
    while i < length:
        let total_sum = total_sum + arr[i]
        let i = i + 1
    end
    return (total_sum)
end
```

### 8. **Prime Number Checker**
Write a function that checks if a given number is prime.

```python
@external
func is_prime(n: felt) -> (result: felt):
    if n <= 1:
        return (0)
    let mut i = 2
    while i * i <= n:
        if n % i == 0:
            return (0)
        let i = i + 1
    end
    return (1)
end
```

### 9. **Basic Counter with Increment and Decrement**
Create a simple counter with functions to increment and decrement the counter's value.

```python
@storage_var
func counter() -> (value: felt):
end

@external
func increment():
    let (current_value) = counter.read()
    counter.write(current_value + 1)
end

@external
func decrement():
    let (current_value) = counter.read()
    counter.write(current_value - 1)
end
```

### 10. **Simple Bank Account**
Write a simple bank account contract where users can deposit and withdraw funds.

```python
@storage_var
func balance(account: felt) -> (value: felt):
end

@external
func deposit(account: felt, amount: felt):
    let (current_balance) = balance(account).read()
    balance(account).write(current_balance + amount)
end

@external
func withdraw(account: felt, amount: felt) -> (success: felt):
    let (current_balance) = balance(account).read()
    if current_balance >= amount:
        balance(account).write(current_balance - amount)
        return (1)
    else:
        return (0)
    end
end
```

These exercises cover fundamental smart contract operations in Cairo, including arithmetic, conditional logic, loops, recursion, and storage.
