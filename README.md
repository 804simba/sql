[Question](https://leetcode.com/problems/nth-highest-salary/)

``CREATE FUNCTION getNthHighestSalary(N INT) RETURNS INT
  BEGIN
    DECLARE result INT;
      SET result = NULL;
      SET N = N - 1;
      SELECT DISTINCT salary INTO result
      FROM Employee
      ORDER BY salary DESC
      LIMIT 1 OFFSET N;
    RETURN (
      result
  );
END``

[Link](https://leetcode.com/problems/second-highest-salary/)
``
  SELECT DISTINCT(
  SELECT DISTINCT salary FROM Employee e
  ORDER BY salary DESC LIMIT 1 OFFSET 1
) AS SecondHighestSalary;
``