Giải này hơi khó :) nên giải được 1 bài 

# Rabbithole

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/dcedc914-5694-4103-83d6-02c69079dba3)

`robots.txt` kiểm tra ta có 1 path:

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/140e7ec2-94f0-431f-aeaf-3c8025d072f4)

Dựa vào `hardworking` được bold có thể thử xem nó có phải là path khác không:

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/a397c0c9-faa6-4154-857c-783ff32653b8)

Method not Allowed? có nghĩa là có 1 method nào đó cho phép vào và ta còn có `s3cr3t1v3_m3th0d` là hint. Mở Burp để kiểm tra:

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/d239fd2c-c978-4379-a6aa-5277ac8871c2)

Thường những Respond như thế này ta sẽ thử qua `Cookie` vì `userID=guest` thay bằng admin 

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/37b55eef-7080-4055-80cf-bbbdf99586c9)

Flag: `pearl{c0ngr4t5_but_th1s_1s_just_th3_b3g1nn1ng}`
