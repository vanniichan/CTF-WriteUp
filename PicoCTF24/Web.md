# Bookmarklet

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/122f0369-c8f7-44a3-b4f7-33b71f41cb74)

Bài này đơn giản chỉ cần bật console chạy là xong 

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/66547c16-637e-44bd-b0ce-1ac87de5ea4b)

Flag: `picoCTF{p@g3_turn3r_1d1ba7e0}`

# WebDecode

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/eefef95a-6a6c-456c-b05e-2b149506eaa0)

Thử dò chức năng vào ở chức năng about thấy một mã base64

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/2752a173-845a-4957-9568-f749baf102b3)

Flag: `picoCTF{web_succ3ssfully_d3c0ded_df0da727}`

# IntroToBurp

Bài này có 2 chức năng là đăng ký và nhập otp

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/03bd66ff-2ead-4f19-a43d-9fe1be6a7261)

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/7129ca3c-937d-4bf3-9fec-face54f4ee27)

Sẽ ra sao nếu ta xóa đi param `otp`

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/5a465e83-97a0-419b-903e-a6fcc1ef9618)

Flag: `picoCTF{#0TP_Bypvss_SuCc3$S_2e80f1fd}`

#  Unminify

Bài này đơn giản cũng chỉ là lục ra flag trong Crt + U :)

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/9a61ccc5-b38b-4422-b7e3-a780396fdfc4)

Flag: `picoCTF{pr3tty_c0d3_622b2c88}`

# No SQL Injection

Hint to tổ bố ngay đề bài

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/218369ce-5fb7-4235-86c6-c40e804aad8f)

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/7746bdcb-82c0-46fe-8288-cd098f225bf6)

Tải folder về chú ý được trong database có tài khoản và flag nằm ở Token

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/e9213c82-3c91-4650-9793-1ab011d09e9c)

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/1b8a2edc-b389-47a4-a154-a8c466b1113b)

Từ trên cũng thấy được ta phải login được vào để lấy token 

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/16a604de-7d4c-4d99-a940-ad9c6a4bc21f)

Tuy nhiên khi bắt gói tin ta lại thấy 2 gói login và login/

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/1c681c80-6a34-4509-8845-67fa211050b9)

`$ne:"invalid"` là query truy vấn tất cả giá trị không khớp với invalid để luôn thõa mãn với `email`

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/48b3ad39-bcf7-4265-b2f4-a535112b8619)

Không nhập được, nên thử cách khác với " --> \"

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/63a250bd-e8be-4d6b-a05f-f29c4c01bb83)

Flag:  `picoCTF{jBhD2y7XoNzPv_1YxS9Ew5qL0uI6pasql_injection_53d90e28}`

# Trickster

Bài này chỉ nhận file là `.png`

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/f48af0a5-f424-4cc5-81ad-7cd648b60308)

Tuy nhiên khi upload thành công thì file ảnh sẽ ở đâu và xem như thế nào? --> `/robots.txt`

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/9cd85183-3bc0-4075-a23d-b86b8f1c2d07)

Thử giấu đuôi `.png.php` xem có được không :))

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/0220657d-62ce-46a0-92ce-3b618bc852cc)

Sẽ ra sao nếu file png thật nhưng lại có mã shell? Nhưng chèn payload vào đâu

https://thecyberjedi.com/php-shell-in-a-jpeg-aka-froghopper/

Vậy thì có thể dùng `Exiftool` để chèn php shell vào comment 

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/7f279125-e744-4107-8fe3-b9af9b61ea5a)

Đổi thành `.png.php`

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/c07d1748-bf40-4287-91e9-736ddd5f4156)

Như đã nói ở trên file được up ở `/uploads` 

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/276498bc-2e5d-4cf8-8f29-8e8b8ffee29d)

RCE thành công rồi =))

Tiếp tục dùng shell khác để tiến hành lấy flag `/uploads/ls.png.php`

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/682e47be-90cf-43b2-a17e-d6676cd91bdc)

`/GQ4DOOBVMMYGK.txt` 

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/4071e198-2436-482a-83e5-c724717ccb90)

Flag: `picoCTF{c3rt!fi3d_Xp3rt_tr1ckst3r_48785c0e}`
