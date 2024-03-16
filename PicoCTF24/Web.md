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
