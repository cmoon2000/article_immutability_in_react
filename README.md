Thuật ngữ Immutability - tính không thay đổi là một khái niệm cần phải được hiểu khi sử dụng React. Có thể bạn đã biết rằng chúng ta không được [trực tiếp thay đổi trạng thái](https://reactjs.org/docs/state-and-lifecycle.html#do-not-modify-state-directly). 

> Vậy làm sao để thay đổi trạng thái khi bạn không được phép thay đổi nó?

Bạn dễ cảm thấy khó hiểu. Thay đổi dữ liệu mà không thay đổi dữ liệu? Nghe đầy sạn phải không?

Bài viết này sẽ giải đáp cho thắc mắc này.

# Immutability là gì?

**Mutability** được dịch là 'tính chất có thể thay đổi'. Trong lập trình, chúng ta sử dụng từ này khi nói tới những đối tượng mà trạng thái có thể bị thay đổi. Ngược lại, một đối tượng sau khi được tạo ra mà không bao giờ thay đổi - ta nói giá trị của nó có **tính không thay đổi**.

Có vẻ lạ nhưng thực tế chúng ta sử dụng rất nhiều giá trị có tính không thay đổi. Chả hạn như chuỗi:

```js
  > let familiarSlogan = '2 3 Dzo'    // tạo ra một chuỗi và gán nó vào biến

  // Giả sử muốn đổi thành '2 3 Nhau'
  > familiarSlogan[4] = 'N';
  > familiarSlogan[5] = 'h';
  > familiarSlogan[6] = 'a';
  > familiarSlogan[7] = 'u';
  > familiarSlogan
  '2 3 Dzo'  // familiarSlogan không bị thay đổi

  > familiarSlogan = familiarSlogan.slice(0, 4) + 'Nhau'  // tạo chuỗi mới
  > familiarSlogan
  '2 4 Nhau'
```

Chúng ta không thể thay đổi ngay trên chuỗi '2 3 Dzo'. Để *familiarSlogan* có giá trị mới, ta chỉ còn cách tạo một chuỗi mới và gán vào biến.



