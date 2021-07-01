# QNT755-FinalProject-Repo today is June 22
import numpy as np
from statistics import mean, median, mode, stdev
from collections import Counter
path   = 'NHANES.csv'
header = []
with open(path, 'r') as f:
     raw = [row.replace('\r','').replace('\n','') for row in f.readlines()]
header = raw[0][1:].rsplit(',')
c_idx = {header[i]:i for i in range(len(header))}
print(c_idx)
data = []
for line in raw:
    data.append(line.rsplit(','))
female_sleep = []
for row in data[1:]:
    if row[2]=='female' and row[49]!='NA':
        female_sleep.append(int(row[49]))
male_sleep = []
for row in data[1:]:
    if row[2]=='male' and row[49]!='NA':
        male_sleep.append(int(row[49]))
print(np.mean(female_sleep))
print(np.mean(male_sleep))
ave_female_BMI = []
for row in data[1:]:
    if row[2]=='female' and row[20]!='NA':
        ave_female_BMI.append(float(row[20]))
ave_male_BMI = []
for row in data[1:]:
    if row[2]=='male' and row[20]!='NA':
        ave_male_BMI.append(float(row[20]))
print('ave_female BMI =', np.mean(ave_female_BMI))        
print('ave_male BMI =', np.mean(ave_male_BMI))
female_BPSysAve = []
for row in data[1:]:
    if row[2]=='female' and row[24]!='NA':
female_BPSysAve.append(int(row[24]))
male_BPSysAve = []
for row in data[1:]:
    if row[2]=='male' and row[24]!='NA':
        male_BPSysAve.append(int(row[24]))
print('female BPSysAve =', np.mean(female_BPSysAve))        
print('male BPSysAve =', np.mean(male_BPSysAve))
female_BPDiaAve = []
for row in data[1:]:
    if row[2]=='female' and row[25]!='NA':
        female_BPDiaAve.append(int(row[25]))
male_BPDiaAve = []
for row in data[1:]:
    if row[2]=='male' and row[25]!='NA':
        male_BPDiaAve.append(int(row[25]))
print('Avg female BPDia =', np.mean(female_BPDiaAve))        
print('Avg male BPDia =', np.mean(male_BPDiaAve))
female_TotChol = []
for row in data[1:]:
    if row[2]=='female' and row[34]!='NA':
        female_TotChol.append(float(row[34]))
male_TotChol = []
for row in data[1:]:
    if row[2]=='male' and row[34]!='NA':
        male_TotChol.append(float(row[34]))
print('Avg Female Total Cholesterol =', np.mean(female_TotChol))        
print('Avg Male Total Cholesterol =', np.mean(male_TotChol))
female_Diabetes = []
for row in data[1:]:
    if row[2]=='female' and row[39]!='NA':
        female_Diabetes.append(row[39])
male_Diabetes = []
for row in data[1:]:
    if row[2]=='male' and row[39]!='NA':
        male_Diabetes.append(row[39])
print('Female Diabetes', Counter(female_Diabetes))        
print('Male Diabetes', Counter(male_Diabetes))
female_Alcohol = []
for row in data[1:]:
    if row[2]=='female' and row[58]!='NA':
        female_Alcohol.append(int(row[58]))
male_Alcohol = []
for row in data[1:]:
    if row[2]=='male' and row[58]!='NA':
        male_Alcohol.append(int(row[58]))
print('Avg Female Alcohol Drinks per Day =', np.mean(female_Alcohol))        
print('Avg Male Alcohol Drinks per Day =', np.mean(male_Alcohol))
female_PA = []
for row in data[1:]:
    if row[2]=='female' and row[52]!='NA':
        female_PA.append(int(row[52]))
male_PA = []
for row in data[1:]:
    if row[2]=='male' and row[52]!='NA':
        male_PA.append(int(row[52]))
print('Avg Female Days of Physical Activity per Week =', np.mean(female_PA))        
print('Avg Male Days of Physical Activity per Week =', np.mean(male_PA))
female_TV = []
for row in data[1:]:
    if row[2]=='female' and row[53]!='NA':
        female_TV.append(row[53])
male_TV = []
for row in data[1:]:
    if row[2]=='male' and row[53]!='NA':
        male_TV.append(row[53])
print('Female TV', Counter(female_TV))        
print('Male TV', Counter(male_TV))
