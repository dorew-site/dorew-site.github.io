# dorew-site.github.io
> Code Upload file lên IPFS cho DorewSite

Demo:

![](https://i.imgur.com/JTt9yzB.png)

Sử dụng https://nft.storage để upload lên ipfs ==> **lấy API Key của** https://nft.storage

Đây là Template mặc định khi bạn mới bắt đầu sử dụng DorewSite, nếu bạn không may đã làm thất lạc nó, bạn có thể cài đặt lại như sau:
- Tải zip bên dưới về

![](https://i.imgur.com/pRzMfoz.png)


- Truy cập: **/cms** -> Đăng nhập -> **Sao lưu** -> **Tải lên template** -> Chọn zip vừa tải về -> **Sử dụng**

![](https://i.imgur.com/nsjVRWx.png)


![](https://i.imgur.com/OL6qhsw.png)


![](https://i.imgur.com/zr41KOA.png)


![](https://i.imgur.com/PQarWGW.png)


- Truy cập **phpMyAdmin**, tạo bảng **ipfs** có cấu trúc như hình:

![](https://i.imgur.com/4hZL8Ue.png)


Hoặc tạo bảng trên với code twig:

```twig
{% set time = 'int(11) NOT NULL' %}
{% set filename = 'varchar(255) NOT NULL' %}
{% set filesize = 'int(11) NOT NULL' %}
{% set cid = 'varchar(255) NOT NULL' %}
{% set password = 'varchar(255) NOT NULL' %}
{% set passphrase = 'varchar(255) NOT NULL' %}
{% set ip = 'varchar(255) NOT NULL' %}
{% set user_agent = 'varchar(255) NOT NULL' %}

{% set structure = {'time':time,'filename':filename,'filesize':filesize,'CID':cid,'password':password,'passphrase':passphrase,'ip':ip,'user_agent':user_agent} %}

{% do create_table_with_column('ipfs', structure) %}
```


- Truy cập **/cms**, mở file **index**, sửa lại **API Key** của bạn.