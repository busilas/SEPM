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
