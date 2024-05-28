# kcehC ytinaS

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/865689d2-08cd-4330-b01e-99a1eb66ee87)

Nhìn mô tả thôi cũng biết phải làm gì trong discord : )

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/bed3631e-649d-4da3-bde7-26a1ce6eaa95)

Nhìn từ phải sang trái là ta có flag 

Flag: `actf{who_did_you_decode_my_secret_message}`

# Putnam

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/a8996ae0-1853-4c01-844e-86e8f781c8ec)

...

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/1706597d-62ed-485b-9262-f1e6fe8cbfc1)

Flag: `actf{just_a_tad_easier_than_the_actual_putnam}`

# trip

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/7077cca6-275d-4e40-b21e-cf8b38f550e0)

Tải file về thì ta có ảnh:

![trip](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/c7be05be-8aa2-42e5-bc81-51b38f287651)

Bài này nó yêu cầu tìm vị trí. Exif tool :

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/45fc76c8-17ff-4dc1-a6a5-f77d20496a48)

Đem dcode sau đó map 

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/fcbe3007-7f84-4881-ad57-b7d0512e7504)

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/2bd9d48f-b779-4633-ba4a-7f8e8e2b5cdd)

Flag: `actf{Chincoteague}`

# aw man

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/647faf63-2b20-4860-a31f-de4a289b5031)

Tải file về :

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/0526aa72-1e95-41f6-b191-f07992e7daf1)

Exif tool:

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/692a3b3c-06e5-40fa-af6a-5d4b555ae1d3)

Đem dcode và ta có flag:

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/d18bc35d-fb79-4e3d-8e02-d0915367c583)

Flag: `actf{crazy?_i_was_crazy_once}`

# do you wanna build a snowman

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/a3b8ec22-d191-45a5-b593-9c10951c122f)

```
curl -O https://files.actf.co/67ad046a16c81593ac82fdc7975dd8713a9c364774b69e2a8a3632e639c7fc66/snowman.jpg
-O : lấy file từ xa
-o : lấy file và lưu nó ở 1 file.txt định sẵn
```
![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/903714d7-3c52-4fc3-8abb-2d9b5ef26e1d)

Tải file về nhưng nó bị lỗi nội dung:

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/4a2317b1-1f4d-4a7b-b4ba-53ab211acf76)

Dùng HxD ta có thể đoán đượ vấn đềlà head signature của file hình như sai

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/ab19ea45-c987-4df9-9da2-83ce6c346c09)

Sửa lại:

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/7dfac4e4-f3be-4608-946a-48c10d8d9bb4)

Sửa lại byte cho đúng header:

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/2eee0abf-2583-476f-9d52-a8c4f16bb45c)

Ảnh sau khi sửa:

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/a8ce405a-bfe6-4364-8c48-0f0e9b6a3269)

Flag: `actf{built_the_snowman}`

