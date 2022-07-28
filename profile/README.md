# Main definitions

## Variables relative to treatment lines

| endakttherapronr or current_line | Current treatment line | Variable prefix   |
| :--------------: | :-----------------------: | ----------------- |
|        0         |     No Treatment received | ed variables      |
|        1         |     1st Line Treatment| pt variables      |
|        2         |     2nd Line Treatment| m1 variables      |
|        3         |     3rd Line Treatment| m2 variables      |
|        4         |     4th Line Treatment| m3 variables      |
|        5         |     5th Line Treatment| m4 variables      |
|        6         |     6th Line Treatment| m5 variables      |
|        7         |     7th Line Treatment| m6 variables      |
|        8         |     8th Line Treatment| m7 variables      |
|        9         |     9th Line Treatment| m8 variables      |
|        10        |     10th Line Treatment| m9 variables      |


## Time-To-Next-Treatment (duration between the start dates of two consecutive treatments)

|      TTNT     |       Start   |        End      | 
| :-----------: | ------------- |:---------------:|
|     TTNT1     | pttmstart	    |     m1tmstart     |
|     TTNT2     | m1tmstart	    |     m2tmstart     |
|     TTNT3     | m2tmstart	    |     m3tmstart     |
|     TTNT4     | m3tmstart	    |     m4tmstart     |
|     TTNT5     | m4tmstart	    |     m5tmstart     |
|     TTNT6     | m5tmstart	    |     m6tmstart     |
|     TTNT7     | m6tmstart	    |     m7tmstart     |
|     TTNT8     | m7tmstart	    |     m8tmstart     |
|     TTNT9     | m8tmstart	    |     m9tmstart     |

**Note:**

mXstart is the earliest date of any treatment (chemotherapy or stem cell transplantation or surgery...).

Ex: TTNT2:
```python
m1start_dates = [var for var in data if var.startwith(‘m1’) if ‘ende’ in var]
m1start = min(data[m1ende_dates])

m2start_dates = [var for var in data if var.startwith(‘m2’) if ‘ende’ in var]
m2start = min(data[m2start_dates])

TTNT2 = m2start - m1start
```

## Therapy Duration: Duration between the start and end of a treatment

|      Therapy duration or TDX   |       Start   |        End      | 
| :----------------------------: | ------------- |:---------------:|
|     1st line treatment or TD1  | pttmstart	    |     ptende     |
|     2nd line treatment or TD2  | m1tmstart	    |     m1ende     |
|     3rd line treatment or TD3  | m2tmstart	    |     m2ende     |
|     4th line treatment or TD4     | m3tmstart	    |     m3ende     |
|     5th line treatment or TD5     | m4tmstart	    |     m4ende     |
|     6th line treatment or TD6     | m5tmstart	    |     m5ende     |
|     7th line treatment or TD7     | m6tmstart	    |     m6ende     |
|     8th line treatment or TD8     | m7tmstart	    |     m7ende     |
|     9th line treatment or TD9     | m8tmstart	    |     m8ende     |

mXende is the date of the latest treatment or the censor date or death date

Ex: For second line treatment:
```python
if current_line == 2: # The patient is currently in the second line treatment
	m1ende = censor_date or death_date
if current_line > 2:
	m1ende_dates = [var for var in data if var.startwith(‘m1’) if ‘ende’ in var]
	m1ende = max(data[m1ende_dates])

TD2 = m1ende - m1start
```


**Contact**

If you need support to analyse our data, please contact us at info@oncologyinformationservice.com 
