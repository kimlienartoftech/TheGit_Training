# 1.Git là gì?
- **Git** là một **hệ thống kiểm soát phiên bản phân tán code nguồn mở**. Nó được thiết kế để xử lý các dự án từ nhỏ đến lớn với tốc độ và hiệu quả cao. Nó được phát triển để điều phối công việc giữa các developer. Kiểm soát phiên bản cho phép chúng ta theo dõi và làm việc cùng với các thành viên trong nhóm của chúng ta tại cùng một không gian làm việc.

# 2. Tại sao lại dùng Git
- **Tiết kiệm thời gian (save time)**  
	Git là công nghệ **nhanh như chớp**. Mỗi lệnh chỉ mất vài giây để thực thi nên chúng ta có thể tiết kiệm rất nhiều thời gian so với đăng nhập vào tài khoản GitHub và tìm hiểu các tính năng của nó.
- **Làm việc ngoại tuyến (offline working)**
    Một trong những lợi ích quan trọng nhất của Git là nó hỗ trợ **làm việc ngoại tuyến**. Nếu chúng ta đang gặp phải sự cố kết nối internet, nó sẽ không ảnh hưởng đến công việc của chúng ta. Trong Git, chúng ta có thể làm hầu hết mọi thứ cục bộ. So sánh, các CVS ​​khác như SVN bị hạn chế và thích kết nối với kho lưu trữ trung tâm hơn.
- **Hoàn lại sai lầm (undo mistakes)**
	Một lợi ích bổ sung của Git là chúng ta có thể **Hoàn tác** lỗi. Đôi khi hoàn tác có thể là một lựa chọn cứu tinh cho chúng ta. Git cung cấp tùy chọn hoàn tác cho hầu hết mọi thứ.
- **Theo dõi các thay đổi (Track changes)**
    Git tạo điều kiện với một số tính năng thú vị như **Diff, Log** và **Status** , cho phép chúng ta theo dõi các thay đổi để chúng ta có thể **kiểm tra trạng thái, so sánh** các file hoặc chi nhánh của mình.

# 3. Tải xuống Git
 - Trước khi tải về Git thì bạn cần có một tài khoản [Github](https://github.com)
 - Git có sẵn tại hầu hết phiên bản của MacOS và Linus. Chính vì vậy, người dùng của hai hệ điều hành này không cần thiết phải tải xuống. Tuy nhiên đây là [cách để tải Git về trên MacOS](https://git-scm.com/download/mac)
 - Để tại về Git trên Windows cũng khá đơn giản, bạn có thể sử dụng [hướng dẫn sau tại trang chủ của Git](https://git-scm.com/download/win)
 - Để kiểm tra xem Git được tải thành công chưa bạn có thể sử dụng lệnh ```git --version``` ở terminal hoặc cmd

 # 4. Clone một repository
- Để clone một repository bạn mong muốn hãy sử dụng lệnh ```git clone``` đi cùng với đường link định dạng https hoặc ssh của repo mà bạn muốn clone

```
# Phương thức HTTPS
git clone https://github.com/kimlienartoftech/TheGit_Training
# Còn đây là SSH
git clone git@github.com:kimlienartoftech/TheGit_Training.git
```
 - Còn một phương thức khác là sử dụng GitCLI nhưng chúng ta sẽ không đề cập đến đây vì không phổ biến

 - Việc clone này sẽ đồng thời clone toàn bộ lịch sử chỉnh sửa của repo đó => Nếu repo có dung lượng lớn hoặc có nhiều chỉnh sửa có thể sử dụng phương thức sau 
```
git clone (link to the repo) --depth 1
```
 - Sau đó thì bạn có thể dùng nhiều phương thức để mở repo đó lúc này đang ở dưới dạng Folder trong máy bạn

 # 5. Các lệnh cơ bản trong Git
 **1. Kiểm tra trạng thái branch, các file chưa được commit hoặc các file đã commit**

```
git status
```

 **2. Thêm thay đổi ở các tệp**
```
git add (file's name)
```
 - Tuy nhiên nếu số lượng file thay đổi là quá lớn bạn có thể sử dụng một trong hai lệnh sau để thêm toàn bộ file
```
git add --all
git add .
```
 **3. Commit**
 - Git commit có tác dụng lưu thay đổi ở các file và sinh một mã hash duy nhất - chìa khóa cho lần commit đó (lưu ý rằng các thay đổi ở file này hoàn toàn chưa tồn tại ở GitHub)
 - ```git commit``` phải đi kèm với một hậu tố là ```-m``` hay là viết tắt của message. Điều này sẽ giúp bạn có những ghi chú về các thay đổi trong các file
 - Các tin nhắn này là chìa khóa giúp cho mọi người hiểu bạn đã thay đổi những gì chính vì vậy nó cần đảm bảo rằng tin nhắn ngắn gọn và đầy đủ thông tin cần thiết
```
git commit -m "Message"
```
 **4. Các nhánh (Branches)**
 - Như đúng cái tên của nó, nhánh là một tính năng của Git cho phép nhiều người tạo ra các phiên bản khác nhau của phần mềm và thực hiện chỉnh sửa mà không ảnh hưởng đến nhánh chính (hay còn được biết đến với cái tên của nhánh sản phẩm)
 - Người dùng có thể làm việc ở nhiều nhánh khác nhau một cách nhanh chóng và không gây ảnh hưởng tới nhau
 - Sau khi thực hiện các công việc xong, qua quá trình kiểm tra các nhánh có thể merge (hợp) vào với nhánh chính

 Để tạo một branch mới 
 ```
 git branch (branch's name)
 ```
 Liệt kê các branch
 ```
 git branch
 ```
 Chuyển tới một branch khác
 ```
 git checkout (branch you want to move to)
 ```
 Merge hai branch khác nhau. 
 ```
 # Phải ở hai branch khác nhau
 git checkout master
 git merge (branch's name)
 ```
 - Tuy nhiên điều này sẽ dẫn tới một vấn đề khác: Merge conflict. Merge conflict xảy ra khi hai người cùng thay đổi vào một file nhưng lại có những thay đổi khác nhau. Khi đó Git sẽ không thể xác định thay đổi nào là chính xác và bạn sẽ phải mở IDE và tìm hiểu sự khác nhau giữa những thay đổi đó

 - Đây là một vấn đề khá khó, vì vậy bạn có thể tìm hiểu thêm

 Xóa hai branch khác nhau
 ```
 git branch -d (branch's name)
 ```
 # 6. Git và GitHub
 **1. Git pull**

 - Git pull có chức năng cập nhật repo ở local của người dùng đồng bộ với repo trên máy chủ. Có thể hiểu ```git pull``` là sự kết hợp của ```fetch```, ```merge```. Để hiểu rõ hơn, hãy cùng xem cách ```fetch``` và ```merge``` hoạt động. 

 - ```fetch```: sẽ theo dõi những gì đã xảy ra trên GitHub
 
 - ```merge```: sẽ merge những thay đổi đó vào local
 ```
 git pull
 ```

 **2. Git push**
 
 - Đẩy những thay đổi ở local lên GitHub
 ```
 git push
 ```

 - Ngoài ra bạn có thể dùng lệnh để buộc Git đẩy lên GitHub
 ```
 git push -f (--force)
 ```
 
 **3. Pull request**

 - Nhiều repo yêu cầu bạn phải fork (tính năng của GitHub cho phép người dùng sao chép một repo của một cá nhân bất kì về repo của mình sau đó thực hiện các thay đổi như một repo riêng biệt). Từ các repo được fork này bạn có thể mở các pull request tới các repo gốc tới các nhánh. Từ đó mọi người có thể xem code của bạn rồi đưa ra các bình luận, chỉnh sửa. Sau khi chỉnh sửa xong sẽ được merge vào nhánh rồi tiếp tục chỉnh sửa để merge vào nhánh chính

 # .gitignore 

  - Đây là một định dạng file đặc biệt nhằm thông báo cho Git về những file không muốn được đẩy lên một cách công khai lên GitHub (file chứa dữ liệu quan trọng, file do ngôn ngữ lập trình tự sinh ra, ...)
  - Các file nằm trong .gitignore phải đảm bảo rằng không liên quan trực tiếp tới code hoặc có thể tự sinh ra bởi các ngôn ngữ lập trình ở mọi thiết bị

  # Ví dụ
  - Ở đây chúng ta sẽ xem một quy trình làm việc với Git giả định
```
# Clone repo từ GitHub về local
$ git clone git@github.com:kimlienartoftech/TheGit_Training.git                                        
Cloning into 'TheGit_Training'...
remote: Enumerating objects: 26, done.
remote: Counting objects: 100% (26/26), done.
remote: Compressing objects: 100% (18/18), done.
remote: Total 26 (delta 3), reused 22 (delta 2), pack-reused 0
Receiving objects: 100% (26/26), 6.37 KiB | 6.37 MiB/s, done.
Resolving deltas: 100% (3/3), done.

# Di chuyển tới folder repo
$ cd TheGit_Training

# Kiểm tra trạng thái
$ git status                                                                         
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean

# Thêm những thay đổi ở file
$ git add .

#Lưu vào lịch sử cùng thông báo "More contents
$ git commit -m "More contents"
[main 5b023ed] More contents
 1 file changed, 64 insertions(+), 9 deletions(-)

# Đồng bộ GitHub với local
$ git push 
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 1.87 KiB | 1.87 MiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To github.com:kimlienartoftech/TheGit_Training.git
   bd60c92..5b023ed  main -> main
```

- Tiếp theo đây là một phần của một máy khác khi tương tác với repo đó tuy nhiên local này vẫn chưa được merge với những cập nhật ở phía trên
```
# Cập nhật thay đổi trên GitHub
$ git pull
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 1), reused 3 (delta 1), pack-reused 0
Unpacking objects: 100% (3/3), 1.85 KiB | 1.85 MiB/s, done.
From github.com:kimlienartoftech/TheGit_Training
   bd60c92..5b023ed  main       -> origin/main
Updating bd60c92..5b023ed
Fast-forward
 README.md | 73 ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++---------
 1 file changed, 64 insertions(+), 9 deletions(-)
```


# Đây là một branch hoàn toàn mới! Hãy commit file tên mình.txt vàp nhé
