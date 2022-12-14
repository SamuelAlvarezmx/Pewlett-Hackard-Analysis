# Pewlett-Hackard-Analysis

## Overview

The company Pewlett Hackard is analyzing how many employees will start to leave the company due to retirement. In this project it was created different tables in Postgres to identify the number of retiring employees in the different departments of the company. Also it was wasked to group different people that could be eligible for a mentorship program to mitigate the impact of the retiring members.

## Results

* The number of employees that are near to retirement is staggering, near 40k people are next to face retirement in the company.

* There are only two managers that are near retirement, meaning key positions in the company are not in risk of facing an abrupt change.

<img width="176" alt="retiring_titles" src="https://user-images.githubusercontent.com/104656920/185514213-8f1fdd04-2f36-484f-8bcb-85a7cb9cc448.png">

* Senior positions will be the most affected titles during the retirement wave that the company is facing, almost accounting for almost the 70% of the people leaving the company.  

<img width="176" alt="retiring_titles" src="https://user-images.githubusercontent.com/104656920/185514229-d7106e88-355b-4d3d-8153-2b798bccee5d.png">

* Development is department with most retiring positions.

<img width="240" alt="retirees_by_department" src="https://user-images.githubusercontent.com/104656920/185515649-be4bbcfc-726c-48dd-a4e8-dc779b0cf382.png">

## Summary

  * How many roles will need to be filled as the "silver tsunami" begins to make an impact?
  
   The roles that we will need to fill are 41,380. A lot of people will be leaving and it is needed to begin recruiting ASAP.
  
  * Are there enough qualified, retirement-ready employees in the departments to mentor the next generation of Pewlett Hackard employees?
   Using the following code we were able to see that there as sufficient team members in the company to face the silver tsunami that is coming. The company          has a lot of employees in each of the departments that handling the leave of many of them will for sure be a challenge but not a risk to the company.
   
Select COUNT(e.emp_no), d.dept_name

FROM employees AS e

INNER JOIN dept_emp AS de

ON e.emp_no = de.emp_no

INNER JOIN departments AS d

ON de.dept_no = d.dept_no

WHERE (de.to_date = '9999-01-01')
GROUP BY d.dept_name
ORDER BY COUNT(e.emp_no) DESC;

<img width="229" alt="Total employees" src="https://user-images.githubusercontent.com/104656920/185522413-45084d51-425e-4080-b1e7-066d7b2b32ef.png">
