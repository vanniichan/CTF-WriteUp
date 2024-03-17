![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/9d556e1f-60f9-49b6-9a2e-a7212809c75f)

Mình chỉ làm 3 bài gần cuối vì nó hơi "rắc rối" xíu, mấy bài kia thì đơn giản quá :)

# Binary Search

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/1923957e-af3d-42d7-9639-117c9d1aa4ec)

Đọc code chỉ lưu ý là nhập 10 lần đoán được số để ra flag sai thì random lại số đó

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/115dc7b9-a0fb-4e75-953f-15d2152b755c)

Vì số chạy từ 1 --> 1000 nên mình sẽ lấy từ 500 làm mốc rồi từ đó %2

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/f857d191-106d-4183-9225-e2b7cbd62abe)

Tiếp tục tính trung bình 

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/46b429d5-9bf6-46f3-9e4d-ae25cab9a42c)

Xác suất tầm thứ 8 là có thể ra flag

Flag: `picoCTF{g00d_gu355_6dcfb67c}`

# endianness

Source code không có gì chú ý lắm

Cái quan trọng là tìm hiểu xem <b>little and big endian</b> là gì https://viblo.asia/p/little-endian-vs-big-endian-E375z0pWZGW

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/d3713e36-c92e-4ac9-8047-264b513fe066)

Ssh server

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/9af0d542-4544-4bd2-9fe7-c7dd5efdc975)

Vì little and big endian định dạng dưới dạng hex nên để giải được chúng ta có thể chuyển đổi `word` qua [ASCII table](https://fastbitlab.com/ascii-code/)

`zqmug --> lit: 67756d717a --> big: 7a716d7567`

Flag: `picoCTF{3ndi4n_sw4p_su33ess_28329f0a}`

# dont-you-love-banners

![image](https://github.com/vanniichan/CTF-WriteUp/assets/112863484/c3c5e7ea-4ade-4ce6-b8af-71f8a645637a)

Bài này có 2 cách giải: 
- Giải bằng hash trong /etc/shadow
- Sử dụng symlinks

Mình sẽ giải cách 2:

