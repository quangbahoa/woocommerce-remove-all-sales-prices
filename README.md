#  WooCommerce Remove All Sales Price

### Requirements / Yêu cầu bắt buộc
- WordPress 5.0+
- WooCommerce 4.0+
- Product CSV Import Suite `https://woocommerce.com/products/product-csv-import-suite/`

### Sample file / File ví dụ
- Download [woocommerce-product-variations-export-sample.csv](https://github.com/quangbahoa/woocommerce-remove-all-sales-prices/blob/main/sample/woocommerce-product-variations-export-sample.csv)


### Step / Các bước thực hiện

##### Step 1: Export product / Xuất sản phẩm
- Go to All products click Export `wp-admin/edit.php?post_type=product`
- Xuất toàn bộ sản phẩm tại: `wp-admin/edit.php?post_type=product` 

##### Step 2: Edit CSV / Sửa file CSV
- Open csv file and remove all columns except / Mở file csv xóa các cột không cần thiết nhưng để lại các cột sau:
	+ Column `Parent`
	+ Column `parent_sku`
	+ Column `post_parent`
	+ Column `ID`
	+ Column `post_status`
	+ Column `sku`
	+ Column `regular_price`
	+ Column `sale_price`
	+ Column `meta:_sale_price_dates_from`
	+ Column `meta:_sale_price_dates_to`

- Remove all values from column `sale_price` / Xóa tất cả các giá trị tại cột `sale_price` 
- Add values to columns `meta:_sale_price_dates_from` and `meta:_sale_price_dates_to` / Thêm giá trị vào các cột `meta:_sale_price_dates_from` và `meta:_sale_price_dates_to`
- Save it / Lưu file csv lại.
- Tips: You should add value to `meta:_sale_price_dates_to` as yesterday (see sample) / Bạn nên thêm giá trị cho cột `meta:_sale_price_dates_to` là ngày hôm qua (xem file ví dụ)

##### Step 3: Merge Variations / Hợp nhất các biến thể
- Go to Product CSV Import Suite panel `wp-admin/admin.php?page=woocommerce_csv_import_suite` / Mở Product CSV Import Suite panel tại `wp-admin/admin.php?page=woocommerce_csv_import_suite`
- Click to Merge Variations button / Chọn Merge Variations
- Upload your csv file and start merge / Tải lên file csv vừa sửa và bắt đầu chạy trình hợp nhất.


### Note
- Sample way as simple products.
- You can using this tutorial to bulk change sale date.