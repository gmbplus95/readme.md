# Thiết kế màn hình keyplan

## Khái quát

* Cho phép user thiết kế màn hình keyplan

## Cách vào màn hình

* Quản lý master > Danh sách hiện trường
  * Trường hợp chưa có dữ liệu thì sẽ tạo mới màn hình keyplan

    * Cách 1: Chọn 1 hiện trường -> Chọn tab 作業予定一覧 -> Click button 新規作成 để  vào form tạo màn hình keyplan mới
    * Cách 2: Chọn 1 hiện trường -> Chọn tab 作業実績一覧 -> Click button 新規作成 để vào form tạo màn hình keyplan mới

    ~~~
    - Trường hợp form tạo đã có dữ liệu về các màn hình keyplan hiện tại. User có thể chọn 1 màn hình keyplan để chỉnh sửa
    ~~~
  * Trường hợp đã có dữ liệu thì sẽ cho phép vào edit màn hình keyplan

## Định nghĩa thuật ngữ

- Không có

## Ký hiệu sử dụng

- o : Áp dụng
- x : Không áp dụng

## 1. Định nghĩa hạng mục màn hình

### 1. Tổng quan màn hình keyplan

``` Hình ảnh miêu tả tổng quan màn hình keyplan. Mặc định chọn Home tab (ホーム) khi vào trang hoặc reload trang.```

![Layout screen](./document_images/layout_screen_active_home_tab_keyplan.png)

1. Home tab (ホーム)
2. Edit tab (オブジェクトの編集)
3. Các tool sử dụng để style canvas(Home tab (ホーム))

   1. Lùi 1 bước về trạng thái chỉnh sửa trước đấy (１つ戻る)
   2. Tiến lên 1 bước trạng thái chỉnh sửa vừa lùi (１つ進む)
   3. Chọn đối tượng (選択)
   4. Thêm text (テキスト)
   5. Thêm linh kiện (アイテム)
   6. Vẽ hình (図形)
   7. Vẽ đường (線) // edited
   8. Di chuyển background (背景移動)
   9. Cut object được chọn (カット)
   10. Copy object được chọn(コピー)
   11. Paste object được chọn (貼り付け)
4. Màn hình canvas
5. Màn hình print range
6. Menu navigation bottom
7. Phần thông tin của page header

``` Hình ảnh miêu tả tổng quan màn hình keyplan khi chọn một đối tượng và click vào Edit tab (オブジェクトの編集 ).```

![Layout screen](./document_images/layout_screen_active_edit_tab_keyplan.png)

1. Home tab (ホーム)
2. Edit tab (オブジェクトの編集)
3. Các tool sử dụng để style canvas(Edit home)

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
4. Màn hình canvas
5. Màn hình background print
6. Menu navigation bottom
7. Object được vẽ

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
   7. Thay đổi kích thước của chiều mũi tên (矢印のサイズ) ([Các trường hợp Kích thước mũi tên(矢印のサイズ) sẽ được enable hoặc disable](#11.-Các-trường-hợp-tool-arrow-size-sẽ-được-enable-hoặc-disable))
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

   ![Active tool Home tab (ホーム) and disable tool Edit tab (オブジェクトの編集)](document_images/active_home_tab.png)

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

   ![Disable tool delete object](./document_images/disable_edit_tab_keyplan_screen.png)

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

1. Trạng thái bình thường
2. Trạng thái không hoạt động(Vô hiệu hóa)
3. Trạng thái không hoạt động + di chuột qua
4. Trạng thái khi di chuột qua
5. Trạng thái đã chọn

## 2. Vẽ canvas trong kế hoạch sắp xếp hiện trường

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

        ![Disable tool move-front(最前面へ), move-back(最背面へ)](./document_images/disable_tool_move_front_and_move_back.png)
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
      * User có thể thay đổi các đường thẳng của đối tượng bằng cách ấn double click vào đối tượng. Sau có chọn 1 điểm và kéo để thay đổi giá trị của đường thẳng.

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


     | Người sử dụng | Admin trụ sở chính | Admin chi nhánh quản đốc hiện trường | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
     | - | :-: | :-: | :-: | :-: | :-: | :-: |
     | Quyền hạn | o | o | o | o | o | x |
   * Các tool style sẽ được enable và disable với đối tượng là text ([Tìm hiểu các tool style áp dụng và không áp dụng với đối tượng là text](#1-Nhóm-các-style-áp-dụng-cho-đối-tượng-là-text-bao-gồm:)).
   * Disable tool group (グループ化)

     ``` Hình ảnh miêu tả tool group (グループ化) bị disable```

     ![Disable tool group (グループ化)](./document_images/disable_tool_group.png)
   * Chỉnh sửa text: Có thể sửa text đã vẽ bằng cách double click lên text muốn chỉnh sửa, click bất kì vị trí nào bên ngoài để kết thúc chỉnh sửa. // added
6. Thêm linh kiện (アイテム)

   > Khái quát chức năng: Cho phép chọn loại linh kiện, hiển thị ảnh linh kiện tương ứng
   >

   * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


     | Người sử dụng | Admin trụ sở chính | Admin chi nhánh quản đốc hiện trường | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
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
7. Tự động chọn object sau khi vẽ

   * Sau khi thêm ảnh, linh kiện, text, vẽ hình và vẽ line sẽ tự động chuyển sang tool chọn object và chuyển trạng thái thành đã được chọn với object vừa vẽ. Đồng thời sẽ kích hoạt Edit tab (オブジェクトの編集)

     ```Hình ảnh dưới đây miêu tả tool chọn object đã được chọn```

     ![Active tool select](./document_images/automatically_select_the_object_keyplan_screen.png)

     1. Tool chọn object đã được chọn
     2. Active tool edit tab
   * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


     | Người sử dụng | Admin trụ sở chính | Admin chi nhánh quản đốc hiện trường | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
     | - | :-: | :-: | :-: | :-: | :-: | :-: |
     | Quyền hạn | o | o | o | o | o | o |

## 3. Bottom Navigation  // edited

1. Thiết lập zoom // edited

   > Khái quát chức năng: Cho phép phóng to, thu nhỏ canvas // edited
   >

   * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


     | Người sử dụng | Admin trụ sở chính | Admin chi nhánh quản đốc hiện trường | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
     | - | :-: | :-: | :-: | :-: | :-: | :-: |
     | Quyền hạn | o | o | o | o | o | x |
   * Mức phóng nhỏ nhất là 25%
   * Mức phóng lớn nhất là 800%

   ~~~
   NOTE: Disable button thu nhỏ khi độ phóng là 25%
   ~~~

   ``` Hình ảnh miêu tả nút thu nhỏ bị disable```

   ![Disable zoomdown button](./document_images/disable_zoomdown_button_keyplan_screen.png)

   ~~~
   NOTE: Disable button phóng to khi độ phóng là 800%
   ~~~

   ``` Hình ảnh miêu tả nút phóng to bị disable```

   ![Disable zoomin button](./document_images/disable_zoom_in_button_keyplan_screen.png)

// deleted

## 4. Chỉnh sửa canvas trong kế hoạch sắp xếp hiện trường

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

       ![Disable tool move-front (最前面へ) and active tool move-back (最背面へ)](./document_images/active_tool_move_back.png)
    2. Disable tool Di chuyển đối tượng lên trên cùng (最前面へ) với các trường hợp:

       - Nếu chỉ có 1 object hoặc 1 group trên màn hình canvas
       - Object đang hiển thị đang ở vị trí đầu tiên
11. Di chuyển object xuống dưới cuối

    > Khái quát chức năng: Di chuyển object xuống vị trí hiển thị cuối cùng
    >

    * Những kiểu tài khoản dưới đây có quyền thực hiện chức năng.


      | Người sử dụng | Admin trụ sở chính | Admin chi nhánh quản đốc hiện trường | Quản đốc hiện trường | Admin công ty hợp tác | Thợ cả | Thợ thủ công |
      | - | :-: | :-: | :-: | :-: | :-: | :-: |
      | Quyền hạn | o | o | o | o | o | x |
    * Sau khi chọn Di chuyển đối tượng xuống cuối cùng (最背面へ) sẽ disable tool Di chuyển đối tượng xuống cuối cùng (最背面へ) và active tool Di chuyển đối tượng lên trên cùng (最前面へ)

      ```Hình ảnh miêu tả tool Di chuyển đối tượng xuống cuối cùng (最背面へ) bị disable```

      ![Disable tool move-back (最背面へ) and active tool move-front (最前面へ)](./document_images/active_tool_move_front.png)
12. Số lượng object đã vẽ  // added

    > Khái quát chức năng:  Tối đa 500 object có thể vẽ, số lượng object sẽ update khi người dùng thêm/bớt object.
    >
