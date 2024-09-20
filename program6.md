## 6. Write a python program create csv file student.csv(sid,sname,city,contact) using 10 records. (in which 5 records input directly and 5 records take input from user) write records into this file.Read this file using csv module and print only those where city is 'Bar


```python
import csv
```


```python
l=[
    [1,'om','bardoli','1234567890'],
    [2,'sai','surat','3456789012'],
    [3,'ram','vyara','1234567123'],
    [4,'radha','ahmedabad','1234337890'],
    [5,'krishna','bardoli','1234467890'],
  ] 
```

## write the direct records to student.csv


```python
with open("D:/23BCA294/sqlite3/csv/student1.csv","w", newline='') as f:
    write = csv.writer(f)
    write.writerow(['sid','sname','city','contact'])
    write.writerows(l)
```

## insert 5 records from user


```python
l1=[]
for i in range(6,11): #student IDs will start from 6 to 10
    # print (f"enter details for student{i}:")
    sname = input("enter name: ")
    city = input("enter city: ")
    contact = input("enter contact number: ")
    l1.append([i, sname, city, contact])
```

    enter name:  harsh
    enter city:  surat
    enter contact number:  1234567678
    enter name:  parth
    enter city:  vyara
    enter contact number:  1234567876
    enter name:  jenish
    enter city:  bardoli
    enter contact number:  7892940000
    enter name:  nirav
    enter city:  surat
    enter contact number:  9510837077
    enter name:  nilay
    enter city:  bardoli
    enter contact number:  4648679134
    

## append user input records to student.csv


```python
with open("D:/23BCA294/sqlite3/csv/student1.csv","a",newline='')as f:
    writer = csv.writer(f)
    writer.writerows(l1)
```

## read student.csv and print record where city is 'bardoli'


```python
with open("D:/23BCA294/sqlite3/csv/student1.csv","r") as f:
    reader = csv.DictReader(f)
    print(f"{'sid':<5} {'sname':<10} {'city':<10} {'contact':<10}")
    print("="*35)
    for row in reader:
        if row['city'].lower()  == 'bardoli':
            print(f"{row['sid']:<5} {row['sname']:<10} {row['city']:<5} {row['contact']:<10}")
```

    sid   sname      city       contact   
    ===================================
    1     om         bardoli 1234567890
    5     krishna    bardoli 1234467890
    8     jenish     bardoli 7892940000
    10    nilay      bardoli 4648679134
    


```python

```
