# IBM HR Attrition — Python EDA

Exploratory Data Analysis on the IBM Watson HR dataset (1,470 employees) 
using Python. This notebook mirrors the SQL analysis done separately, 
covering attrition patterns across departments, salary bands, overtime, 
and tenure.

## Libraries Used
- Pandas
- Matplotlib  
- Seaborn

## Key Findings
- Overall attrition rate: 16.1%
- Overtime employees: 30.5% attrition — 3x higher than non-OT
- Low salary band (<3k): 28.6% attrition
- Sales department: highest attrition at 20.6%
- 79 high-risk employees identified (OT + Low Satisfaction + Low Pay)
- Danger zone: Year 0–2 employees leave the most

## Related Projects
- SQL Analysis: github.com/Amitj6124/employee-attrition-sql
