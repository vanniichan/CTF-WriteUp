# Save the City

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/f9435a75-4a01-41a5-a8d2-9445342605d3)

Sau khi sử dụng lệnh của bài ta có:

![Ảnh chụp màn hình 2024-03-03 154644](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/3306d58d-30ef-4534-80dd-e641d379f731)

Hầu như không thể tương tác gì, terminal chỉ hiện ra phiên bản SSH và kết thúc chương trình, thử lên tra xem có CVE nào về phiên bản này không:

`https://gist.github.com/mgeeky/a7271536b1d815acfb8060fd8b65bd5d`

Vậy là có và ta có thể khai thác và theo đề, chúng ta cần tìm được location 

![Ảnh chụp màn hình 2024-03-03 155027](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/264c57f2-5d51-486a-ae73-84e0ca910182)

Flag: `VishwaCTF{elrow-club-pune}`

# Trip to Us

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/19c13343-a45f-4147-8ff7-990486f81689)

Bài này tìm hidden login để lấy flag. Sử dụng `dirsearch` ta tìm được 2 đường dẫn vào trang login (home.php) và /db (database) để lấy flag

![Ảnh chụp màn hình 2024-03-03 155559](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/abc284ee-6691-45ab-894e-0914acfaac22)

![Ảnh chụp màn hình 2024-03-03 155320](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/413b4634-2cf2-4052-9429-ea991424d858)

Flag: `VishwaCTF{y0u_g0t_th3_7r1p_t0_u5}`

# They are coming 

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/fb4d5e9f-4739-4056-9017-17507d4ffb92)

Truy cập vào robots.txt để xem có path nào được allow không:

![Ảnh chụp màn hình 2024-03-03 155707](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/406f8b83-e920-472a-be73-4bf438a82219)

Dcode bằng base64 ta có hidden path `/secret-location` và sau đó ở mục local store ta có flag, tuy nhiên nó đã bị encode

![Ảnh chụp màn hình 2024-03-03 155745](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/d1844812-12e8-453c-b7e2-d018ad5f5617)

Từ đề bài ta có thể lấy được cipher của nó là aes128:

![Ảnh chụp màn hình 2024-03-03 160023](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/4e28679d-3aff-4be6-9d4c-b94d0d8e3f63)

Flag: `VishwaCTF{g0_Su88m1t_1t_Qu14kl7}`

# H34D3RS

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/c4010493-656b-4659-9b1e-002be803e841)

Từ yêu cầu đề bài, ta có thể khai thác thông qua các header, sử dụng `Burp` để gửi Request:

Ta nhận được Respond, tức là có thể tác động vào `User-Agent`

![Ảnh chụp màn hình 2024-03-04 161942](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/f6eb9d3a-1bf6-4f3d-9267-32049493b4dd)

![Ảnh chụp màn hình 2024-03-04 162105](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/112f3b00-21f2-4a17-8446-c36797452758)

Vừa đọc hiểu vừa search gg để dử dụng các header :)

![Ảnh chụp màn hình 2024-03-04 162238](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/a663defb-c09f-4fd1-a6f2-82f11c02a14c)

Đoạn này là hơi mất thời gian về cái `nine time` này =))

![Ảnh chụp màn hình 2024-03-04 162457](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/7100dacb-7ffb-4365-80a4-3ac8d8cb3ec8)

![Ảnh chụp màn hình 2024-03-04 162535](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/bb360789-0c01-4411-9c74-393b8d9054b5)

```
GET / HTTP/2
Host: ch42789157521.ch.eng.run
Referer: https://vishwactf.com/
Upgrade-Insecure-Requests: 10
User-Agent: lorbrowser
Date: 2044
Downlink: 999999999
```
 Flag: `VishwaCTF{s3cret_sit3_http_head3rs_r_c0o1}`


