A collection of good food/coffee places. Right now, there is `Berlin.csv` for
places in Berlin that I personally know and `Berlin-Todo.csv` for places that I
yet need to visit.

## Useful commands for working with these lists

Print in a readable way and sort first by area and then restaurant type:

```bash
cat Berlin.csv | sort -t"|" -k 3,3 -k 2,2 | column -s"|" -t
```

Filter by area and print:

```bash
awk -F"|" '$3 ~ /Prenzlauer Berg/ {print $0}' < Berlin.csv | sort -t"|" -k 3,3 -k 2,2 | column -s"|" -t
```

Filter by type and print:

```bash
awk -F"|" '$2 ~ /Coffee/ {print $0}' < Berlin.csv | sort -t"|" -k 3,3 -k 2,2 | column -s"|" -t
```
