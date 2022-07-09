# teja-python


```python

# excel consolidation
# https://colab.research.google.com/
import pandas as pd
import glob
import os
path = "/content/"
filenames = glob.glob(path + "*.xlsx")
print('File names:', filenames)
outputxlsx = pd.DataFrame()
for file in filenames:
    df = pd.concat(pd.read_excel( file, sheet_name=None), ignore_index=True, sort=False)
    outputxlsx = outputxlsx.append( df, ignore_index=True)

print('Final Excel sheet now generated at the same location:')
outputxlsx.to_excel("Output.xlsx", index=False)
```


```python


# csv to excel consolidation
import pandas as pd
import glob
path = "/content/"
filenames = glob.glob(path + "*.csv")
li = []
for filename in filenames:
    df = pd.read_csv(filename, index_col=None, header=0, encoding= 'unicode_escape')
    li.append(df)
frame = pd.concat(li, axis=0, ignore_index=True)
frame.to_excel("outputfile.xlsx",index = False)
```
