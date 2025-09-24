WITH laba_final_transaction AS
(
  SELECT 
    *,
    CASE 
      WHEN nett_sales <= 50000 THEN 0.1
      WHEN nett_sales > 50000 AND nett_sales <= 100000 THEN 0.15
      WHEN nett_sales > 100000 AND nett_sales <= 300000 THEN 0.2
      WHEN nett_sales > 300000 AND nett_sales <= 500000 THEN 0.25
      WHEN nett_sales > 500000 THEN 0.3
    END AS persentase_gross_laba
  FROM 
    (
      SELECT 
      *,
      ROUND((PRICE*(1-discount_percentage)), 2) AS nett_sales
    FROM `kimia_farma.kf_final_transaction`
    )
)
SELECT 
  laba.transaction_id,
  laba.date,
  laba.discount_percentage,
  laba.branch_id,
  ktr_cabang.branch_name,
  ktr_cabang.provinsi,
  ktr_cabang.kota,
  laba.rating AS rating_cabang,
  laba.customer_name,
  pdt.product_name,
  pdt.price AS actual_price,
  ROUND((laba.discount_percentage*100), 2) AS discount_percentage,
  ROUND((laba.persentase_gross_laba*100), 2) AS persentase_gross_laba,
  laba.nett_sales,
  ROUND((laba.nett_sales * laba.persentase_gross_laba), 2) AS nett_profit,
  laba.rating AS rating_transaksi
FROM laba_final_transaction AS laba
INNER JOIN `kimia_farma.kf_kantor_cabang` AS ktr_cabang ON laba.branch_id = ktr_cabang.branch_id
INNER JOIN `kimia_farma.kf_product` AS pdt ON laba.product_id = laba.product_id;
