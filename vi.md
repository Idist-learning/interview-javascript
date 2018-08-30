
[Source](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-functional-programming-7f218c68b3a0 "Permalink to Master the JavaScript Interview: What is Functional Programming?")

# Làm chủ buổi phỏng vấn về javascript: Lập trình hướng function là gì?

![][1]

Kiến trúc Synth — Orihaus (CC BY 2.0)

> "Làm chủ buổi phỏng vấn về JavaScript" là một loạt các bài viết được thiết kế để chuẩn bị cho các ứng viên về các câu hỏi phổ biến mà họ có khả năng gặp phải khi đăng ký vị trí JavaScript từ mức vừa đến mức cao hơn. Đây là những câu hỏi thường xuyên được sử dụng trong các cuộc phỏng vấn thực sự.

Lập trình theo hướng chức năng là một chủ đề thực sự nóng trong thế giới JavaScript. Vài năm trước, chỉ vài lập trình viên JavaScript biết lập trình hàm là gì, nhưng mỗi codebase của các ứng dụng lớn mà tôi đã thấy trong 3 năm qua đã sử dụng nhiều ý tưởng về lập trình hàm.

**Lập trình hướng chức năng** (thường được viết tắt là FP) là quá trình xây dựng phần mềm bằng cách xây dựng **hàm thuần túy**, tránh **chia sẻ dữ liệu có thể thay đổi trạng thái** và **các hiệu ứng phụ**. Lập trình hướng chức năng là sử dụng **khai báo** thay vì **mệnh lệnh**, và trạng thái của ứng dụng được truyền qua các hàm thuần túy. Ngược lại với lập trình hướng đối tượng, nơi mà trạng thái của ứng dụng thường được chia sẻ và được đóng gói với các phương thức trong các đối tượng.

Lập trình hướng chức năng là một **mô hình lập trình**, có nghĩa nó là một cách suy nghĩ về việc xây dựng phần mềm dựa trên một số nguyên tắc cơ bản, xác định (được liệt kê ở trên). Các ví dụ khác về mô hình lập trình bao gồm lập trình hướng đối tượng và lập trình thủ tục.

Code hướng chức năng có xu hướng ngắn gọn hơn, dễ dự đoán hơn và dễ kiểm tra hơn code hướng thủ tục hoặc đối tượng - nhưng nếu bạn không quen với nó và các pattern phổ biến liên kết với nó, code hướng chức năng cũng có thể dày đặc hơn và tài liệu liên quan có thể khó hiểu đối với người mới tiếp xúc.

Nếu bạn bắt đầu tìm hiểu về điều khoản trong lập trình chức năng, bạn sẽ nhanh chóng  gặp những trở ngại có thể rất đáng sợ cho người mới bắt đầu. Để khẳng định rằng nó có một lộ trình học tập là một cách nói nghiêm túc. Nhưng nếu bạn đã lập trình JavaScript trong một thời gian, rất có thể là bạn đã sử dụng rất nhiều concept và utility của lập trình hướng  chức năng trong phần mềm thực tế của bạn.

> Đừng để tất cả những khái niệm mới làm bạn sợ hãi. Nó dễ hơn rất nhiều so với những gì bạn nghe được.


The hardest part is wrapping your head around all the unfamiliar vocabulary. There are a lot of ideas in the innocent looking definition above which all need to be understood before you can begin to grasp the meaning of functional programming:

Phần khó nhất là bạn nghĩ tới là các khái niệm không quen thuộc. Có rất nhiều ý tưởng về việc tìm kiếm các định nghĩa vô nghĩa ở trên trong khi mọi thứ cần phải được hiểu trước khi bạn có thể bắt đầu nắm bắt ý nghĩa của lập trình hướng chức năng:

* Hàm thuần tuý
* Thành phần chức năng
* tránh chia sẻ trạng thái
* tránh biến đổi trạng thái
* tránh các hiệu ứng phụ

Nói cách khác, nếu bạn muốn biết về lập trình hướng chức năng trong thực tế, bạn phải bắt đầu với việc tìm hiểu về những khái niệm cốt lõi.

Một **hàm thuần tuý** là hàm bao gồm:
* Với cùng các yếu tố đầu vào, luôn trả về cùng một đầu ra, và
* Không có các hiệu ứng phụ

Các hàm thuần túy có rất nhiều thuộc tính quan trọng trong lập trình hàm, bao gồm **tính minh bạch khi tham chiếu** (bạn có thể thay thế một hàm gọi với giá trị kết quả của nó mà không thay đổi ý nghĩa của chương trình). Đọc ["Hàm thuần túy là gì?"] [2] để biết thêm chi tiết.

**Thành phần chức năng** là quá trình kết hợp hai hoặc nhiều chức năng để tạo ra một chức năng mới hoặc thực hiện một số tính toán. Ví dụ, thành phần `f. g` (dấu chấm có nghĩa là "composed with") tương đương với `f (g (x))` trong JavaScript. Hiểu biết về thành phần chức năng là một bước quan trọng hướng tới sự hiểu biết cách một phần mềm được xây dựng bằng việc sử dụng lập trình hướng chức năng. Đọc ["Thành phần chức năng là gì?"] [3] để biết thêm.

### Trạng thái được chia sẻ

** Trạng thái chia sẻ ** là bất kỳ biến, đối tượng hoặc không gian bộ nhớ nào tồn tại trong một phạm vi chia sẻ hoặc thuộc tính của đối tượng được truyền giữa các phạm vi. Một phạm vi chia sẻ có thể bao gồm phạm vi toàn cục hoặc phạm vi trong hàm. Thông thường, trong lập trình hướng đối tượng, các đối tượng được chia sẻ giữa các phạm vi bằng cách thêm các thuộc tính cho các đối tượng khác.

Ví dụ, một trò chơi máy tính có thể có một đối tượng chính của trò chơi, với các nhân vật và các mục trong trò chơi được lưu trữ dưới dạng các thuộc tính thuộc sở hữu của đối tượng đó. Lập trình chức năng tránh trạng thái chia sẻ - thay vào đó dựa vào cấu trúc dữ liệu không thay đổi và tính toán thuần túy để lấy dữ liệu mới từ dữ liệu hiện có. Để biết thêm chi tiết về cách phần mềm chức năng có thể xử lý trạng thái ứng dụng, hãy xem ["10 mẹo để có cấu trúc Redux tốt hơn"] [4].

Vấn đề của chia sẻ cá trạng thái là để hiểu được tác động của một hàm, bạn phải biết toàn bộ lịch sử của mọi biến chia sẻ mà hàm sử dụng hoặc tác động.

Hãy tưởng tượng bạn có một đối tượng người dùng cần lưu. Hàm `saveUser ()` của bạn tạo một yêu cầu tới một API trên máy chủ. Trong khi điều đó xảy ra, người dùng thay đổi hình ảnh hồ sơ của họ bằng `updateAvatar ()` và kích hoạt một yêu cầu `saveUser ()` khác. Khi lưu, máy chủ sẽ gửi lại một đối tượng người dùng chuẩn để thay thế bất kỳ thứ gì trong bộ nhớ để đồng bộ hóa với các thay đổi xảy ra trên máy chủ hoặc để đáp ứng các cuộc gọi API khác.

Thật không may, phản hồi thứ hai nhận được trước phản ứng đầu tiên, vì vậy khi phản ứng đầu tiên (hiện đã lỗi thời) được trả về, ảnh hồ sơ mới bị xóa sổ trong bộ nhớ và được thay thế bằng thẻ cũ. Đây là một ví dụ về race condition - một lỗi rất phổ biến liên quan đến trạng thái được chia sẻ.

Một vấn đề phổ biến khác liên quan đến trạng thái chia sẻ là việc thay đổi thứ tự mà các hàm được gọi có thể gây ra một loạt các lỗi vì các hàm hoạt động trên các trạng thái được chia sẻ phụ thuộc vào thời gian:

Ví dụ về thời gian phụ thuộc

Khi bạn tránh việc chia sẻ trạng thái, thời gian và thứ tự của các cuộc gọi hàm không thay đổi kết quả của việc gọi hàm. Với các hàm thuần túy, được cung cấp cùng một đầu vào, bạn sẽ luôn nhận được cùng một đầu ra. Điều này làm cho các cuộc gọi hàm hoàn toàn độc lập với các cuộc gọi hàm khác, có thể đơn giản hóa triệt để các thay đổi và tái cấu trúc. Mỗi thay đổi trong mỗi chức năng, hoặc thời gian của một cuộc gọi chức năng sẽ không chồng lên nhau và phá vỡ các phần khác của chương trình.

Trong ví dụ trên, chúng ta sử dụng `Object.assign ()` và truyền vào một đối tượng rỗng làm tham số đầu tiên để sao chép các thuộc tính của `x` thay vì thay đổi nó tại chỗ. Trong trường hợp này, nó sẽ tương đương với việc tạo một đối tượng mới ngay từ đầu, không có `Object.assign ()`, nhưng đây là một pattern phổ biến trong JavaScript để tạo ra các bản sao của trạng thái hiện tại thay vì sử dụng các đột biến như ví dụ đầu tiên.

Nếu bạn xem xét kỹ các câu lệnh `console.log ()` trong ví dụ này, bạn sẽ thấy một cái gì đó mà tôi đã đề cập: thành phần hàm. Nhớ lại từ trước, thành phần hàm trông giống như sau: `f (g (x))`. Trong trường hợp này, chúng ta thay thế `f ()` và `g ()` bằng `x1 ()` và `x2 ()` cho thành phần: `x1. x2`.

Tất nhiên, nếu bạn thay đổi thứ tự của bố cục, đầu ra sẽ thay đổi. Thứ tự của các hành động rất quan trọng. `f (g (x))` không phải lúc nào cũng bằng `g (f (x))`, nhưng những gì không quan trọng nữa là những gì xảy ra với các biến bên ngoài hàm - và đó là một vấn đề lớn. Với hàm số không thuần tuý, bạn không thể hiểu đầy đủ chức năng của một hàm trừ khi bạn biết toàn bộ lịch sử của mọi biến mà hàm sử dụng hoặc ảnh hưởng.

Xóa phụ thuộc thời gian cuộc gọi chức năng và bạn loại bỏ toàn bộ các lỗi tiềm ẩn.

### Tính bất biến

Một đối tượng **không thay đổi** là một đối tượng không thể sửa đổi sau khi nó được tạo ra. Ngược lại, một đối tượng **có thể thay đổi** là bất kỳ đối tượng nào có thể được sửa đổi sau khi nó được tạo ra.

Tính bất biến là một khái niệm trung tâm về lập trình chức năng bởi vì không có nó, luồng dữ liệu trong chương trình của bạn bị mất. Lịch sử của state sẽ bị mất và các lỗi lạ có thể xâm nhập vào phần mềm của bạn. Để biết thêm về tầm quan trọng của bất biến, hãy xem ["Người Dao bất biến."] [5]

Trong JavaScript, điều quan trọng là không nhầm lẫn `const`, với bất biến. `const` tạo ra một ràng buộc tên biến mà không thể được gán lại sau khi tạo. `const` không tạo ra các đối tượng bất biến. Bạn không thể thay đổi đối tượng mà ràng buộc đề cập đến, nhưng bạn vẫn có thể thay đổi các thuộc tính của đối tượng, có nghĩa là các ràng buộc được tạo bằng `const` là có thể thay đổi hoặc không thay đổi.

Các vật thể bất biến không thể thay đổi được. Bạn có thể làm cho một giá trị thực sự bất biến bằng cách đóng băng sâu đối tượng. JavaScript có một phương thức đóng băng mộtđối tượng rất sâu:

Nhưng các vật thể bị đóng băng chỉ là không thay đổi bề ngoài. Ví dụ, đối tượng sau đây có thể thay đổi:

Như bạn có thể thấy, các thuộc tính nguyên thủy cấp cao nhất của một đối tượng bị đóng băng thì không thể thay đổi, nhưng bất kỳ thuộc tính nào cũng là một đối tượng (bao gồm mảng, vv…) vẫn có thể bị đột biến - vì vậy ngay cả đối tượng bị đóng băng cũng không thay đổi trừ khi bạn đi bộ toàn bộ cây đối tượng và đóng băng mọi thuộc tính đối tượng.

Trong nhiều ngôn ngữ lập trình chức năng, có cấu trúc dữ liệu bất biến đặc biệt gọi là ** cấu trúc dữ liệu trie ** (phát âm là "cây") được đóng băng sâu - nghĩa là không có thuộc tính nào có thể thay đổi, bất kể mức độ của thuộc tính trong hệ thống phân cấp đối tượng .

Các nhiệm vụ sử dụng ** chia sẻ cấu trúc ** để chia sẻ các vị trí bộ nhớ tham chiếu cho tất cả các phần của đối tượng không thay đổi sau khi đối tượng đã sao chép một toán tử, sử dụng ít bộ nhớ hơn và cho phép cải thiện hiệu suất đáng kể đối với một số loại hoạt động.

Ví dụ, bạn có thể sử dụng so sánh nhận dạng tại gốc của cây đối tượng để so sánh. Nếu danh tính giống nhau, bạn không phải đi bộ cả cây để kiểm tra sự khác biệt.

Có một số thư viện trong JavaScript tận dụng các cố gắng, bao gồm [Immutable.js] [6] và [Mori] [7].

Tôi đã thử nghiệm với cả hai, và có xu hướng sử dụng Immutable.js trong các dự án lớn đòi hỏi một lượng đáng kể trạng thái bất biến. Để biết thêm về điều đó, hãy xem ["10 Lời khuyên cho Kiến trúc Redux Tốt hơn"] [4].

### Hiệu ứng phụ

Một hiệu ứng phụ là bất kỳ thay đổi trạng thái ứng dụng nào có thể quan sát được bên ngoài hàm được gọi ngoài giá trị trả về của nó. Các tác dụng phụ bao gồm:

* Sửa đổi bất kỳ biến bên ngoài hoặc thuộc tính đối tượng nào (ví dụ: biến toàn cầu hoặc biến trong chuỗi phạm vi hàm chính)
* Đăng nhập vào bảng điều khiển
* Viết lên màn hình
* Viết vào một tập tin
* Ghi vào mạng
* Kích hoạt bất kỳ quá trình bên ngoài nào
* Gọi bất kỳ chức năng nào khác có phản ứng phụ

Tác dụng phụ chủ yếu là tránh trong lập trình chức năng, làm cho hiệu quả của một chương trình dễ hiểu hơn nhiều, và dễ dàng hơn nhiều để kiểm tra.

Haskell và các ngôn ngữ chức năng khác thường tách biệt và đóng gói các hiệu ứng phụ từ các hàm thuần túy bằng [** monads **] [8]. Chủ đề của các monads là đủ sâu để viết một cuốn sách, vì vậy chúng tôi sẽ lưu nó cho sau này.

Những gì bạn cần biết ngay bây giờ là các tác vụ phụ cần phải được phân lập với phần còn lại của phần mềm của bạn. Nếu bạn giữ các hiệu ứng phụ tách biệt với phần còn lại của logic chương trình, phần mềm của bạn sẽ dễ dàng hơn để mở rộng, tái cấu trúc, gỡ lỗi, kiểm tra và bảo trì.

Đây là lý do mà hầu hết các khung công tác front-end khuyến khích người dùng quản lý hiển thị trạng thái và thành phần trong các mô-đun riêng lẻ, tách biệt nhau.
### Reusability Thông qua các hàm bậc cao

Lập trình chức năng có xu hướng sử dụng lại một tập hợp các tiện ích chức năng phổ biến để xử lý dữ liệu. Lập trình hướng đối tượng có xu hướng colocate phương pháp và dữ liệu trong các đối tượng. Những phương pháp colocated chỉ có thể hoạt động trên loại dữ liệu mà chúng được thiết kế để hoạt động và thường chỉ có dữ liệu chứa trong cá thể đối tượng cụ thể đó.

Trong lập trình chức năng, bất kỳ loại dữ liệu nào là trò chơi công bằng. Cùng một tiện ích `map ()` có thể ánh xạ đối tượng, chuỗi, số hoặc bất kỳ kiểu dữ liệu nào khác vì nó lấy hàm làm đối số xử lý thích hợp loại dữ liệu đã cho. FP rút ra thủ thuật tiện ích chung của nó bằng cách sử dụng ** các hàm bậc cao hơn **.

JavaScript có ** các hàm lớp đầu tiên **, cho phép chúng ta xử lý các hàm như dữ liệu - gán chúng cho các biến, chuyển chúng đến các hàm khác, trả về chúng từ các hàm, v.v.

Hàm ** thứ tự cao hơn ** là bất kỳ hàm nào nhận hàm làm đối số, trả về hàm hoặc cả hai. Các hàm bậc cao thường được sử dụng để:
* Tóm tắt hoặc cô lập hành động, hiệu ứng hoặc điều khiển luồng không đồng bộ bằng cách sử dụng chức năng gọi lại, lời hứa, monads, v.v.
* Tạo các tiện ích có thể hoạt động trên nhiều loại dữ liệu khác nhau
* Áp dụng một phần chức năng cho các đối số của nó hoặc tạo ra một hàm được kết hợp với mục đích sử dụng lại hoặc thành phần hàm
* Lấy danh sách các hàm và trả về một số thành phần của các hàm đầu vào đó

#### Vùng chứa, Functors, Lists và Streams

Một functor là cái gì đó có thể được ánh xạ trên. Nói cách khác, nó là một container có một giao diện có thể được sử dụng để áp dụng một hàm cho các giá trị bên trong nó. Khi bạn thấy từ functor, bạn nên nghĩ "có thể điều chỉnh được".

Trước đó chúng ta đã biết rằng cùng một tiện ích `map ()` có thể hoạt động trên nhiều kiểu dữ liệu khác nhau. Nó làm điều đó bằng cách nâng hoạt động ánh xạ để làm việc với một API functor. Các hoạt động kiểm soát lưu lượng quan trọng được sử dụng bởi `map ()` tận dụng giao diện đó. Trong trường hợp của `Array.prototype.map ()`, vùng chứa là một mảng, nhưng các cấu trúc dữ liệu khác cũng có thể là các hàm functors - miễn là chúng cung cấp API ánh xạ.

Hãy xem cách `Array.prototype.map ()` cho phép bạn trừu tượng kiểu dữ liệu từ tiện ích ánh xạ để làm cho `map ()` có thể sử dụng được với bất kỳ kiểu dữ liệu nào. Chúng ta sẽ tạo một ánh xạ `double ()` đơn giản, chỉ đơn giản là nhân bất kỳ giá trị nào được truyền vào bởi 2:

Điều gì sẽ xảy ra nếu chúng ta muốn hoạt động trên các mục tiêu trong một trò chơi để tăng gấp đôi số điểm mà họ giành được? Tất cả những gì chúng ta phải làm là tạo ra một thay đổi tinh tế cho hàm `double ()` mà chúng ta truyền vào `map ()`, và mọi thứ vẫn hoạt động:

Khái niệm sử dụng các phép trừu tượng như hàm functors và các hàm bậc cao hơn để sử dụng các hàm tiện ích chung để thao tác với bất kỳ số lượng các kiểu dữ liệu khác nhau nào là quan trọng trong lập trình hàm. Bạn sẽ thấy một khái niệm tương tự được áp dụng trong [tất cả các cách khác nhau] [9].

> "Danh sách được biểu thị theo thời gian là một luồng".
Tất cả những gì bạn cần hiểu bây giờ là mảng và functors không phải là cách duy nhất khái niệm container và giá trị trong các container được áp dụng. Ví dụ, một mảng chỉ là một danh sách các thứ. Danh sách được biểu thị theo thời gian là luồng - vì vậy bạn có thể áp dụng cùng các loại tiện ích để xử lý luồng sự kiện đến - thứ mà bạn sẽ thấy rất nhiều khi bạn bắt đầu xây dựng phần mềm thực với FP.

### Tuyên bố so với mệnh lệnh

Lập trình hàm là một mô hình khai báo, có nghĩa là logic chương trình được thể hiện mà không mô tả rõ ràng việc kiểm soát luồng.

** Chương trình ** bắt buộc dành dòng mã mô tả các bước cụ thể được sử dụng để đạt được kết quả mong muốn - điều khiển luồng **: Cách thực hiện **.

** Các chương trình ** tuyên bố trừu tượng quá trình kiểm soát luồng, và thay vào đó chi tiêu các dòng mã mô tả luồng dữ liệu **: Điều gì ** cần làm. _How_ bị tóm tắt.

Ví dụ, ánh xạ ** mệnh lệnh ** này lấy một mảng các số và trả về một mảng mới với mỗi số nhân với 2:

Ánh xạ dữ liệu bắt buộc

Ánh xạ ** tuyên bố ** này thực hiện điều tương tự, nhưng tóm tắt điều khiển luồng bằng cách sử dụng tiện ích `Array.prototype.map ()` chức năng, cho phép bạn thể hiện rõ ràng luồng dữ liệu:

** Mã ** bắt buộc thường xuyên sử dụng các câu lệnh. Câu lệnh ** là một đoạn mã thực hiện một số hành động. Ví dụ về các câu lệnh thường được sử dụng bao gồm `for`,` if`, `switch`,` throw`, v.v ...

** Mã tuyên bố ** dựa nhiều hơn vào biểu thức. Biểu thức ** là một đoạn mã đánh giá một số giá trị. Biểu thức thường là một số kết hợp của các cuộc gọi hàm, giá trị và toán tử được đánh giá để tạo ra giá trị kết quả.

Đây là tất cả các ví dụ về các biểu thức:
    
    
    2 * 2
    doubleMap ([2, 3, 4])
    Math.max (4, 3, 2)

Thông thường trong mã, bạn sẽ thấy các biểu thức được gán cho một mã định danh, được trả về từ các hàm, hoặc được chuyển vào một hàm. Trước khi được chỉ định, trả về, hoặc được thông qua, biểu thức được đánh giá đầu tiên và giá trị kết quả được sử dụng.

### Phần kết luận

Ưu đãi lập trình chức năng:

* Chức năng thuần túy thay vì chia sẻ trạng thái & tác dụng phụ
* Tính không thay đổi đối với dữ liệu có thể thay đổi
* Chức năng thành phần trên kiểm soát dòng chảy bắt buộc
* Nhiều tiện ích chung, có thể sử dụng lại sử dụng các hàm bậc cao hơn để hành động trên nhiều loại dữ liệu thay vì các phương thức chỉ hoạt động trên dữ liệu được phân bổ của chúng
* Tuyên bố chứ không phải là mã bắt buộc (phải làm gì, thay vì cách thực hiện)
* Biểu thức trên báo cáo
* Container và chức năng bậc cao hơn trên đa hình ad-hoc

### Bài tập về nhà

Tìm hiểu và thực hành nhóm lõi chức năng bổ sung mảng chức năng này:

Sử dụng bản đồ để chuyển đổi mảng giá trị sau thành một mảng tên mục:

Sử dụng bộ lọc để chọn các mục có điểm lớn hơn hoặc bằng 3:

Sử dụng giảm để tổng hợp các điểm:

#### Khám phá chuỗi

### Nâng cao kỹ năng của bạn

[Học JavaScript với Eric Elliott] [10]. Nếu bạn không phải là thành viên, bạn đang bỏ lỡ!

![][11]

[1]: https://cdn-images-1.medium.com/max/1600/1*1OxglOpkZHLITbIKEVCy2g.jpeg
[2]: https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-pure-function-d1c076bec976
[3]: https://medium.com/javascript-scene/master-the-javascript-interview-what-is-function-composition-20dfb109a1a0
[4]: https://medium.com/javascript-scene/10-tips-for-better-redux-architecture-69250425af44
[5]: https://medium.com/javascript-scene/the-dao-of-immutability-9f91a70c88cd
[6]: https://github.com/facebook/immutable-js
[7]: https://github.com/swannodette/mori
[8]: https://en.wikipedia.org/wiki/Monad_%28functional_programming%29
[9]: https://github.com/fantasyland/fantasy-land
[10]: http://ericelliottjs.com/product/lifetime-access-pass/
[11]: https://cdn-images-1.medium.com/max/1600/1*3njisYUeHOdyLCGZ8czt_w.jpeg

  