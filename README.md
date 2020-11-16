# Thiết kế màn hình hiện trường

## Khái quát

* Cho phép user thiết kế màn hình hiện trường

## Cách vào màn hình

* Quản lý master > Danh sách hiện trường > Chọn 1 hiện trường

## Định nghĩa thuật ngữ

- Không có

## Ký hiệu sử dụng

- o : Áp dụng
- x : Không áp dụng

## 1. Định nghĩa hạng mục màn hình

### 1. Tổng quan màn hình thiết kế hiện trường

``` Hình ảnh miêu tả tổng quan màn hình thiết kế hiện trường. Mặc định chọn Home tab (ホーム) khi vào trang hoặc reload trang.```

![Layout screen](./document_images/layout_screen_active_home_tab.png)

1. Home tab (ホーム)
2. Edit tab (オブジェクトの編集)
3. Các tool sử dụng để style canvas (Home tab (ホーム))

   1. Lùi 1 bước về trạng thái chỉnh sửa trước đấy (１つ戻る)
   2. Tiến lên 1 bước trạng thái chỉnh sửa vừa lùi (１つ進む)
   3. Chọn đối tượng (選択)
   4. Thêm text (テキスト)
   5. Thêm ảnh (画像)
   6. Thêm linh kiện (アイテム)
   7. Vẽ hình (図形)
   8. Vẽ đường (線)  // edited
   9. Sao chép từ ngày khác / vị trí khác (別日/別場所 からコピー) // edited
   10. Di chuyển background (背景移動)
   11. Thay đổi background (背景設定)
   12. Cut object được chọn (カット)
   13. Copy object được chọn (コピー)
   14. Paste object được chọn (貼り付け)
   15. Thay đổi hình dạng con trỏ chuột khi di chuyển vào khu vực chỉnh sửa canvas (ポインター)
   16. Thay đổi print range (印刷範囲)
   17. In màn hình canvas (印刷)
4. Màn hình canvas
5. Màn hình print range
6. Menu navigation bottom
7. Phần thông tin của bản vẽ // edited
8. Button ẩn hiện thanh công cụ  (ツールバーを非表示にする) // edited

``` Hình ảnh miêu tả tổng quan màn hình thiết kế hiện trường khi chọn một đối tượng và click vào Edit tab (オブジェクトの編集 ).```

![Layout screen](./document_images/layout_screen_active_edit_tab.png)

1. Home tab (ホーム)
2. Edit tab (オブジェクトの編集)
3. Các tool sử dụng để style canvas (Edit home)

   1. Thay đổi màu background (塗り)
   2. Thay đổi độ trong suốt background (透明度)
   3. Thay đổi màu của line (線の色)
   4. Thay đổi kiểu line (線の種類)
   5. Thay đổi kích thước line (線の太さ)
   6. Thay đổi chiều mũi tên (矢印の向き)
   7. Thay đổi kích thước của chiều mũi tên (矢印のサイズ) ([Các trường hợp Kích thước mũi tên(矢印のサイズ) sẽ được enable hoặc disable](#11.-Các-trường-hợp-tool-arrow-size-sẽ-được-enable-hoặc-disable))
   8. Thay đổi màu của text (文字の色)
   9. Thay đổi kích thước của text (文字のサイズ)
   10. Group (グループ化) / Ungroup (グループ解除) các đối tượng hoặc các group
   11. Di chuyển đối tượng lên trên cùng (最前面へ)
   12. Di chuyển đối tượng xuống cuối cùng (最背面へ)
   13. Khóa đối tượng (ロック)
   14. Xóa đối tượng (削除)
   15. Hiển thị thông tin đối tượng (情報)
4. Màn hình canvas
5. Màn hình background print
6. Menu navigation bottom
7. Object được vẽ
8. Phần thông tin của bản vẽ // edited
9. Ẩn hiện các tool sử dụng để style canvas (ツールバーを非表示にする)

### 2. Phần dùng chung

1. Các quyền được thực hiện khi đăng nhập vào hệ thống

   - Admin trụ sở chính
   - Admin chi nhánh
   - Quản đốc hiện trường
   - Admin công ty hợp tác
   - Thợ cả
   - Thợ thủ công
2. Các trạng thái khi thao tác với tool:

   #### 1. Trạng thái cho phép chọn


   * ```Hình ảnh dưới đây thể hiện trạng thái cho phép chọn của đối tượng```

     ![Object status may select](document_images/object_status_may_select.png)

   #### 2. Trạng thái không thể thao tác

   * ``` Hình ảnh miêu tả trạng thái không thể thao tác của đối tượng```

     ![Object status has been disabled](document_images/object_status_disabled.png)

   #### 3. Trạng thái khi di chuyển con trỏ chuột vào đối tượng:

   * ``` Hình ảnh miêu tả trạng khi di chuyển con trỏ chuột vào đối tượng```

     ![Object status hover](document_images/object_status_hover.png)

   #### 4. Trạng thái đã được chọn

   * ```Hình ảnh miêu tả trạng thái đã được chọn của đối tượng```

     ![Object status is selected](document_images/object_status_selected.png)

   #### 5. Trạng thái khi click vào đối tượng

   * ```Hình ảnh miêu tả trạng thái khi được click của đối tượng```

     ![Object status is clicked](document_images/object_status_clicked.png)

   #### 6. Trạng thái khi di chuyển con trỏ chuột vào các lựa chọn của droplist

   * ```Hình ảnh miêu tả trạng thái khi user click chọn tool vẽ. Sau đó di chuyển con trỏ chuột vào droplist```

     ![Drop-down expansion status](document_images/drop-down_expanstion_status.png)
3. 9 tool sử dụng để style cho đối tượng:

   #### Hình ảnh miêu tả 9 tool sử dụng để style cho đối tượng

   ![All tool styles](document_images/all_tool_styles_active.png)


   1. Thay đổi màu background (塗り)
   2. Thay đổi độ trong suốt background (透明度)
   3. Thay đổi màu của line (線の色)
   4. Thay đổi kiểu line (線の種類)
   5. Thay đổi kích thước line (線の太さ)
   6. Thay đổi chiều mũi tên (矢印の向き)
   7. Thay đổi kích thước của chiều mũi tên (矢印のサイズ) ([Các trường hợp  Kích thước mũi tên(矢印のサイズ) sẽ được enable hoặc disable](#11.-Các-trường-hợp-tool-arrow-size-sẽ-được-enable-hoặc-disable))
   8. Thay đổi màu của text (文字の色)
   9. Thay đổi kích thước của text (文字のサイズ)

### 3. Nhóm tool để style cho đối tượng:

* #### 1. Nhóm tool để style cho đối tượng là text bao gồm:

  1. Miêu tả dưới dạng hình ảnh

     ![Tool styles applied to text](document_images/tool_styles_applied_to_text.png)

     1. Thay đổi màu background (塗り)
     2. Thay đổi độ trong suốt của màu background (透明度)
     3. Thay đổi màu của text (文字の色)
     4. Thay đổi kích thước của font chữ (文字のサイズ)
  2. Miêu tả dưới dạng bảng


     | Style áp  dụng | Màu background | Độ trong suốt background | Màu của line | Kiểu line | Kích thước line | Kiểu mũi tên | Kích thước mũi tên | Màu của chữ | Kích thước của chữ |
     | - | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
     | Áp dụng | o | o | x | x | x | x | x | o | o |
* #### 2. Nhóm tool để style cho đối tượng là hình tròn, hình chữ nhật, hình đa giác:

  1. Miêu tả dưới dạng hình ảnh

     ![Tool styles applied to tool circle](document_images/tool_styles_applied_to_tool_shape.png)

     1. Thay đổi màu background (塗り)
     2. Thay đổi độ trong suốt của màu background (透明度)
     3. Thay đổi màu của line (線の色)
     4. Thay đổi kiểu line (線の種類)
     5. Thay đổi kích thước line (線の太さ)
  2. Miêu tả dưới dạng bảng


     | Style áp  dụng | Màu background | Độ trong suốt background | Màu của line | Kiểu line | Kích thước line | Kiểu mũi tên | Kích thước mũi tên | Màu của chữ | Kích thước của chữ |
     | - | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
     | Áp dụng | o | o | o | o | o | x | x | x | x |
* #### 3. Nhóm tool để style cho đối tượng là đường thẳng bao gồm:

  1. Miêu tả dưới dạng hình ảnh

     ![Tool styles applied tool line](document_images/tool_styles_applied_tool_line.png)

     1. Thay đổi màu của line (線の色)
     2. Thay đổi kiểu line (線の種類)
     3. Thay đổi kích thước line (線の太さ)
     4. Thay đổi chiều mũi tên (矢印の向き)
     5. Thay đổi kích thước của chiều mũi tên (矢印のサイズ) ([Các trường hợp  Kích thước mũi tên (矢印のサイズ) sẽ được enable hoặc disable](#11.-Các-trường-hợp-tool-arrow-size-sẽ-được-enable-hoặc-disable))
  2. Miêu tả dưới dạng bảng


     | Style áp  dụng | Màu background | Độ trong suốt background | Màu của line | Kiểu line | Kích thước line | Kiểu mũi tên | Kích thước mũi tên | Màu của chữ | Kích thước của chữ |
     | - | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
     | Áp dụng | x | x | o | o | o | o | o | x | x |
* #### 4. Nhóm tool để style cho đối tượng là hình nhiều đường(polyline) bao gồm:

  1. Miêu tả dưới dạng hình ảnh

     ![Tool styles applied tool polyline](document_images/tool_styles_applied_tool_polyline.png)

     1. Thay đổi màu background (塗り)
     2. Thay đổi độ trong suốt background (透明度)
     3. Thay đổi màu của line (線の色)
     4. Thay đổi kiểu line (線の種類)
     5. Thay đổi kích thước line (線の太さ)
     6. Thay đổi chiều mũi tên (矢印の向き)
     7. Thay đổi kích thước của chiều mũi tên (矢印のサイズ) ([Các trường hợp  Kích thước mũi tên (矢印のサイズ) sẽ được enable hoặc disable](#11.-Các-trường-hợp-tool-arrow-size-sẽ-được-enable-hoặc-disable))
  2. Miêu tả dưới dạng bảng


     | Style áp  dụng | Màu background | Độ trong suốt background | Màu của line | Kiểu line | Kích thước line | Kiểu mũi tên | Kích thước mũi tên | Màu của chữ | Kích thước của chữ |
     | - | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
     | Áp dụng | o | o | o | o | o | o | o | x | x |
* #### 5. Nhóm tool để style cho đối tượng là đường kẻ tự do bao gồm:

  1. Miêu tả dưới dạng hình ảnh

     ![Tool styles applied tool freehand](./document_images/tool_styles_applied_tool_freehand.png)

     1. Thay đổi màu của line (線の色)
     2. Thay đổi kiểu line (線の種類)
     3. Thay đổi kích thước line (線の太さ)
  2. Miêu tả dưới dạng bảng


     | Style áp  dụng | Màu background | Độ trong suốt background | Màu của line | Kiểu line | Kích thước line | Kiểu mũi tên | Kích thước mũi tên | Màu của chữ | Kích thước của chữ |
     | - | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
     | Áp dụng | x | x | o | o | o | x | x | x | x |
* #### 6. Đối tượng là linh kiện hoặc hình ảnh

  1. Miêu tả dưới dạng hình ảnh

     ![All tool styles will be disabled](document_images/all_tool_styles_disabled.png)

     ``` * Đây là trường hợp đặc biệt:  Nếu đối tượng là linh kiện hoặc hình ảnh thì sẽ không thể áp dụng bất cứ style nào lên đối tượng.```

### 4. Khi vào màn hình canvas hoặc reload trang

1. Canvas sẽ tự động căn giữa màn hình, ẩn 2 navigation bar bên trái
2. Tự động chọn Di chuyển background (背景移動), chuyển tool sang trạng thái đã được chọn

   ``` Hình ảnh miêu tả Di chuyển background (背景移動) được chọn khi vào màn hình canvas hoặc reload trang```

   ![Tool pan active](document_images/tool_pan_active.png)
3. Mặc định hiển thị ở chế độ toàn màn hình
4. Disable các tool:

   + Lùi 1 bước về trạng thái chỉnh sửa trước đấy (１つ戻る), Tiến lên 1 bước trạng thái chỉnh sửa vừa lùi (１つ進む)

     ![Disable tool redo and go foward](document_images/disable_tool_redo_and_go_foward.png)
   + Cut (カット) , Copy (コピー), Paste (貼り付け)

     ![Disable tool cut, copy, paste](document_images/disable_tool_cut_copy_paste.png)
5. Active tool home bar(ホーム), disable tool edit bar(オブジェクトの編集)

   ![Active tool Home tab (ホーム) and disable tool Edit tab (オブジェクトの編集 )](document_images/active_home_tab.png)

### 5. Các cách để kết thúc khi vẽ 1 đối tượng

Sử dụng 1 trong cách cách dưới đây:

1. Click đúp vào đối tượng đang vẽ
2. Ấn nút `Space` trên bàn phím
3. Click vào tool chọn object

   ```Hình ảnh miêu tả khi tool object được chọn```

   ![Click tool object](./document_images/object_selection_status.png)

### 6. Các trường hợp khi nào 1 tool style sẽ bị disable

1. Khi không thể áp dụng style cho object đang được chọn
2. Khi không thể áp dụng cho bất kỳ object nào trong trường hợp chọn nhiều object
3. Khi chọn tool group (グループ化)
4. Khi object bị lock

### 7. Các trường hợp tool copy, cut và paste bị disable

1. Dùng chung

   1. Mặc định tool copy/cut/paste sẽ bị disable trong trường hợp

      1.1 Khi vào màn hình canvas

      1.2 Khi reload trang
   2. Các trường hợp tool copy/cut/paste bị disable

      2.1 Màn hình canvas không có object nào

      2.2 Không chọn bất cứ object nào
2. Bổ sung

   1. Trường hợp tool paste sẽ bị disable
      1. Khi không có object nào được copy hoặc cut

### 8. Các tool sẽ bị disable khi thực hiện chức năng lock object

1. Cut (カット), Paste (貼り付け)

   ```Hình ảnh miêu tả tool Cut (カット) và Paste (貼り付け) bị disable```

   ![Disable tool cut and Paste](./document_images/disable_tool_cut_and_paste.png)
2. Tất cả các tool style

   ``` Hình ảnh miêu tả tất cả tool style bị disable```

   ![Disable all tool styles](./document_images/all_tool_styles_disabled.png)
3. Tool group (グループ化)

   ```Hình ảnh miêu tả tool group (グループ化) bị disable```

   ![Disable tool group (グループ化)](./document_images/disable_tool_group.png)
4. Tool Ungroup(グループ解除)

   ``` Hình ảnh miêu tả tool Ungroup (グループ解除) bị disable```

   ![Disable Tool Ungroup(グループ解除)](./document_images/disable_tool_ungroup.png)
5. Tool Di chuyển đối tượng lên trên cùng (最前面へ), Di chuyển đối tượng xuống cuối cùng (最背面へ)

   ``` Hình ảnh miêu tả tool Di chuyển đối tượng lên trên cùng (最前面へ) và Di chuyển đối tượng xuống cuối cùng (最背面へ) bị disable```

   ![Disable tool move front (最前面へ) and move back (最背面へ)](./document_images/disable_tool_move_front_and_move_back.png)
6. Tool xóa object (削除)

   ``` Hình ảnh miêu tả tool xóa object (削除) bị disable```

   ![Disable tool delete object](./document_images/disable_tool_delete_object.png)

### 9. Các tool sẽ bị disable khi thực hiện chức năng group hoặc ungroup

1. Tool group (グループ化)

   * Disable tất cả các tool style ([9 tool sử dụng để style cho đối tượng](#Hình-ảnh-miêu-tả-9-tool-sử-dụng-để-style-cho-đối-tượng))
2. Tool Ungroup(グループ解除)

   - Khi chọn ungroup sẽ tự động chuyển về Home tab (ホーム) và disable Edit tab (オブジェクトの編集 )

   ``` Hình ảnh miêu tả Edit tab (オブジェクトの編集 ) bị disable```

   ![Disable tool delete object](./document_images/disable_edit_tab.png)

### 10. Các trường hợp tool kích thước của chiều mũi tên sẽ được enable hoặc disable

> Trạng thái enable và disable của tool `'Thay đổi kích thước của chiều mũi tên (矢印のサイズ)'` sẽ phụ thuộc vào giá trị của tool `'Thay đổi chiều mũi tên (矢印の向き)'`

1. Trường hợp tool `'Thay đổi chiều mũi tên (矢印の向き)'` có giá trị là `なし` thì sẽ disable tool `'Thay đổi kích thước của chiều mũi tên (矢印のサイズ)'`

   ``` Hình ảnh miêu tả Kích thước mũi tên(矢印のサイズ) bị disable khi giá trị của tool 'Thay đổi chiều mũi tên (矢印の向き)' có giá trị là なし```

   ![Disable Kích thước mũi tên(矢印のサイズ)](./document_images/disable_tool_arrow_size.png)
2. Khi giá trị của tool `'Thay đổi chiều mũi tên (矢印の向き)'` khác `なし` thì sẽ enable tool `'Thay đổi kích thước của chiều mũi tên (矢印のサイズ)'`

   ``` Hình ảnh miêu tả tool kích thước của chiều mũi tên được enable khi giá trị của tool 'Thay đổi chiều mũi tên (矢印の向き)' có giá trị khác なし```

   ```Ví dụ 1: ```

   ![The value of arrow size is 始点](document_images/enable_tool_arrow_size_2.png)

   ```Ví dụ 2:```

   ![The value of arrow size is 両端](./document_images/enable_tool_arrow_size_3.png)

### 11. Đóng mở toolbar (ツールバーを非表示にする)

* Cho phép ẩn hiện các tool sử dụng để style canvas ở Home tab (ホーム) hoặc Edit tab (オブジェクトの編集 )

  * Trường hợp user click vào link `ツールバーを非表示にする` sẽ ẩn các tool sử dụng để style canvas ở tab đang active. Sau khi click, text sẽ chuyển thành `ツールバーを表示する`

  ``` Hình ảnh miêu tả các tool sử dụng để style canvas ở Home tab (ホーム) đã bị ẩn khi click link 'ツールバーを非表示にする'```

  ![Layout screen](./document_images/hide_tool_bar.png)

  ``` Hình ảnh miêu tả tool bả ở Home tab (ホーム) được hiển thị sau khi click link 'ツールバーを表示する'```

  * Trường hợp user click vào link `ツールバーを表示する` sẽ hiển thị các tool sử dụng để style canvas ở tab đang active. Sau khi click, text sẽ chuyển thành `ツールバーを非表示にする`

  ![Layout screen](./document_images/show_tool_bar.png)

### 12. Các trạng thái của tool tab

```Hình miêu tả các trạng thái của tool tab```

![Layout screen](./document_images/tool_tab_statuses.png)

1. Trạng thái bình thường (通常)
2. Trạng thái không hoạt động(Vô hiệu hóa) (非活性)
3. Trạng thái không hoạt động + di chuột qua (非活性+マウスオーバー)
4. Trạng thái khi di chuột qua(マウスオーバー)
5. Trạng thái đã chọn(選択中)

## 2. Thiết lập kế hoạch sắp xếp hiện trường

1. Thiết lập vị trí (作業場所) và ngày sử dụng (作業日)

   > Khái quát chức năng:
   >

   + Cho phép tạo nhiều kế hoạch sắp xếp trên 1 hiện trường
   + Cho phép tạo kế hoạch sắp xếp theo từng ngày(作業日) và vị trí(作業場所)

   ![Layout screen](./document_images/setting_place_and_time.png)

   ```Bảng dưới đây thể hiện những tài khoản được phép thao tác với chức năng:```


   | Kiểu tài khoản | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
   | - | :-: | :-: | :-: | :-: | :-: | :-: |
   | Quyền hạn | o | o | o | o | o | x |
2. Thiết lập ảnh nền

   > Khái quát chức năng: Cho phép thêm hoặc gỡ ảnh, file background của canvas trong kế hoạch sắp xếp hiện trường.
   >

   + Ảnh và file PDF không được quá 15MB.
   + Modal cropbox có kích thước là 800px x 560px
   + Vùng chọn crop có kích thước là: 560px x 396px

     1. Sử dụng file ảnh

        + Định dạng file cho phép: ```PNG, JPEG, JPG, GIF```
     2. Sử dụng file pdf

        + Định dạng file cho phép: ```PDF```
   + Các bước thực hiện:

     1. Sau khi user chọn ảnh/file PDF sẽ hiển thị modal để crop ảnh:

        * User có thể thay đổi kích thước cắt bằng cách kéo vùng chọn để crop.
        * Hình ảnh sẽ tự động resize theo chiều ngang hoặc chiều dọc. Phụ thuộc vào tỉ lệ hình ảnh đó so với kích thước vùng chọn crop.

        ```Hình ảnh miêu tả màn hình crop ảnh sau khi upload file background```

        ![Modal crop background file](document_images/modal_crop_backgorund_file.png)

        1. Khung giới hạn crop
        2. Khung chọn crop
     2. Sau khi user crop xong ảnh, ấn nút `決定` để  chọn ảnh/file PDF làm background

        * Phần sáng màu là phần được chọn làm background. Phần không được chọn sẽ hiển thị tối màu.
        * Background lúc này sẽ được resize theo kích thước vùng chọn.
     3. User có thể chọn ảnh khác hoặc hủy bỏ thao tác bằng cách nhấn `キャンセル`

## 3. Vẽ canvas trong kế hoạch sắp xếp hiện trường

1. Di chuyển canvas

   > Khái quát chức năng: Cho phép di chuyển canvas của kế hoạch sắp xếp hiện trường trong màn hình
   >

   ```Bảng dưới đây thể hiện những tài khoản được phép thao tác với chức năng:```


   | Kiểu tài khoản | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
   | - | :-: | :-: | :-: | :-: | :-: | :-: |
   | Quyền hạn | o | o | o | o | o | x |
2. Chọn object

   1. Với trường hợp chọn 1 object

      + Tool style nào không thể áp dụng được cho object sẽ bị disable.([Các tool style áp dụng tương với từng loại đối tượng](#4.-Các-nhóm-style-có-thể-áp-dụng-cho-các-đối-tượng:))
   2. Với trường hợp chọn nhiều object

      + Chỉ enable những style nào cho phép áp dụng cho đối tượng bên trong list object được chọn.([Các tool style áp dụng tương với từng loại đối tượng](#4.-Các-nhóm-style-có-thể-áp-dụng-cho-các-đối-tượng:))
   3. Với trường hợp chọn tất cả object

      + Disable tool Di chuyển đối tượng lên trên cùng (最前面へ), Di chuyển đối tượng xuống cuối cùng (最背面へ)

        ``` Hình ảnh miêu tả tool Di chuyển đối tượng lên trên cùng (最前面へ) và Di chuyển đối tượng xuống cuối cùng (最背面へ) bị disable```

        ![Disable tool Di chuyển đối tượng lên trên cùng (最前面へ), move-Di chuyển đối tượng xuống cuối cùng (最背面へ)](./document_images/disable_tool_move_front_and_move_back.png)
   4. Với trường hợp chọn 1 group

      - Disable tất cả các tool style ([9 tool sử dụng để style cho đối tượng](#Hình-ảnh-miêu-tả-9-tool-sử-dụng-để-style-cho-đối-tượng))
   5. Trường hợp chọn nhiều group

      - Disable tất cả các tool style ([9 tool sử dụng để style cho đối tượng](#Hình-ảnh-miêu-tả-9-tool-sử-dụng-để-style-cho-đối-tượng))
   6. Sau khi chọn 1 object hoặc 1 group

      - Active Edit tab (オブジェクトの編集)
      - Chuyển tool chọn object (選択) sang trạng thái đã được chọn

        ``` Hình ảnh miêu tả trạng thái active của Edit tab (オブジェクトの編集). Tool object chuyển sang trạng thái đã được chọn```

        ![Active Edit tab, Object selection status](./document_images/object_selection_status.png)
      - Active tool Cut (カット), Copy (コピー)

        ``` Hình ảnh miêu tả trạng thái active của tool Cut (カット) và Copy (コピー)```

        ![Active tool cut and copy](./document_images/active_tool_cut_and_copy.png)
3. Vẽ hình

   > Khái quát chức năng: Cho phép vẽ hình(hình tròn, hình chữ nhật, hình đa giác) trên canvas.
   >

   1. Hình tròn (円)

      ``` Hình ảnh miêu tả các loại hình khi click vào tool vẽ hình```

      ![Active tool cut and copy](./document_images/droplist_tool_shape.png)

      * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


        | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
        | - | :-: | :-: | :-: | :-: | :-: | :-: |
        | Quyền hạn | o | o | o | o | o | x |
      * Các tool style sẽ được enable và disable với đối tượng là hình tròn ([Tìm hiểu các tool style áp dụng và không áp dụng với đối tượng là hình tròn](#2.-Nhóm-các-style-áp-dụng-cho-đối-tượng-là-hình-tròn,-hình-chữ-nhật,-hình-đa-giác:)).
      * Các cách để kết thúc khi vẽ hình tròn([Các cách để kết thúc khi vẽ 1 đối tượng](#6.-Các-cách-để-kết-thúc-khi-vẽ-1-đối-tượng))
      * Disable tool group (グループ化)

        ``` Hình ảnh miêu tả tool group (グループ化) bị disable```

        ![Disable tool group](./document_images/disable_tool_group.png)
   2. Hình chữ nhật (四角)

      ``` Hình ảnh miêu tả các loại hình khi click vào tool vẽ hình```

      ![Active tool cut and copy](./document_images/droplist_tool_shape.png)

      * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


        | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
        | - | :-: | :-: | :-: | :-: | :-: | :-: |
        | Quyền hạn | o | o | o | o | o | x |
      * Các tool style sẽ được enable và disable với đối tượng là hình chữ nhật ([Tìm hiểu các tool style áp dụng và không áp dụng với đối tượng là chữ nhật](#2.-Nhóm-các-style-áp-dụng-cho-đối-tượng-là-hình-tròn,-hình-chữ-nhật,-hình-đa-giác:)).
      * Các cách để kết thúc khi vẽ hình chữ nhật([Các cách để kết thúc khi vẽ 1 đối tượng](#6.-Các-cách-để-kết-thúc-khi-vẽ-1-đối-tượng))
      * Disable tool group (グループ化)

        ``` Hình ảnh miêu tả tool group (グループ化) bị disable```

        ![Disable tool group (グループ化)](./document_images/disable_tool_group.png)
   3. Hình đa giác (多角形)

      ``` Hình ảnh miêu tả các loại hình khi click vào tool vẽ hình```

      ![Active tool cut and copy](./document_images/droplist_tool_shape.png)

      * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


        | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
        | - | :-: | :-: | :-: | :-: | :-: | :-: |
        | Quyền hạn | o | o | o | o | o | x |
      * Các tool style sẽ được enable và disable với đối tượng là hình đa giác ([Tìm hiểu các tool style áp dụng và không áp dụng với đối tượng là hình đa giác](#2.-Nhóm-các-style-áp-dụng-cho-đối-tượng-là-hình-tròn,-hình-chữ-nhật,-hình-đa-giác:)).
      * Các cách để kết thúc khi vẽ hình đa giác([Các cách để kết thúc khi vẽ 1 đối tượng](#6.-Các-cách-để-kết-thúc-khi-vẽ-1-đối-tượng))
      * User có thể thay đổi các đường thẳng của đối tượng bằng cách ấn double click vào đối tượng. Sau có chọn 1 điểm và kéo để thay đổi giá trị của đường thẳng.

        ``` Hình ảnh miêu tả khi user ấn double click vào đối tượng là hình đa giác```

        ![Active tool cut and copy](./document_images/double_click_polygon.png)
      * Disable tool group (グループ化)

        ``` Hình ảnh miêu tả tool group (グループ化) bị disable```

        ![Disable tool group (グループ化)](./document_images/disable_tool_group.png)
4. Vẽ line

   * Đường thẳng, đường thẳng gấp khúc (được cố định bằng cách vừa ấn phím `Shift`) // edited

   1. Vẽ đường thẳng (直線)

      ``` Hình ảnh miêu tả các loại đường thẳng khi click vào tool vẽ line```

      ![Active tool cut and copy](./document_images/droplist_tool_line.png)

      * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


        | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
        | - | :-: | :-: | :-: | :-: | :-: | :-: |
        | Quyền hạn | o | o | o | o | o | x |
      * Các tool style sẽ được enable và disable với đối tượng là đường thẳng ([Tìm hiểu các tool style áp dụng và không áp dụng với đối tượng là đường thẳng](#3-Nhóm-các-style-áp-dụng-cho-đối-tượng-là-đường-thẳng-bao-gồm:)).
      * Các cách để kết thúc khi vẽ hình đa giác([Các cách để kết thúc khi vẽ 1 đối tượng](#6.-Các-cách-để-kết-thúc-khi-vẽ-1-đối-tượng))
      * Disable tool group (グループ化)

        ``` Hình ảnh miêu tả tool group (グループ化) bị disable```

        ![Disable tool group (グループ化)](./document_images/disable_tool_group.png)
   2. Vẽ đường thẳng gấp khúc (折れ線) // edited

      ``` Hình ảnh miêu tả các loại đường thẳng khi click vào tool vẽ line```

      ![Active tool cut and copy](./document_images/droplist_tool_line.png)

      * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


        | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
        | - | :-: | :-: | :-: | :-: | :-: | :-: |
        | Quyền hạn | o | o | o | o | o | x |
      * Các tool style sẽ được enable và disable với đối tượng là đường thẳng đa giác([Tìm hiểu các tool style áp dụng và không áp dụng với đối tượng là đường thẳng đa giác](#4-Nhóm-các-style-áp-dụng-cho-đối-tượng-là-đường-thẳng-đa-giác-bao-gồm:)).
      * Các cách để kết thúc khi vẽ hình đa giác([Các cách để kết thúc khi vẽ 1 đối tượng](#6.-Các-cách-để-kết-thúc-khi-vẽ-1-đối-tượng))
      * User có thể thay đổi các đường thẳng của đối tượng bằng cách ấn double click vào đối tượng. Sau có chọn 1 điểm và kéo để thay đổivị trí của điểm tương ứng. //edited

        ``` Hình ảnh miêu tả khi user ấn double click vào đối tượng là đường thẳng đa giác```

        ![Active tool cut and copy](./document_images/double_click_polyline.png)
      * Disable tool group (グループ化)

        ``` Hình ảnh miêu tả tool group (グループ化) bị disable```

        ![Disable tool group (グループ化)](./document_images/disable_tool_group.png)
   3. Vẽ đường kẻ tự do (自由線)

      ``` Hình ảnh miêu tả các loại đường thẳng khi click vào tool vẽ line```

      ![Active tool cut and copy](./document_images/droplist_tool_line.png)

      * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


        | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
        | - | :-: | :-: | :-: | :-: | :-: | :-: |
        | Quyền hạn | o | o | o | o | o | x |
      * Các tool style sẽ được enable và disable với đối tượng là đường kẻ tự do([Tìm hiểu các tool style áp dụng và không áp dụng với đối tượng là đường kẻ tự do](#5-Nhóm-các-style-áp-dụng-cho-đối-tượng-là-đường-kẻ-tự-do-bao-gồm:)).
      * Các cách để kết thúc khi vẽ hình đa giác([Các cách để kết thúc khi vẽ 1 đối tượng](#6.-Các-cách-để-kết-thúc-khi-vẽ-1-đối-tượng))
      * Disable tool group (グループ化)

        ``` Hình ảnh miêu tả tool group (グループ化) bị disable```

        ![Disable tool group (グループ化)](./document_images/disable_tool_group.png)
5. Thêm text (テキスト)

   > Khái quát chức năng: Cho phép vẽ text tùy ý trên canvas
   >

   * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


     | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
     | - | :-: | :-: | :-: | :-: | :-: | :-: |
     | Quyền hạn | o | o | o | o | o | x |
   * Các tool style sẽ được enable và disable với đối tượng là text ([Tìm hiểu các tool style áp dụng và không áp dụng với đối tượng là text](#1-Nhóm-các-style-áp-dụng-cho-đối-tượng-là-text-bao-gồm:)).
   * Disable tool group (グループ化)

     ``` Hình ảnh miêu tả tool group (グループ化) bị disable```

     ![Disable tool group (グループ化)](./document_images/disable_tool_group.png)
   * Chỉnh sửa text: Có thể sửa text đã vẽ bằng cách double click lên text muốn chỉnh sửa, click bất kì vị trí nào bên ngoài để kết thúc chỉnh sửa. // added
6. Thêm ảnh (画像)

   > Khái quát chức năng: Cho phép thêm ảnh tùy ý trên canvas
   >

   * Định dạng file cho phép : `PNG, JPEG, JPG, GIF`
   * File upload tối đa là 15Mb
   * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


     | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
     | - | :-: | :-: | :-: | :-: | :-: | :-: |
     | Quyền hạn | o | o | o | o | o | x |
   * Tất cả các tool style sẽ bị disable với đối tượng là ảnh ([Tìm hiểu các tool style không được áp dụng với đối tượng là ảnh](#6-Đối-tượng-là-linh-kiện-hoặc-hình-ảnh)).
   * Disable tool group (グループ化)

     ``` Hình ảnh miêu tả tool group (グループ化) bị disable```

     ![Disable tool group (グループ化)](./document_images/disable_tool_group.png)
7. Thêm linh kiện (アイテム)

   > Khái quát chức năng: Cho phép chọn loại linh kiện, hiển thị ảnh linh kiện tương ứng
   >

   * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


     | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
     | - | :-: | :-: | :-: | :-: | :-: | :-: |
     | Quyền hạn | o | o | o | x | x | x |
   * Tất cả các tool style sẽ bị disable với đối tượng là linh kiện ([Tìm hiểu các tool style không được áp dụng với đối tượng là linh kiện](#6-Đối-tượng-là-linh-kiện-hoặc-hình-ảnh)).
   * Disable tool group (グループ化)

     ``` Hình ảnh miêu tả tool group (グループ化) bị disable```

     ![Disable tool group (グループ化)](./document_images/disable_tool_group.png)
   * Lưu giá trị scale % hiển thị linh kiện

     * Cho phép cập nhật giá trị % scale hiển thị linh kiện
       * Mức scale nhỏ nhất là 10%
       * Mức scale lớn nhất là 200% // edited

     ~~~
     - Mặc định giá trị scale hiển thị là 100%
     - Nếu thay đổi % scale sẽ được update realtine. Khi reload lại trang sẽ hiển thị theo giá trị % scale vừa update.
     ~~~
8. Copy canvas từ vị trí/ ngày khác (別日/別場所 からコピー)

   > Khái quát chức năng: Copy canvas từ vị trí/ ngày khác vào màn hình canvas hiện tại.
   >

   * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


     | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
     | - | :-: | :-: | :-: | :-: | :-: | :-: |
     | Quyền hạn | o | o | o | x | x | x |
9. Tự động chọn object sau khi vẽ

   * Sau khi thêm ảnh, linh kiện, text, vẽ hình và vẽ line sẽ tự động chuyển sang tool chọn object và chuyển trạng thái thành đã được chọn với object vừa vẽ. Đồng thời sẽ kích hoạt Edit tab (オブジェクトの編集)

     ```Hình ảnh dưới đây miêu tả tool chọn object đã được chọn```

     ![Active tool select](./document_images/automatically_select_the_object.png)

     1. Tool chọn object đã được chọn
     2. Active tool Edit tab (オブジェクトの編集 )
   * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


     | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
     | - | :-: | :-: | :-: | :-: | :-: | :-: |
     | Quyền hạn | o | o | o | o | o | o |

## 4. Bottom Navigation  // edited

1. Thiết lập zoom // edited

   > Khái quát chức năng: Cho phép phóng to, thu nhỏ canvas // edited
   >

   * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


     | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
     | - | :-: | :-: | :-: | :-: | :-: | :-: |
     | Quyền hạn | o | o | o | o | o | x |
   * Mức phóng nhỏ nhất là 25%
   * Mức phóng lớn nhất là 800%

   ~~~
   NOTE: Disable button thu nhỏ khi độ phóng là 25%
   ~~~

   ``` Hình ảnh miêu tả nút thu nhỏ bị disable```

   ![Disable zoomdown button](./document_images/disable_zoomdown_button.png)

   ~~~
   NOTE: Disable button phóng to khi độ phóng là 800%
   ~~~

   ``` Hình ảnh miêu tả nút phóng to bị disable```

   ![Disable zoomin button](./document_images/disable_zoom_in_button.png)
    // deleted
2. Thiết lập print range (印刷範囲)

   > Khái quát chức năng: Cho phép thay đổi kích thước print range, set về trạng thái mặc định
   >

   * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


     | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
     | - | :-: | :-: | :-: | :-: | :-: | :-: |
     | Quyền hạn | o | o | o | o | o | x |
3. Hiển thị thông tin object của canvas

   > Khái quát chức năng: Hiển thị thông tin tạo object/ update/ trạng thái lock
   >

   * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


     | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
     | - | :-: | :-: | :-: | :-: | :-: | :-: |
     | Quyền hạn | o | o | o | o | o | x |
4. Chia màn hình (画面分割)

   > Khái quát chức năng: Cho phép chia nhỏ màn hình, hiển thị canvas của ngày sử dụng và các địa điểm khác
   >

   ~~~
   - Mặc định khi vào màn hình thiết kế hiện trường sẽ hiển thị chế độ 1 màn hình
   ~~~

   * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


     | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
     | - | :-: | :-: | :-: | :-: | :-: | :-: |
     | Quyền hạn | o | o | o | o | o | x |

   1. Trường hợp 1 màn hình

      * Menu navbar bottom hiển thị các option: chia màn hình, button zoom in/out, select độ phóng

        ```Hình ảnh miêu tả navbar bottom ở chế độ 1 màn hình```

        ![Navbar bottom in case of 1 screen](./document_images/navbar_bottom_1_screen.png)
   2. Trường hợp nhiều hơn 1 màn hình

      * Disable tất cả các tool trên Home tab (ホーム) và Edit tab (オブジェクトの編集 ), ngoại trừ tool in và mode pointer vẫn cho phép thao tác bình thường

        ```Hình ảnh miêu tả tất cả các tool ở Home tab (ホーム) sẽ bị disable ngoại trừ tool in (印刷) và tool pointer ((ポインター)) vẫn cho phép thao tác bình thường.  Đồng thời Edit tab (オブジェクトの編集 ) bị disable ```

        ![Disable tools in case of multiple screen](./document_images/disable_tools_multiple_screen.png)
      * Menu navbar góc phải dưới màn hình chuyển các option zoom in/out sang option sắp xếp theo vị trí và theo ngày. Thêm button tiến, lùi theo option sắp xếp theo vị trí và theo ngày

        ```Hình ảnh miêu tả navbar bottom ở chế độ nhiều hơn 1 màn hình```

        ![Navbar bottom in case of multiple screen](./document_images/navbar_bottom_multiple_screen.png)

        ``` Hình ảnh miêu tả chế độ nhiều màn hình```

        ![Multiple screen](./document_images/multiple_screen.png)
5. Thiết lập thứ tự hiển thị

   > Khái quát chức năng: Sau khi chia nhỏ màn hình, cho phép sort theo ngày sử dụng, vị trí, lùi/tiến theo ngày sử dụng hoặc vị trí

   * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


     | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
     | - | :-: | :-: | :-: | :-: | :-: | :-: |
     | Quyền hạn | o | o | o | o | o | x |

## 5. Chỉnh sửa canvas trong kế hoạch sắp xếp hiện trường

1. Các tool style

   1.1 Thay đổi màu background (塗り)

   > Khái quát chức năng: Thay đổi màu background của object
   >

   * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


     | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
     | - | :-: | :-: | :-: | :-: | :-: | :-: |
     | Quyền hạn | o | o | o | o | o | x |
   * Kiểu đối tượng được áp dụng


     | Kiểu đối tượng | Hình tròn | Hình chữ nhật | Hình đa giác | Đường thẳng | Đường thẳng đa giác | Vẽ đường kẻ tự do | Text |
     | - | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
     | Áp dụng | o | o | o | x | o | x | o |
   * Tìm hiểu trường hợp tool thay đổi màu background sẽ bị disable([Trường hợp tool thay đổi màu background sẽ bị disable](#7.-Các-trường-hợp-tool-style-sẽ-bị-disable))

   1.2 Thay đổi độ trong suốt background (透明度)

   > Khái quát chức năng: Thay đổi độ trong suốt của màu background
   >

   * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


     | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
     | - | :-: | :-: | :-: | :-: | :-: | :-: |
     | Quyền hạn | o | o | o | o | o | x |
   * Kiểu đối tượng được áp dụng


     | Kiểu đối tượng | Hình tròn | Hình chữ nhật | Hình đa giác | Đường thẳng | Đường thẳng đa giác | Vẽ đường kẻ tự do | Text |
     | - | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
     | Áp dụng | o | o | o | x | o | x | o |
   * Tìm hiểu trường hợp tool thay đổi độ trong suốt background sẽ bị disable([Trường hợp tool thay đổi độ trong suốt background sẽ bị disable](#7.-Các-trường-hợp-tool-style-sẽ-bị-disable))

   1.3 Thay đổi màu của line (線の色)

   > Khái quát chức năng: Thay đổi màu của line
   >

   * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


     | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
     | - | :-: | :-: | :-: | :-: | :-: | :-: |
     | Quyền hạn | o | o | o | o | o | x |
   * Kiểu đối tượng được áp dụng


     | Kiểu đối tượng | Hình tròn | Hình chữ nhật | Hình đa giác | Đường thẳng | Đường thẳng đa giác | Vẽ đường kẻ tự do | Text |
     | - | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
     | Áp dụng | o | o | o | o | o | o | x |
   * Tìm hiểu trường hợp tool thay đổi màu của line sẽ bị disable([Trường hợp tool thay đổi màu của line sẽ bị disable](#7-Các-trường-hợp-tool-style-sẽ-bị-disable))

   1.4 Thay đổi kiểu line (線の種類)

   > Khái quát chức năng: Thay đổi line style theo kiểu default hoặc nét đứt
   >

   * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


     | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
     | - | :-: | :-: | :-: | :-: | :-: | :-: |
     | Quyền hạn | o | o | o | o | o | x |
   * Kiểu đối tượng được áp dụng


     | Kiểu đối tượng | Hình tròn | Hình chữ nhật | Hình đa giác | Đường thẳng | Đường thẳng đa giác | Vẽ đường kẻ tự do | Text |
     | - | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
     | Áp dụng | o | o | o | o | o | x | x |
   * Tìm hiểu trường hợp tool thay đổi kiểu của line sẽ bị disable([Trường hợp tool thay đổi kiểu của line sẽ bị disable](#7-Các-trường-hợp-tool-style-sẽ-bị-disable))

   1.5 Thay đổi kích thước line (線の太さ)

   > Khái quát chức năng: Thay đổi kích thước của line
   >

   * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


     | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
     | - | :-: | :-: | :-: | :-: | :-: | :-: |
     | Quyền hạn | o | o | o | o | o | x |
   * Kiểu đối tượng được áp dụng


     | Kiểu đối tượng | Hình tròn | Hình chữ nhật | Hình đa giác | Đường thẳng | Đường thẳng đa giác | Vẽ đường kẻ tự do | Text |
     | - | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
     | Áp dụng | o | o | o | o | o | o | x |
   * Tìm hiểu trường hợp tool thay đổi kích thước của line sẽ bị disable([Trường hợp tool thay đổi kích thước của line sẽ bị disable](#7-Các-trường-hợp-tool-style-sẽ-bị-disable))

   1.6 Thay đổi chiều mũi tên (矢印の向き)

   > Khái quát chức năng: Thay đổi chiều mũi tên hiển thị
   >

   * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


     | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
     | - | :-: | :-: | :-: | :-: | :-: | :-: |
     | Quyền hạn | o | o | o | o | o | x |
   * Kiểu đối tượng được áp dụng


     | Kiểu đối tượng | Hình tròn | Hình chữ nhật | Hình đa giác | Đường thẳng | Đường thẳng đa giác | Vẽ đường kẻ tự do | Text |
     | - | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
     | Áp dụng | x | x | x | o | o | x | x |
   * Tìm hiểu trường hợp tool thay đổi chiều của mũi tên sẽ bị disable([Trường hợp tool thay đổi chiều của mũi tên sẽ bị disable](#7-Các-trường-hợp-tool-style-sẽ-bị-disable))

   1.7 Thay đổi kích thước của mũi tên (矢印のサイズ) // edited

   > Khái quát chức năng: Thay đổi kích thước của chiều mũi tên hiển thị
   >

   * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


     | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
     | - | :-: | :-: | :-: | :-: | :-: | :-: |
     | Quyền hạn | o | o | o | o | o | x |
   * Kiểu đối tượng được áp dụng


     | Kiểu đối tượng | Hình tròn | Hình chữ nhật | Hình đa giác | Đường thẳng | Đường thẳng đa giác | Vẽ đường kẻ tự do | Text |
     | - | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
     | Áp dụng | x | x | x | o | o | x | x |
   * Tìm hiểu trường hợp tool thay đổi kích thước của chiều của mũi tên sẽ bị disable([Trường hợp tool thay đổi kích thước của chiều của mũi tên sẽ bị disable](#7-Các-trường-hợp-tool-style-sẽ-bị-disable))

   1.8 Thay đổi màu của text (文字の色)

   > Khái quát chức năng: Thay đổi màu của text
   >

   * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


     | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
     | - | :-: | :-: | :-: | :-: | :-: | :-: |
     | Quyền hạn | o | o | o | o | o | x |
   * Kiểu đối tượng được áp dụng


     | Kiểu đối tượng | Hình tròn | Hình chữ nhật | Hình đa giác | Đường thẳng | Đường thẳng đa giác | Vẽ đường kẻ tự do | Text |
     | - | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
     | Áp dụng | x | x | x | x | x | x | o |
   * Tìm hiểu trường hợp tool thay đổi màu của text sẽ bị disable([Trường hợp tool thay đổi màu của text sẽ bị disable](#7-Các-trường-hợp-tool-style-sẽ-bị-disable))

   1.9 Thay đổi kích thước của text (文字のサイズ)

   > Khái quát chức năng: Thay đổi màu của text
   >

   * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


     | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
     | - | :-: | :-: | :-: | :-: | :-: | :-: |
     | Quyền hạn | o | o | o | o | o | x |
   * Kiểu đối tượng được áp dụng


     | Kiểu đối tượng | Hình tròn | Hình chữ nhật | Hình đa giác | Đường thẳng | Đường thẳng đa giác | Vẽ đường kẻ tự do | Text |
     | - | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
     | Áp dụng | x | x | x | x | x | x | o |
   * Tìm hiểu trường hợp tool thay đổi màu của text sẽ bị disable([Trường hợp tool thay đổi màu của text sẽ bị disable](#7-Các-trường-hợp-tool-style-sẽ-bị-disable))
2. Copy (コピー)

   > Khái quát chức năng: Copy object đang được chọn
   >

   * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


     | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
     | - | :-: | :-: | :-: | :-: | :-: | :-: |
     | Quyền hạn | o | o | o | o | o | x |
   * Tìm hiểu trường hợp tool Copy (コピー) sẽ bị disable ([Trường hợp tool copy sẽ bị disable](#8-Các-trường-hợp-tool-copy,-cut-và-paste-bị-disable))
3. Cut (カット)

   > Khái quát chức năng: Xóa và copy object đang được chọn
   >

   * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


     | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
     | - | :-: | :-: | :-: | :-: | :-: | :-: |
     | Quyền hạn | o | o | o | o | o | x |
   * Tìm hiểu trường hợp tool Cut (カット) sẽ bị disable ([Trường hợp tool cut sẽ bị disable](#8-Các-trường-hợp-tool-copy,-cut-và-paste-bị-disable))
4. Paste (貼り付け)

   > Khái quát chức năng: Paste object vừa được copy/cut
   >

   * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


     | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
     | - | :-: | :-: | :-: | :-: | :-: | :-: |
     | Quyền hạn | o | o | o | o | o | x |
   * Tìm hiểu trường hợp tool Paste (貼り付け) sẽ bị disable ([Trường hợp tool paste sẽ bị disable](#8-Các-trường-hợp-tool-copy,-cut-và-paste-bị-disable))
5. Shortcut key

   > Khái quát chức năng: Cho phép thao tác với object hoặc chọn tool bằng shortcut key  // edited
   >

   * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


     | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
     | - | :-: | :-: | :-: | :-: | :-: | :-: |
     | Quyền hạn | o | o | o | o | o | x |
   * Các phím tắt cho phép sử dụng

     1. Copy (コピー) (Ctrl+C)
     2. Cut (カット) (Ctrl+X)
     3. Paste (貼り付け) (Ctrl+V)
     4. Redo (１つ戻る)(Ctrl+Z)
     5. Chọn tất cả (Ctrl+A)
     6. Tool select (選択) (Key A)  // added
     7. Tool Text (テキスト) (Key T) // added
     8. Tool di chuyển background (背景移動) (Spacebar) // added
     9. Xóa object đã chọn (削除) (Key Del) // added
6. Khóa đối tượng (ロック)

   > Khái quát chức năng: Cho phép set lock, unlock canvas trong kế hoạch sắp xếp hiện trường
   >

   ``` Hình ảnh miêu tả object đang ở trạng thái được chọn```

   ![Navbar bottom in case of 1 screen](./document_images/active_object.png)

   ```Hình ảnh miêu tả object đang ở trạng thái bị lock```

   ![Navbar bottom in case of 1 screen](./document_images/object_locked.png)

   * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


     | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
     | - | :-: | :-: | :-: | :-: | :-: | :-: |
     | Quyền hạn | o | o | o | o | o | x |
   * Các trường hợp cho phép thực hiện chức năng

     1. Cho phép Lock/Unlock 1 object hoặc 1 group
     2. Chọn nhiều object/group, trong đó có 1 object/group bị lock
     3. Lock tất cả object hoặc tất cả group

   ~~~
   NOTE: Admin công ty hợp tác và thợ cả không thể unlock object đã lock bởi admin trụ sở chính, admin chi nhánh quản đốc hiện trường hoặc quản đốc hiện trường. // edited
   ~~~

   Các tool sẽ bị disable khi thực hiện chức năng khóa đối tượng([Các tool sẽ bị disable khi thực hiện chức năng lock object](#9-Các-tool-sẽ-bị-disable-khi-thực-hiện-chức-năng-lock-object))
7. Group (グループ化) hoặc Ungroup (グループ解除) nhiều đối tượng

   > Khái quát chức năng: Cho phép group hoặc ungroup nhiều object
   >

   * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


     | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
     | - | :-: | :-: | :-: | :-: | :-: | :-: |
     | Quyền hạn | o | o | o | o | o | x |
   * Chỉ áp dụng group với 2 object trở lên.
   * Các tool sẽ bị disable khi thực hiện chức năng group hoặc ungroup nhiều đối tượng([Các tool sẽ bị disable khi thực hiện chức năng group và ungroup nhiều đối tượng](#10.-Các-tool-sẽ-bị-disable-khi-thực-hiện-chức-năng-group-hoặc-ungroup))
8. Redo (１つ戻る)

   > Khái quát chức năng: Lùi 1 bước về trạng thái chỉnh sửa trước đấy
   >

   * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


     | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
     | - | :-: | :-: | :-: | :-: | :-: | :-: |
     | Quyền hạn | o | o | o | o | o | x |

   ~~~
   - Tối đa 5 lần redo trên 1 màn hình thao tác. Sau 5 lần thao tác sẽ disable tool redo
   - Reload lại trang sẽ reset lại số lần redo về 0
   ~~~
9. Go foward (１つ進む)

   > Khái quát chức năng: Tiến lên 1 bước trạng thái chỉnh sửa vừa lùi (１つ進む)
   >

   * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


     | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
     | - | :-: | :-: | :-: | :-: | :-: | :-: |
     | Quyền hạn | o | o | o | o | o | x |

   ~~~
   - Tối đa 5 lần go forward trên 1 màn hình thao tác. Sau 5 lần thao tác sẽ bị disable nút go forward
   - Reload lại trang sẽ reset số lần go forward về 0
   ~~~
10. Di chuyển object lên trên cùng (最前面へ)

    > Khái quát chức năng: Di chuyến object lên vị trí hiển thị đầu tiên
    >

    * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


| Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
| - | :-: | :-: | :-: | :-: | :-: | :-: |
| Quyền hạn | o | o | o | o | o | x |

    1. Sau khi chọn tool Di chuyển đối tượng lên trên cùng (最前面へ) sẽ disable tool Di chuyển đối tượng lên trên cùng (最前面へ) và active tool Di chuyển đối tượng xuống cuối cùng (最背面へ)

       ```Hình ảnh miêu tả tool Di chuyển đối tượng lên trên cùng (最前面へ) bị disable```

       ![Disable tool move-front and active tool move-back](./document_images/active_tool_move_back.png)
    2. Disable tool Di chuyển đối tượng lên trên cùng (最前面へ) với các trường hợp:

       - Nếu chỉ có 1 object hoặc 1 group trên màn hình canvas
       - Object đang hiển thị đang ở vị trí đầu tiên
11. Di chuyển object xuống dưới cuối

    > Khái quát chức năng: Di chuyển object xuống vị trí hiển thị cuối cùng
    >

    * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


| Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
| - | :-: | :-: | :-: | :-: | :-: | :-: |
| Quyền hạn | o | o | o | o | o | x |
    * Sau khi chọn Di chuyển đối tượng xuống cuối cùng (最背面へ) sẽ disable tool Di chuyển đối tượng xuống cuối cùng (最背面へ) và active tool Di chuyển đối tượng lên trên cùng (最前面へ)

      ```Hình ảnh miêu tả tool Di chuyển đối tượng xuống cuối cùng (最背面へ) bị disable```

      ![Disable tool move-back (最背面へ) and active tool move-front (最前面へ)](./document_images/active_tool_move_front.png)

## 6. In kế hoạch sắp xếp hiện trường

1. Thiết lập phạm vi in

   > Khái quát chức năng: Cho phép thiết lập phạm vi in
   >

   * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


   | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
   | - | :-: | :-: | :-: | :-: | :-: | :-: |
   | Quyền hạn | o | o | o | o | o | x |
2. Cho phép chuyển đổi pham vị in sang định dạng PDF và thực hiện download.

   > Khái quát chức năng: Cho phép convert phạm vi in đã thiết sang PDF, và thực hiện chức năng download.
   >

   * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


   | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
   | - | :-: | :-: | :-: | :-: | :-: | :-: |
   | Quyền hạn | o | o | o | o | o | x |

## 7. Thông tin màn hình sắp xếp hiện trường // added tất cả các nội dung bên dưới

1. Thiết lập chế độ toàn màn hình (フルスクリーンモード)

    > Khái quát chức năng: Trên chế độ full screen, sẽ hiển thị màn hình canvas và layout chọn tool, header và navbar ở góc phải cuối màn hình
    >

* Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


   | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
   | - | :-: | :-: | :-: | :-: | :-: | :-: |
   | Quyền hạn | o | o | o | o | o | x |
* Khi hiển thị chế độ fullscreen sẽ ẩn 2 menu navbar bên trái màn hình

~~~
NOTE: Mặc định khi vào màn hình hiện trường sẽ ở chế độ fullscreen
~~~

2. Khóa mở/mở khóa màn hình canvas

    > Khái quát chức năng: Khóa hoăc mở khóa màn hình canvas, admin công ty hợp tác và thợ cả không thể thêm hay chỉnh sửa object trong màn hình canvas, tool style sẽ bị ẩn đối với 2 role trên.
    >

  | Người sử dụng | Admin trụ sở chính | Admin chi nhánh | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
  | - | :-: | :-: | :-: | :-: | :-: | :-: |
  | Quyền hạn | o | o | o | x | x | x |
3. Số lượng object đã vẽ

	> Khái quát chức năng:  Tối đa 500 object có thể vẽ, số lượng object sẽ update khi người dùng thêm/bớt object.
    >
