import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

sf = pd.read_csv("C:\\Users\\Maria\\Desktop\\SF - Crime Data 2016_.csv")

#just printing the table summary
print (sf)

#printing the entire table (might take a while)
print(sf.to_string())


print (type(list(sf.columns.values))) # converting an np.array to a list
print (type(sf.columns.values)) #checking the type of the column

#printing the name of the columns
print (list(sf.columns.values))

# print a specific col
print (sf.Category)

print(list(sf.loc[12])) #printing a specific row as a list

print(sf.loc[52555, "Category"]) #printing a specific LOCation in the table

print (sf.axes) #axes is eixo (2)

s = len(sf.loc[sf['DayOfWeek'] == 'Sunday'])
m = len(sf.loc[sf['DayOfWeek'] == 'Monday'])
t = len(sf.loc[sf['DayOfWeek'] == 'Tuesday'])
w = len(sf.loc[sf['DayOfWeek'] == 'Wednesday'])
th = len(sf.loc[sf['DayOfWeek'] == 'Thursday'])
f = len(sf.loc[sf['DayOfWeek'] == 'Friday'])
sa = len(sf.loc[sf['DayOfWeek'] == 'Saturday'])

result1 = {
    "Sunday": s,
    "Monday": m,
    "Tuesday": t,
    "Wednesday": w,
    "Thursday": th,
    "Friday": f,
    "Saturday": sa
}


for k, v in result1.items():
    print("Cases on {} = {}".format(k, v))

plt.plot (["Sunday","Monday","Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"], [s, m, t, w, th, f, sa])

plt.title("San Francisco Crime")

plt.xlabel("Days of the week")

plt.ylabel("Qty Crimes")

plt.show()

