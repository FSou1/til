# grid-column and grid-row

If you want to expand a cell on multiple columns or rows, you can use `grid-column` and `grid-row` properties:

```
.el--2 {
  grid-column: 1 / 5;
  grid-row: 2 / 3;
}
```

`grid-column: 1 / 5;` means start at the column `1` and finish at the column `5`.

If you don't want to specify the exact index of the column, you can use `span` (which means start at `1` and finish at `1+4`):

```
.el--2 {
  grid-column: 1 / span 4;
  grid-row: 2 / 3;
}
```

You can also use `-1`, which means go from `1` to the end of the row:

```
.el--2 {
  grid-column: 1 / -1;
  grid-row: 2 / 3;
}
```
