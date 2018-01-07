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

Chúng ta không thể thay đổi ngay trên chuỗi '2 3 Dzo'. Để *familiarSlogan* có giá trị mới, ta sẽ phải tạo một chuỗi mới và gán lại vào biến.

# Spread operator

Ví dụ sau sẽ sử dụng **spread operator** đối với mảng và đối tượng. Bằng cách đặt dấu 3 chấm trước mỗi một mảng/đối tượng, ta sẽ lấy ra được thành phần con của mảng/đối tượng đó.

```js
// Mảng:
let nums = [1,2,3];
let otherNums = [...nums];  // => [1,2,3]
nums === otherNums // => false! nums và otherNums là 2 đối tượng phân biệt mặc dù chúng có các phần tử giống nhau

// Đối tượng:
let person = {
  name: "Liz",
  age: 32
}
let otherPerson = {...person};  // tạo ra một người khác có cùng đặc điểm
person === otherPerson  // false! đây là 2 người khác nhau

// 
let company = {
  name: "TNHH Foo",
  people: [
    {name: "Joe"},
    {name: "Alice"}
  ]
}
let newCompany = {...company};
newCompany === company  // => false!
newCompany.people === company.people  // => true!
```

Từ một mảng/đối tượng, **Spread operator** giúp ta tạo mới một mảng/đối tượng có cùng nội dung. Điểm hữu ích là ta có thể thay đổi các thuộc tính của bản sao khi cần:

```js
let liz = {
  name: "Liz",
  age: 32,
  location: {
    city: "Portland",
    state: "Oregon"
  },
  pets: [
    {type: "cat", name: "Redux"}
  ]
}

// tăng tuổi Liz lên 1, trong khi các thuộc tính còn lại giữ nguyên:
let olderLiz = {
  ...liz,
  age: 33
}
```
