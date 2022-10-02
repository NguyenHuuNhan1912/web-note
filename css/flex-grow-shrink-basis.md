# Flex Grow, Shrink, Basis trong Flexbox 
## Flex Grow 
* `flex grow`: Là thuộc tính của một `flex-item `
* `Trường hợp sử dụng`: Khi muốn các `flex-item` dãn ra để chiếm trọn diện tích của `flex-container`
* `Giá trị mặc định là 0`: Mặc định là không cho phép dãn ra
## Flex Shrink
* `flex shrink`: Là một thuộc tính của flex-item
* `Trường hợp sử dụng`: Khi muốn các `flex-item` co lại để vừa với diện tích của `flex-item`
* `Giá trị mặc định là 1`: Mặc định là luôn cho phép co lại
## Flex basis
* `Flex basis`: Là thuộc tính của `flex-item`
* `Trường hợp sử dụng`: Đặt width cho `flex-item`
* `Giá trị mặc định là auto`
## Hiểu hơn về các giá trị trên
### Ví dụ
* 1 `flex-container` có width = 800px
* `flex-container` có 2 `flex-item`
* `flex-item-1` có width = 200px
* `flex-item-2` có width = 400px 
* Chúng ta thấy width của `flex-item-1` và width của `flex-item-2` chỉ có 600px 
* Vậy `flex-container` sẽ thừa ra 200px và đó gọi là `flex-space`
* Lần lượt cho `flex-item-1` và `flex-item-2` giá trị `flex-grow: 1`
* Lúc này width của `flex-item-1` và `flex-item-2` sẽ không còn là 200px và 400px như trước nữa mà sẽ thay đổi thành 300px và 500px -> Vừa đủ với width của `flex-container`
* Vậy tại sao flexbox lại làm được điều đó ?
* Dựa trên công thức: `flex-item` = (`flex-grow-item`/`flex-grow-total`) * `flex-space` 
        ** với `flex-space` sẽ là width của `flex-container` - tổng của các width `flex-item`
        ** với `flex-grow-total` là tổng các giá trị của flex-grow của mỗi item ví dụ này `flex-grow-total` là 2
        ** với `flex-grow-item` là giá trị `flex-grow` của item ví dụ này là 1
        ** `flex-item-1` = (1/2) * 400px = 200px
        ** `flex-item-2` = (1/2) * 400px = 200px
        ** Vậy `flex-item-1` và `flex-item-2` sẽ được cộng thêm 200px
        ** Cộng thêm width ban đầu thì sẽ chiếm trọn chiều ngang của `flex-container`
* `Flex Shrink` có công thức tương tự như `Flex grow` nhưng `Flex-space` sẽ được tính ngược lại
    ** `flex-space` = Tổng các width `flex-item` - width của `flex-container`
    ** Vì bản chất là muốn các `flex-item` co lại để vừa với width của `flex-container`

