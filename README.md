
import numpy as np
import pandas as pd
from scipy.stats import mode
import matplotlib.pyplot as plt


df=pd.read_csv('HamoyeData1.csv')
print(df.head(10))

print(df.fuel_unit)
modalfuelunit=mode(df.fuel_unit).mode[0]

print(modalfuelunit)

df.fuel_unit=df.fuel_unit.fillna(modalfuelunit)
missingfuelunit=df.fuel_unit.isnull().sum()
print(missingfuelunit)
