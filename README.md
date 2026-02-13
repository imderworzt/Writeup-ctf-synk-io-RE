# Writeup-ctf-synk-io-RE

## Bài 1: Gen_Z_P'Batching_Game

Chạy thử chương trình ta thấy có 4 thử thách

Sau khi xem đề bài của cả 4, tôi quyết định sử dụng các chuỗi mồi như sau:
1. print123
2. HACK1234 (có tiền tố HACK ở đầu)
3. abc_X0X_b (có _X0X_ ở trong)
4. char sum 500 (có 500 ở trong)

Giờ vào IDA, tìm các hàm main::trail(1, 2, 3, 4) và lần lượt đặt BP ở:

Với trail 1:

<img width="1539" height="787" alt="image" src="https://github.com/user-attachments/assets/7c0f576a-3416-4c82-98e9-0f6fa3d9040b" />

Với trail 2:

<img width="1539" height="824" alt="image" src="https://github.com/user-attachments/assets/ee06ab3b-99b0-4ca4-be16-75921032d0cb" />


Với trail 3:

<img width="1561" height="860" alt="image" src="https://github.com/user-attachments/assets/22b13f98-1208-445f-9142-734ab8c8e638" />

Và với trail 4:

<img width="1535" height="783" alt="image" src="https://github.com/user-attachments/assets/c199a836-0eb0-4a15-bb59-005edf4be175" />


Giờ bắt đầu debug

Nhập một nametag ngẫu nhiên và bắt đầu làm

Chọn thử thách 1

<img width="1451" height="775" alt="image" src="https://github.com/user-attachments/assets/472137ed-6cac-402b-9e27-d248c5b075bc" />

Nhập đoạn mồi "print123" và nhấn enter

<img width="1831" height="870" alt="image" src="https://github.com/user-attachments/assets/5f106a85-9f49-429d-ab0a-1533b94a2eef" />

Những câu lệnh lúc nãy ta đặt BP sẽ đều thực hiện những việc sau:

```
  - Kiểm tra sau khi nhập chuỗi, thanh ghi RAX có bằng 1 không
  - Nếu bằng 1 thì nhiệm vụ thất bại, khác 1 thì clear
```

Giờ nhấp chuột vào thanh ghi RAX, nhấn E và sửa giá trị về 0

<img width="631" height="187" alt="image" src="https://github.com/user-attachments/assets/e8f7968d-d458-4e74-bdf8-4df6a9a715c0" />

Sau đó nhấn F9 và qua thử thách

Tiếp theo cứ làm tương tự với 3 thử thách còn lại, chọn thử thách, nhập đoạn mồi tương ứng, thay giá trị RAX về 0 và nhấn F9

Sau khi hoàn thành cả 4, ta chọn lựa chọn 5 và thu được

<img width="1126" height="609" alt="image" src="https://github.com/user-attachments/assets/c21e277a-24b1-46fc-9a4c-c8f6bf5f7ac5" />

FULL ARTIFACT: flag{P3tch!nG_s_Kinds_C00oO0OOL_IG}

Hoàn thành bài
