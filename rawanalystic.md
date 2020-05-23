

By **[Erik Horus](https://github.com/ErikHorus1249)**
Date : 22/05/2020 

## Kết quả sau phân tích bằng AndroPyTool
![https://i.imgur.com/uPxOxMa.jpg](https://i.imgur.com/uPxOxMa.jpg)![](https://i.imgur.com/hSlJXqr.png)
### I. Một số yếu tố cần chú ý 
Sau khi thực hiện đủ 7 bước phân tích bằng AndroPyTool sẽ thu được các thư mục sau :
- [DroidBox_outputs](h)
- [Dynamic](h)
- [Features_files](h)
- [FlowDroid_outputs](h)
- [FlowDroid_processed](h)
- [samples](h)
- [VT_analysis](h)

và tất nhiên trong các thư mục này phải tồn tại các file dữ liệu đó là các .[**json**](h) và .[**csv**](h).

![](https://i.imgur.com/xBGlf7Q.png)
Duới đây là ví dụ cụ thể cho nội dung dữ liệu trong các folder là gì ? 

> 
    05af60ce8a8c3cd31682982122423ef3-analysis.json
Nằm trong thư mục `/Features_files` cụ thể thì đó là các  **API call** sau khi đã bị tách ra khỏi file json.

![](https://i.imgur.com/JPpNn6l.png)

Vậy những gì cần chú ý cho form thứ 2 về bài thực hành AndroPyTool môn an toàn hệ điều hành sẽ bắt đầu từ những file JSON này trước. Còn các file CSV sẽ khai thác sau. 

### II. Câu hỏi trong form thực hành lần 2 

Những câu hỏi liên quan đến cấu hình mình sẽ không nói trong bài này :> các bạn hãy tự tìm hiểu.

#### Cách 1. Trích xuất thủ công 
[Đường dẫn phân tích "permalink" của Virus total ?](h)
Khi vào thư mục `/VT_analysis` mở tệp **.json** duy nhất trong thư mục đó bằng một trình soạn thảo bất kì tìm bằng `Ctrl + F` từ khóa "permalink" sẽ lấy được link. Nó sẽ dẫn đến trang của Virus Total và hiển thị phân tích sơ lược về file APK mà bạn đã dùng dựa trên cơ sở dữ liệu của Virus Total. Khi trả lời form thì trích lấy cái link thôi :>

![](https://i.imgur.com/oQcI6x9.png)
![](https://i.imgur.com/1gE4Tes.png)

[Mã op-code nào được sử dụng nhiều nhất và ít nhất/ Tổng số op-code quan sát được ?](h)

Làm sao để biết mã op-code nào được dùng nhiều ít hay tổng số thì phải sử dụng file .json trong thư mục `/Features_files` có thể chọn một trong hai file **json** để lấy thông tin về op-code. Cách đơn giản nhất là quan sát đếm và cộng nhưng khá phiền cho ai lười và không tin tưởng vào khả năng tính toán của mình. Vậy nên chú ý vào cách trích xuất số 2 :>


![](https://i.imgur.com/kVsIdpe.png)

[Api call nào được sử dụng nhiều nhất và ít nhất/ Tổng số API call quan sát được ?](h)
Để lấy thông tin về API call cũng tương tự như op-code dữ liệu cũng quan sát ngay trong file json nằm trong thư mục `/Features_files` .


![](https://i.imgur.com/9iQ40AE.png)

[Chuỗi ký tự dài nhất trong đoạn mã ?](h)

Cũng tương tự như API calls hay Op-code , Strings cũng được quan sát ngay từ file json trong `/Features_files`.


#### Cách 2. Trích xuất "bán" thủ công  

Mình có viết sẵn một script bằng [Javascript](h) các bạn chỉ cần lấy đường dẫn của file json thêm vào là nó sẽ tự trích xuất ra những gì bạn cần ( không làm mà vẫn có ăn đấy :< ). Nhưng để chạy được thì máy bạn phải cài sẵn [**NodeJs**](https://github.com/ErikHorus1249/Guide-Documents/blob/master/Ubuntu/1.LamGiSauKhiCaiUbuntu.md) và install npm [**readline-sync**](https://www.npmjs.com/package/readline-sync). Thực ra thì do vội nên code cũng hơi sơ sài và cũng không phải clean code nên các bạn thông cảm. Ít ra thì nó sẽ giúp tính toán nhanh hơn đỡ phải ngồi đếm. Tất nhiên đối tượng để lấy đường dẫn vẫn là hai file json như trên cách 1 đã trình bày đó là :

- File json trong `/VT_analysis`
- File json trong `/Features_files`

vào hai thư mục trên và lấy path thôi.

**/VT_analysis**

![](https://i.imgur.com/8xSHIFX.png)

**/Features_files**

![](https://i.imgur.com/5YZrgp3.png)

sau đó mở **Terminal** lên và chạy file [**index.js**](h)  bằng lệnh :

> 
    $ node index.js
    
- Đây là khi nhập sai đường dẫn :< nên chú ý.

![](https://i.imgur.com/6A5BeA3.png)- Khi nhâp đúng đường dẫn từ hai thư mục trên thì kết quả nhận được như sau : 

![](https://i.imgur.com/D2dr74U.png)

Đầy đủ thông tin như vậy là xong :> 

#### Thân ái chào quyết thắng .

#### Tác giả  
- [**ErikHorus**](https://github.com/ErikHorus1249)



