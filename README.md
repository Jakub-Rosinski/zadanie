ZADANIE: CODE REVIEW
1. Otrzymujesz program w pythonie (wersja 3.7).
2. W ramach rozwiązania należy zgłosić uwagi tak jakby to było code review w zespole.
3. Nie ma limitu uwag, można zgłaszać wszystkie nasuwające się uwagi.
4. Proszę wykonane zadanie umieścić na GitHubie (jako prywatne) i zaprosić
użytkowników: https://github.com/c3z oraz https://github.com/PBA77 do jego
wglądu.

Prośba o informację czy wszystkie kwestie są jasne oraz ile czasu mniej więcej zajęło
wykonanie zadania.

Powodzenia!


FRAGMENT KODU:

```
foo = []

from .models import Expense
from collections import namedtuple

MyExpense = namedtuple('F', ['type_', 'amount'])

# test data
foo.append(MyExpense('food', 4))
foo.append(MyExpense('food', 3))
foo.append(MyExpense('var', 3))
foo.append(MyExpense('dog', 1))


def summarizeExpenses(min_amount, input):
    expenses = {}
    for expense in input:
        if expense.amount >= min_amount:
            if not expense.type in expenses:
                expenses[expense.type_] = 0
            expenses[expense.type_] = expenses[expense.type_] + expense.amount

    for (expense, amount) in sorted(expenses.items(), key=lambda e: e[1], reverse=False):
        print expense.type_, amount


summarizeExpenses(2, foo)
```
