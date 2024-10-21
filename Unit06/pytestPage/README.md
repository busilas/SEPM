<h1 align = "center"> Jupyter Notebook Activity - pytest </h1>

This repository includes exercises, which were part of Module 6 ("Software Engineering Project Management") in Unit 6 (pytest and Test-Driven Development) for my MSc in Computer Science at the University of Essex.

## 1. Step

This task involves working with pytest in the Python programming language. The instructions are provided in the Codio workspace under pytest, where the exercise should be completed. Be sure to save your progress to your GitHub repository.

Copy the following code into a file named wallet.py:

```
# code source: https://semaphoreci.com/community/tutorials/testing-python-applications-with-pytest
# wallet.py
class InsufficientAmount(Exception):
    pass
  
class Wallet(object):
    def __init__(self, initial_amount=0):
        self.balance = initial_amount
 
    def spend_cash(self, amount):
        if self.balance < amount:
            raise InsufficientAmount('Not enough available to spend {}'.format(amount))
        self.balance -= amount
 
    def add_cash(self, amount):
        self.balance += amount
```

## 2. Step

Copy the following code into a file named test_wallet.py:

```
# code source: https://semaphoreci.com/community/tutorials/testing-python-applications-with-pytest
# test_wallet.py
 import pytest
from wallet import Wallet, InsufficientAmount

def test_default_initial_amount():
    wallet = Wallet()
    assert wallet.balance == 0
 
def test_setting_initial_amount():
    wallet = Wallet(100)
    assert wallet.balance == 100
 
def test_wallet_add_cash():
    wallet = Wallet(10)
    wallet.add_cash(90)
    assert wallet.balance == 100
 
def test_wallet_spend_cash():
    wallet = Wallet(20)
    wallet.spend_cash(10)
    assert wallet.balance == 10
 
def test_wallet_spend_cash_raises_exception_on_insufficient_amount():
    wallet = Wallet()
    with pytest.raises(InsufficientAmount):
        wallet.spend_cash(100)
```

## Tasks:

- Task 1: Run the tests using the command: $ pytest -q test_wallet.py You should see the following output: pass
- Task 2: Amend the code so that the tests fail.

## Results:
