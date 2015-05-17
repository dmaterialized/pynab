# pYNAB

A simple library designed to make it easy to access YNAB data from Python.

# Examples

Load the shared YNAB budget:

```python
>>> from ynab import YNAB
>>> ynab = YNAB('~/Dropbox/YNAB', 'MyBudget')
```

Get the list of accounts:

```python
>>> ynab.accounts
[<Account: Cash>, <Account: Checking>]
```

Find the total of all reconciled cash transactions starting 2 weeks ago:

```python
>>> sum(ynab.accounts['Cash'].transactions.since('2 weeks ago').filter('reconciled', True).amount)
-22.0
```
