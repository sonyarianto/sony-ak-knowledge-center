First
```
use Doctrine\DBAL\Connection;
```

Then
```
$offset = 0;
$dataPerPage = 20;

$sql    = "SELECT
           *
           FROM
           inquiries
           ORDER BY update_datetime DESC
           LIMIT ?, ?";
$results = $conn->executeQuery($sql, array($offset, $dataPerPage), array(\PDO::PARAM_INT, \PDO::PARAM_INT))->fetchAll();
```
