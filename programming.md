## Programming (14 questions)

#### 1. Write a function to calculate all possible assignment vectors of 2n users, where n users are assigned to group 0 (control), and n users are assigned to group 1 (treatment).
  - Recursive programming (sol in code)
#### 2. Given a list of tweets, determine the top 10 most used hashtags.
  - Store all the hashtags in a dictionary and get the top 10 values
#### 3. Program an algorithm to find the best approximate solution to the knapsack problem1 in a given time.
  - Greedy solution (add the best v/w as much as possible and move on to the next)
#### 4. Program an algorithm to find the best approximate solution to the travelling salesman problem2 in a given time.
  - Greedy
#### 5. You have a stream of data coming in of size n, but you don’t know what n is ahead of time. Write an algorithm that will take a random sample of k elements. Can you write one that takes O(k) space?
  - https://en.wikipedia.org/wiki/Reservoir_sampling

#### 6. Write an algorithm that can calculate the square root of a number.
  - <https://www.quora.com/What-is-the-method-to-calculate-a-square-root-by-hand?redirected_qid=664405>
#### 7. Given a list of numbers, can you return the outliers?
  - sort then select the highest and the lowest 2.5%
#### 8. When can parallelism make your algorithms run faster?  
When could it make your algorithms run slower?

  - Ask someone for more details.
  - compute in parallel when communication cost < computation cost
    - ensemble trees
    - minibatch
    - cross validation
    - forward propagation
    - minibatch
    - not suitable for online learning

#### 9. What are the di erent types of joins? What are the di er\- ences between them?
  -

#### 10. Why might a join on a subquery be slow? How might you speed it up?
  - Change the subquery to a join.
#### 11. Describe the difference between primary keys and foreign keys in a SQL database.
  - Primary keys are columns whose value combinations must be unique in a specific table so that each row can be referenced uniquely. Foreign keys are columns that references columns (often primary keys) in other tables.
#### 12. Given a COURSES table with columns course_id and course_name, a FACULTY table with columns faculty_id and faculty_name, and a COURSE_FACULTY table with columns faculty_id and course_id, how would you return a list of faculty who teach a course given the name of a course?
  - select faculty_name from faculty_id c join (select faculty_id from (select course_id from COURSES where course_name=xxx) as a join COURSE_FACULTY b on a.course_id = b.course_id) d on c.faculty_id = d.faculty_id
#### 13. Given a IMPRESSIONS table with ad_id, click (an indicator that the ad was clicked), and date, write a SQL query that will tell me the click-through-rate of each ad by month.
  - select ad_id, average(click) from IMPRESSIONS group by ad_id, month(date)
#### 14. Write a query that returns the name of each department and a count of the number of employees in each:  
EMPLOYEES containing: Emp_ID (Primary key) and Emp_Name  
EMPLOYEE_DEPT containing: Emp_ID (Foreign key) and Dept_ID (Foreign key)  
DEPTS containing: Dept_ID (Primary key) and Dept_Name

  - select Dept_Name, count(1) from DEPTS a right join EMPLOYEE_DEPT b on a.Dept_id = b.Dept_id group by Dept_Name
