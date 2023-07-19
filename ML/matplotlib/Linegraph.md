## Exmaple -1

```python
from matplotlib import pyplot as plt

#linear Line graph
plt.plot([1,2,3,4],[2,4,6,8],color="r", marker="o", linewidth=3)
plt.xlabel("X")
plt.ylabel("Y")
plt.title("Linear line graph",fontsize=15)
plt.show()

```

## Example-2
```python
# Read the data from Delhi Temprature file
df_delhi = pd.read_csv("DelhiTemprature.csv")
days = df_delhi["days"]
temp = df_delhi["temp"]
plt.plot(days,temp, color='r', marker='o', linewidth=1)
plt.xlabel("June Days")
plt.ylabel("Temp in fahrenheit")
plt.title("Delhi Temprature")

```

## Example-3
```python
# Compare Delhi and Bangalore Tempratures
df_delhi = pd.read_csv("DelhiTemprature.csv")
days = df_delhi["days"]
temp = df_delhi["temp"]
df_blr = pd.read_csv("BangaloreTemprature.csv")
days1 = df_blr["days"]
temp1 = df_blr["temp"]
plt.plot(days,temp, color='r', marker='o', linewidth=1,label="DelhiTemp")
plt.plot(days1,temp1, color='y', marker='^', linewidth=1, label="BlrTemp")
plt.xlabel("June Days")
plt.ylabel("Temp in fahrenheit")
plt.title("Delhi vs Bangalore Temprature")
plt.legend()
```

## Example-4
```python
# Apply grid style
from matplotlib import style
df_delhi = pd.read_csv("DelhiTemprature.csv")
days = df_delhi["days"]
temp = df_delhi["temp"]
df_blr = pd.read_csv("BangaloreTemprature.csv")
days1 = df_blr["days"]
temp1 = df_blr["temp"]
style.use("ggplot")
plt.plot(days,temp, color='r', marker='o', linewidth=1,label="DelhiTemp")
plt.plot(days1,temp1, 'y^--', linewidth=1, label="BlrTemp")
plt.xlabel("June Days")
plt.ylabel("Temp in fahrenheit")
plt.title("Delhi vs Bangalore Temprature")
plt.grid(color='k', linestyle='--', linewidth=2)
plt.legend()
```

