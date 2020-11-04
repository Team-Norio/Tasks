
We want to understand the most and least profitable hour of the day for a given restaurant when looking at labour cost. You'll have two csvs, one describing the shifts, and one describing the hourly sales.

## Labour Data

A shift will include the pay-rate (per hour), the start and end time, and a text field where the manager will enter break info. This may vary depending on the individual manager.

For example:
```
{
    'break_notes': '15-18',
    'start_time': '10:00',
    'end_time': '23:00',
    'pay_rate': 10.0
}
```

The data given shows a shift started at 10AM and ended at 11PM. However, the break_notes "15-18" indicates that the staff member took a 3 hour break in the middle of the day (when they would not be paid). The employee was paid £10 per hour.

## Sales Data

This shows you a set of transactions:

For example
```
[
      {
          'time' : '10:31,
          'amount' : 50.32
      }
]
```

We are hoping that you can compute different metrics for the different hours,
such as the total sales during this hour, the cost of labour for this hour, and
the cost of labour as percentage of sales.

e.g.,
```
Hour	Sales	Labour	%
7:00	100	    30	    30%
8:00	300	    60	    20%
```

## Best and Worst Hours

The goal is to output which hour was the best and worst in terms of labour cost as a percentage of sales. If the sales are null, then return -cost instead of percentage. (e.g -40).

## Instructions

- The `EmptySolution.py` file contains some functions.
- If you need to create other functions, you're free to do so, just keep in mind that the functions that are already defined need to work;