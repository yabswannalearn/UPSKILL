**MAX:**  MAX()
**MIN:** MIN()

**IF: IF("RANGE" "OPERATOR", LOGICAL_TEST, TRUE, FALSE)**
example: =IF(D2:D10 < 30, "Old", "Young")

**IFS: IFS ("RANGE" "OPERATOR" "RANGE", "LOGICALSTATEMENT", "VALUE IF TRUE")**
example =IFS(E2:E10 = "Male", "BADING", E2:E10 = "Female", "Gurlarlu")

**LENGTH: LEN()**
pwede mo tong gamitin para kunyare yung phone number is 11 numbers, para malaman mo kung ilan yung numbers na nakalagay

**LEFT: LEFT("RANGE", "VALUE KUNG ILAN MA RERETURN")** 
RIGHT: RIGHT()

**DATETOTEXT**
cconvert mo yung date cell into text cell para pwede mo na gamitan ng right or left formula

**TRIM**
removes whitespace

**CONCATANATE**
pag join ng dalawang string together kahit magkahiwalay silang column. tapos pwede mo pa lagyan ng mga extra characters in between or in the end.
example
CONCATANATE(B2, " ", B2, "@gmail.com")
output:
`reinael.yabut@gmail.com`

**SUBSTITUTE**
nag ppalit ka lang ng character into a new character
may mga instances to ah
1 instances = sa una sya magpapalit
2 instances = sa pangalawa sya magppalit 
example subsitute(b1:b2, "/", "-",1) and subsitute(b1:b2, "/", "-",2)
1 instance = 2-21/25
2 instance = 2/21-25

SUM
SUMIF adds all with a if statement
SUMIFS adds all cells with ifs statement

COUNT
COUNTIF
COUNTIFS

DAYS bbilangin yung days from start date into end date (pero pag gagawin mo, sstart mo sa end date)
NETWORKDAYS ito naman bbilangin nya rin pero aalisin yung holidays and weekends, sstart mo naman to sa start date papuntang end date