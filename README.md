[Question](https://leetcode.com/problems/nth-highest-salary/)

``CREATE FUNCTION getNthHighestSalary(N INT) RETURNS INT<br>
  BEGIN<br>
    DECLARE result INT;<br>
      SET result = NULL;<br>
      SET N = N - 1;<br>
      SELECT DISTINCT salary INTO result<br>
      FROM Employee ORDER BY salary DESC<br>
      LIMIT 1 OFFSET N;<br>
    RETURN (
      result
  );
END``

[Link](https://leetcode.com/problems/second-highest-salary/)
``
  SELECT DISTINCT(<br>
  SELECT DISTINCT salary FROM Employee e<br>
  ORDER BY salary DESC LIMIT 1 OFFSET 1<br>
) AS SecondHighestSalary;
``