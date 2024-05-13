# Yohanes-Siahaan_Kimia-Farma-PBI

create table dataset_kimia_farma.datamart_kimiafarma as
SELECT DISTINCT fintrx.transaction_id, fintrx.date, fintrx.discount_percentage, fintrx.product_id, fintrx.price, fintrx.branch_id, fintrx.rating
FROM `dataset_kimia_farma.kf_final_transaction` as fintrx
left join `dataset_kimia_farma.kf_inventory` as inv
  on fintrx.branch_id = inv.branch_id
  and fintrx.product_id = inv.product_id
