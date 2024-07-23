### To insert all id_product values with the specified id_carrier_reference values, while ensuring no duplicate entries, you can use the INSERT IGNORE statement along with a SELECT query that filters out existing associations.

1. Subquery for id_carrier_reference values:

- A subquery (cr) is used to create a list of the desired id_carrier_reference values: 67, 47, 55, 51, 58, and 63.

2. CROSS JOIN:

- CROSS JOIN is used to pair each id_product from ps_product with each id_carrier_reference value.

3. LEFT JOIN:

- LEFT JOIN on ps_product_carrier ensures we can check if the combination of id_product and id_carrier_reference already exists in the ps_product_carrier table for id_shop = 1.

4. Filter out existing associations:

- The WHERE pc.id_product IS NULL condition filters out combinations that already exist in the ps_product_carrier table.

5. INSERT IGNORE:

- INSERT IGNORE ensures that duplicate entries are ignored and not inserted twice.

This query will insert the associations for all id_product values with the specified id_carrier_reference values into the ps_product_carrier table, ensuring no duplicates for id_shop = 1. If you have any more specific requirements or adjustments, please let me know!
