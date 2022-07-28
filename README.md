# Main definitions

**Variables relative to treatment lines:**
| endakttherapronr or current_line |    Treatment line     | Variable prefix   |
| :--------------: | :-------------------: | ----------------- |
|        0         |     No Treatment|received | ed variables      |
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


**Definitions of the TTNTs (one digit after comma):**
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

m1start (*not used*) = earliest date of any treatment (chemotherapy or stem cell transplantation or surgery...)
m1start = MIN(m1tmstart, m1smstart, m1hdstart, m1sztdat, m1sztdat2, m1ktstart, m1etstart, m1opdat)
