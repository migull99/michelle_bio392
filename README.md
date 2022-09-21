# michelle gull bio392
hello


## 2022-09-21 exercise day_02

#### similar:
```diff
+ use of pandas
+ with open() as
```

#### different:
```diff
-  use of readline() instead of readlines()
-  no use of csv
-  no use of write()
```


```py
# migull99
import pandas as pd
col=['biosample_id','reference_name','start','end','log2','variant_type','reference_bases','alternate_bases']
df=pd.DataFrame(columns=col)
with open('data.pgxseg', 'r') as fh:
    while True:
        line = fh.readline()
        # break while statement if line does not startwith #
        if not line.startswith('#'):
            break
    while line:
        line=fh.readline()
        x=line.split()
        df=df.append(pd.DataFrame([x],columns=col),ignore_index=True)
head(df)
```

```py
# ziyingyang96
import pandas as pd
import csv
df=pd.DataFrame({})
with open('data.pgxseg', newline='') as segfile:
    for line in segfile.readlines():
        if '#' not in line:
            with open('data.csv','a+') as f:
                f.write(line)
df = pd.read_csv('data.csv',sep='\t')
```

