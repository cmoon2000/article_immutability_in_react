immutable giành cho tối ưu hóa

liên quan `shouldComponentUpdate()`

bản chất là đi so sánh prop/state hiện tại với prop/state trước đó

Vòng đời (theo thứ tự ⏲):

    + 1. change state undirectly (of course🧛‍)
    + 2. shouldComponentUpdate

🤔 immutable should be shallow or deep copy???