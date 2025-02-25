```
usage: rsi [-d {}] [-c TARGET_COLUMN] [--period PERIOD] [-h]
```

Add rsi to dataset based on specific column.

```
optional arguments:
  -d {}, --target-dataset {}
                        The name of the dataset you want to select (default: None)
  -c TARGET_COLUMN, --target-column TARGET_COLUMN
                        The name of the specific column you want to use (default: close)
  --period PERIOD       The period to use (default: 10)
  -h, --help            show this help message (default: False)

For more information and examples, use 'about rsi' to access the related guide.
```

Example:
```
(🦋) /forecast/ $ show TSLA
TSLA has following shape (rowxcolumn): (611, 7)

                    Dataset TSLA | Showing 10 of 611 rows
┏━━━┳━━━━━━━━━━━━┳━━━━━━━━┳━━━━━━━━┳━━━━━━━━┳━━━━━━━━┳━━━━━━━━━━━┳━━━━━━━━━━━┓
┃   ┃ date       ┃ open   ┃ high   ┃ low    ┃ close  ┃ adj_close ┃ volume    ┃
┡━━━╇━━━━━━━━━━━━╇━━━━━━━━╇━━━━━━━━╇━━━━━━━━╇━━━━━━━━╇━━━━━━━━━━━╇━━━━━━━━━━━┩
│ 0 │ 2020-01-02 │ 84.90  │ 86.14  │ 84.34  │ 86.05  │ 86.05     │ 47660500  │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┤
│ 1 │ 2020-01-03 │ 88.10  │ 90.80  │ 87.38  │ 88.60  │ 88.60     │ 88892500  │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┤
│ 2 │ 2020-01-06 │ 88.09  │ 90.31  │ 88.00  │ 90.31  │ 90.31     │ 50665000  │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┤
│ 3 │ 2020-01-07 │ 92.28  │ 94.33  │ 90.67  │ 93.81  │ 93.81     │ 89410500  │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┤
│ 4 │ 2020-01-08 │ 94.74  │ 99.70  │ 93.65  │ 98.43  │ 98.43     │ 155721500 │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┤
│ 5 │ 2020-01-09 │ 99.42  │ 99.76  │ 94.57  │ 96.27  │ 96.27     │ 142202000 │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┤
│ 6 │ 2020-01-10 │ 96.36  │ 96.99  │ 94.74  │ 95.63  │ 95.63     │ 64797500  │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┤
│ 7 │ 2020-01-13 │ 98.70  │ 105.13 │ 98.40  │ 104.97 │ 104.97    │ 132588000 │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┤
│ 8 │ 2020-01-14 │ 108.85 │ 109.48 │ 104.98 │ 107.58 │ 107.58    │ 144981000 │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┤
│ 9 │ 2020-01-15 │ 105.95 │ 107.57 │ 103.36 │ 103.70 │ 103.70    │ 86844000  │
└───┴────────────┴────────┴────────┴────────┴────────┴───────────┴───────────┘

(🦋) /forecast/ $ rsi TSLA
Successfully added 'RSI_10' to 'TSLA' dataset

(🦋) /forecast/ $ show TSLA
TSLA has following shape (rowxcolumn): (611, 8)

                         Dataset TSLA | Showing 10 of 611 rows
┏━━━┳━━━━━━━━━━━━┳━━━━━━━━┳━━━━━━━━┳━━━━━━━━┳━━━━━━━━┳━━━━━━━━━━━┳━━━━━━━━━━━┳━━━━━━━━┓
┃   ┃ date       ┃ open   ┃ high   ┃ low    ┃ close  ┃ adj_close ┃ volume    ┃ RSI_10 ┃
┡━━━╇━━━━━━━━━━━━╇━━━━━━━━╇━━━━━━━━╇━━━━━━━━╇━━━━━━━━╇━━━━━━━━━━━╇━━━━━━━━━━━╇━━━━━━━━┩
│ 0 │ 2020-01-02 │ 84.90  │ 86.14  │ 84.34  │ 86.05  │ 86.05     │ 47660500  │ nan    │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┼────────┤
│ 1 │ 2020-01-03 │ 88.10  │ 90.80  │ 87.38  │ 88.60  │ 88.60     │ 88892500  │ nan    │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┼────────┤
│ 2 │ 2020-01-06 │ 88.09  │ 90.31  │ 88.00  │ 90.31  │ 90.31     │ 50665000  │ nan    │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┼────────┤
│ 3 │ 2020-01-07 │ 92.28  │ 94.33  │ 90.67  │ 93.81  │ 93.81     │ 89410500  │ nan    │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┼────────┤
│ 4 │ 2020-01-08 │ 94.74  │ 99.70  │ 93.65  │ 98.43  │ 98.43     │ 155721500 │ nan    │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┼────────┤
│ 5 │ 2020-01-09 │ 99.42  │ 99.76  │ 94.57  │ 96.27  │ 96.27     │ 142202000 │ nan    │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┼────────┤
│ 6 │ 2020-01-10 │ 96.36  │ 96.99  │ 94.74  │ 95.63  │ 95.63     │ 64797500  │ nan    │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┼────────┤
│ 7 │ 2020-01-13 │ 98.70  │ 105.13 │ 98.40  │ 104.97 │ 104.97    │ 132588000 │ nan    │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┼────────┤
│ 8 │ 2020-01-14 │ 108.85 │ 109.48 │ 104.98 │ 107.58 │ 107.58    │ 144981000 │ nan    │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┼────────┤
│ 9 │ 2020-01-15 │ 105.95 │ 107.57 │ 103.36 │ 103.70 │ 103.70    │ 86844000  │ nan    │
└───┴────────────┴────────┴────────┴────────┴────────┴───────────┴───────────┴────────┘

(🦋) /forecast/ $ clean TSLA
Namespace(drop='', fill='', help=False, limit=5, target_dataset='TSLA')
Successfully cleaned 'TSLA' dataset

(🦋) /forecast/ $ show TSLA
TSLA has following shape (rowxcolumn): (601, 8)

                         Dataset TSLA | Showing 10 of 601 rows
┏━━━┳━━━━━━━━━━━━┳━━━━━━━━┳━━━━━━━━┳━━━━━━━━┳━━━━━━━━┳━━━━━━━━━━━┳━━━━━━━━━━━┳━━━━━━━━┓
┃   ┃ date       ┃ open   ┃ high   ┃ low    ┃ close  ┃ adj_close ┃ volume    ┃ RSI_10 ┃
┡━━━╇━━━━━━━━━━━━╇━━━━━━━━╇━━━━━━━━╇━━━━━━━━╇━━━━━━━━╇━━━━━━━━━━━╇━━━━━━━━━━━╇━━━━━━━━┩
│ 0 │ 2020-01-16 │ 98.75  │ 102.89 │ 98.43  │ 102.70 │ 102.70    │ 108683500 │ 76.00  │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┼────────┤
│ 1 │ 2020-01-17 │ 101.52 │ 103.13 │ 100.63 │ 102.10 │ 102.10    │ 68145500  │ 74.45  │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┼────────┤
│ 2 │ 2020-01-21 │ 106.05 │ 109.72 │ 105.68 │ 109.44 │ 109.44    │ 89017500  │ 80.00  │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┼────────┤
│ 3 │ 2020-01-22 │ 114.38 │ 118.90 │ 111.82 │ 113.91 │ 113.91    │ 156845000 │ 82.56  │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┼────────┤
│ 4 │ 2020-01-23 │ 112.85 │ 116.40 │ 111.12 │ 114.44 │ 114.44    │ 98255000  │ 82.85  │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┼────────┤
│ 5 │ 2020-01-24 │ 114.13 │ 114.77 │ 110.85 │ 112.96 │ 112.96    │ 71768000  │ 78.80  │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┼────────┤
│ 6 │ 2020-01-27 │ 108.40 │ 112.89 │ 107.86 │ 111.60 │ 111.60    │ 68040500  │ 75.05  │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┼────────┤
│ 7 │ 2020-01-28 │ 113.70 │ 115.36 │ 111.62 │ 113.38 │ 113.38    │ 58942500  │ 76.66  │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┼────────┤
│ 8 │ 2020-01-29 │ 115.14 │ 117.96 │ 113.49 │ 116.20 │ 116.20    │ 89007500  │ 79.05  │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┼────────┤
│ 9 │ 2020-01-30 │ 126.48 │ 130.18 │ 123.60 │ 128.16 │ 128.16    │ 145028500 │ 85.87  │
└───┴────────────┴────────┴────────┴────────┴────────┴───────────┴───────────┴────────┘

```
