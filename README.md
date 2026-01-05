<?php
include "config.php";
$result = mysqli_query($conn, "SELECT * FROM buy_orders ORDER BY created_at DESC");
?>
<h2>All Orders</h2>
<table border="1" cellpadding="10">
<tr>
<th>Order #</th>
<th>Product</th>
<th>Price</th>
<th>Qty</th>
<th>Total</th>
<th>Location</th>
<th>Phone</th>
<th>Date</th>
</tr>
<?php while($row = mysqli_fetch_assoc($result)){ ?>
<tr>
<td><?= $row['order_number'] ?></td>
<td><?= $row['product_name'] ?></td>
<td>$<?= $row['price'] ?></td>
<td><?= $row['quantity'] ?></td>
<td>$<?= $row['total'] ?></td>
<td><?= $row['location'] ?></td>
<td><?= $row['phone'] ?></td>
<td><?= $row['created_at'] ?></td>
</tr>
<?php } ?>
</table>
