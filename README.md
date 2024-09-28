# **Lập trình vi điều khiển Esp32 sử dụng framework Esp-Idf** #
## Esp32 Dev Board Datasheet ##
![image](https://github.com/user-attachments/assets/5c1e2350-9764-4ce3-913f-e47da42b0f7d)
## **Cài đặt phần mềm** ##
* Download phiên bản mới nhất của Espressif qua gitHub (cho Windows)"
[Espressif gitHub](https://github.com/espressif/esp-idf)
* Sau khi cài đặt phần mềm sẽ tạo ra cho chúng ra 2 trình command prompt để hiển thị mỗi khi lập trình cho Esp32:
![image](https://github.com/user-attachments/assets/81a37dcb-e5cb-4623-b240-5a10183e09de)
> Tốt nhất khi cài đặt hãy tạo riêng 1 folder cho phần mềm để đễ dàng kiểm soát
> Trong framework tải về nhà phát hành đã có sẵn những project nhỏ bên trong để chúng ta thực hành

## **Thực hiện cấu hình và build project blink đầu tiên** ##
1. Vào trong folder của Esp32 đã cài đặt -> vào thư mục framworks -> `esp-idf` -> `examples` -> `get started`
2. Copy và Paste chương trình `blink` bên trong ra ngoài song song với folder chính của Esp32:
   ![image](https://github.com/user-attachments/assets/1e24fe1c-2282-41a1-b7f6-aedcffd56039)
3. Mở command prompt của Esp32, sau đó cd vào folder blink (chúng ta có thể dùng Visual Studio Code hoặc bất cứ trình editor code nào để mở tất cả các file code trong folder này lên), ngoài ra nếu muốn quay lại folder cũ thì gõ `cd..`
4. Vào lại command prompt và gõ `ls` để xem toàn bộ danh sách file có trong thư mục blink
5. Tiếp theo dùng lệnh `idf.py menuconfig` để chạy giao điện cấu hình cho Esp32
> idf.py: Đây là một công cụ dòng lệnh giúp quản lý toàn bộ quá trình phát triển, từ khởi tạo dự án, cấu hình, biên dịch, flash mã, đến theo dõi nhật ký từ ESP32.
6. Sau khi chạy xong toàn bộ, màn hình command sẽ hiển thị giao diện như sau: 
![image](https://github.com/user-attachments/assets/840fe240-b7dc-4f69-b536-853400eaa8e4)
7. Trong mục "Serial flasher config", chỉnh "flash size" thành 4MB. Trong "Example configuration" chuyển chân Blink GPIO thành chân 2 (lý do vì trong bản diagram của Esp32 được thiết lập sẵn chân 2 là chân led blink)
8. Sau đó thoát giao diện config bằng nút "esc" trong bàn phím
9. Sau đó dùng lệnh `idf.py build` để thực hiện build dự án blink
> Bản chất viêc idf.py build trên command của Esp32 là máy sẽ chạy "Makefile" bên trong folder blink
![image](https://github.com/user-attachments/assets/0fb86ab0-1f1b-42ce-b797-72e2b0049cf2)
> Ảnh trên cho thấy, nó build ra các file bootloader.bin, partition_table.bin, blink.bin(đây chính là cái app của chúng ta). Những cái vùng flash 0x1000,... như chúng ta thấy bên trên là các vùng bộ nhớ mà các file được nạp vào.
10. Bước quan trọng nhất để nạp chương trình vào vi điều khiển là dùng lệnh `idf.py -p COM(SỐ..)flash monitor `, chương trình sẽ ngay lập tức nạp vào bộ nhớ flash của mcu, vừa nạp vừa giữ nút Boot trên vi điều khiểnập trình vi điều khiển Esp32 sử dụng framework Esp-Idf** #

## **Cài đặt phần mềm** ##
* Download phiên bản mới nhất của Espressif qua gitHub (cho Windows)"
[Espressif gitHub](https://github.com/espressif/esp-idf)
* Sau khi cài đặt phần mềm sẽ tạo ra cho chúng ra 2 trình command prompt để hiển thị mỗi khi lập trình cho Esp32:
![image](https://github.com/user-attachments/assets/81a37dcb-e5cb-4623-b240-5a10183e09de)
> Tốt nhất khi cài đặt hãy tạo riêng 1 folder cho phần mềm để đễ dàng kiểm soát
> Trong framework tải về nhà phát hành đã có sẵn những project nhỏ bên trong để chúng ta thực hành

## **Thực hiện cấu hình và build project blink đầu tiên** ##
1. Vào trong folder của Esp32 đã cài đặt -> vào thư mục framworks -> `esp-idf` -> `examples` -> `get started`
2. Copy và Paste chương trình `blink` bên trong ra ngoài song song với folder chính của Esp32:
   ![image](https://github.com/user-attachments/assets/1e24fe1c-2282-41a1-b7f6-aedcffd56039)
3. Mở command prompt của Esp32, sau đó cd vào folder blink (chúng ta có thể dùng Visual Studio Code hoặc bất cứ trình editor code nào để mở tất cả các file code trong folder này lên), ngoài ra nếu muốn quay lại folder cũ thì gõ `cd..`
4. Vào lại command prompt và gõ `ls` để xem toàn bộ danh sách file có trong thư mục blink
5. Tiếp theo dùng lệnh `idf.py menuconfig` để chạy giao điện cấu hình cho Esp32
> idf.py: Đây là một công cụ dòng lệnh giúp quản lý toàn bộ quá trình phát triển, từ khởi tạo dự án, cấu hình, biên dịch, flash mã, đến theo dõi nhật ký từ ESP32.
6. Sau khi chạy xong toàn bộ, màn hình command sẽ hiển thị giao diện như sau: 
![image](https://github.com/user-attachments/assets/840fe240-b7dc-4f69-b536-853400eaa8e4)
7. Trong mục "Serial flasher config", chỉnh "flash size" thành 4MB. Trong "Example configuration" chuyển chân Blink GPIO thành chân 2 (lý do vì trong bản diagram của Esp32 được thiết lập sẵn chân 2 là chân led blink)
8. Sau đó thoát giao diện config bằng nút "esc" trong bàn phím
9. Sau đó dùng lệnh `idf.py build` để thực hiện build dự án blink
> Bản chất viêc idf.py build trên command của Esp32 là máy sẽ chạy "Makefile" bên trong folder blink
![image](https://github.com/user-attachments/assets/0fb86ab0-1f1b-42ce-b797-72e2b0049cf2)
> Ảnh trên cho thấy, nó build ra các file bootloader.bin, partition_table.bin, blink.bin(đây chính là cái app của chúng ta). Những cái vùng flash 0x1000,... như chúng ta thấy bên trên là các vùng bộ nhớ mà các file được nạp vào.
10. Bước quan trọng nhất để nạp chương trình vào vi điều khiển là dùng lệnh `idf.py -p COM(SỐ..)flash monitor `, chương trình sẽ ngay lập tức nạp vào bộ nhớ flash của mcu, vừa nạp vừa giữ nút Boot trên vi điều khiển:
![image](https://github.com/user-attachments/assets/1bc6a018-3c25-4228-93d7-d2be24d1e4b6)
* Sau khi màn hình hiển thị ra dòng như sau:
  ![image](https://github.com/user-attachments/assets/bb562041-4b73-4902-a94a-514e729c436a)
### Như vậy là đèn đã blink thành công ###
* Để thoát chương trình trên command, ta dùng tổ hợp phím "Ctrl + }" để thoát 





