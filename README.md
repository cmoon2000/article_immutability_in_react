Thuật ngữ Immutability - tính không thay đổi là một khái niệm cần phải được hiểu khi sử dụng React. Có thể bạn đã biết rằng chúng ta không được [trực tiếp thay đổi trạng thái](https://reactjs.org/docs/state-and-lifecycle.html#do-not-modify-state-directly). 

> Vậy làm sao để thay đổi trạng thái khi bạn không được phép thay đổi nó?

Bạn dễ cảm thấy khó hiểu. Thay đổi dữ liệu mà không thay đổi dữ liệu? Nghe đầy sạn phải không?

Bài viết này sẽ giải đáp cho thắc mắc này.

# Immutability là gì?

Mutability được dịch là 'tính chất có thể thay đổi'. Trong lập trình, chúng ta sử dụng từ này để chỉ ra những đối tượng mà trạng thái có thể bị thay đổi. Ngược lại, một đối tượng sau khi được tạo ra mà không bao giờ thay đổi - ta nói giá trị của nó có tính không thay đổi.