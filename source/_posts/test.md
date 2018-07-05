title: Ninja Code
tags:
  - code
  - javascript
categories:
  - note
author: Oreki
date: 2018-06-05 17:10:00
---

Nếu coding giống như một trận chiến giữa programer và problem cần giải quyết thì, giống như những chiến binh thực thự, chúng ta tìm kiếm đạo (phương pháp chiến đấu) phù hợp cho chính mình. Trong bạt ngàn những đạo (những nguyên lý), kinh dịch (article trên blog của những blogger nổi tiếng), chú thích kinh nghiệm (những note, post được đông đảo dev `kip` lại),...đâu đó quanh đây vẫn tồn tại một đạo mà không mấy ai để ý đến nhưng số người theo thì đếm không kể hết. Có người đắc đạo hoàn toàn, có người một phần, tuy theo nhiều mức độ khác nhau nhưng tựu chung có thể coi đều là đồng đạo trong môn phái này :))


> Chú ý: Bài viết lược dịch từ [đây](https://javascript.info/ninja-code). Đối với tôi, không có từ nào nhận xét tốt hơn cho bản gốc của bài viết này ngoài 2 chữ `tuyệt vời` :)).

Trong khuôn khổ bài viết, đạo này được naming là __ninja đạo__ - người theo đạo được naming là các ninja (ninja đắc đạo là những ninja tuân thủ nghiêm ngặt theo những đạo lý được liệt kê trong bài viết này).

# Đạo lý trong ninja đạo

![Imgur](https://i.imgur.com/9gCBJvO.jpg)

Chúng ta sẽ cùng điểm qua những giáo lý chủ đạo của đạo phái này. (chú ý, source code sử dụng trong bài viết là javascript, tuy nhiên mở rộng ra nó có thể là bất cứ ngôn ngữ nào, bởi môn sinh theo học ninja đạo là vô biên)
<!-- more -->
> Rất nhiều môn sinh theo ninja đạo. Chỉ một số ít thành công.
>
> -- <cite>Confucius</cite>

## Ngắn gọn là đích đến của sự thông tuệ

Code của bạn __càng ngắn gọn, bạn càng thông minh__ hơn thằng ngồi ở block bên cạnh.

Lấy ví dụ, tất cả chúng ta từ khi bắt đầu học lập tình đều biết đến phép toán `?` và cách nó biến đổi biểu thức điều kiện if về dạng oneline kì diệu như thế nào.

Xem ví dụ bên dưới:

```java
// taken from a well-known javascript library
i = i ? i < 0 ? Math.max(0, len + i) : i : 0;
```

Một ninja đạt cảnh giới cao viết những block code tuyệt vời như vậy! Sẽ chẳng có vấn đề gì nếu nó nằm sâu ngàn lớp trong một thư viện __high performance__ nào đó, nhưng điều gì sẽ xảy ra nếu người động đến đoạn code này là một môn sinh trẻ tuổi? Hẳn là môn sinh non nớt đó sẽ phải bỏ ra kha khá thời gian để bắt được giá trị của `i` khi muốn debug đoạn code này. 

Và rồi đến khi không thể tìm ra lời giải thích thoả đáng cho cái lỗi hắn đang phải debug, hắn sẽ tìm đến bạn (một ninja cảnh giới cao hơn) để hỏi về nó, hãy nói với hắn "Ngắn hơn luôn tốt hơn!", mở cho anh ta con đường đến với ninja đạo.

## Biến số một chữ cái

> Người Dao ẩn mình bằng sự im lặng. Cái gì người Dao đã bắt đầu, chỉ người Dao biết cách kết thúc nó.
>
> -- <cite>Laozi (Tao Te Ching)</cite>

Đối với một ninja, không gì quan trọng hơn là kĩ năng ẩn mình. Vậy kĩ năng ẩn mình của một ninja đắc đạo thể hiện ở đâu? Nó thể hiện từ những thứ nhỏ nhất như là tên biến...

Đặt tên biến `một-chữ-cái` (như là `a`, `b` hay `c`) giúp các ninja thượng đẳng tăng tốc độ code một cách đáng kể!

Tên biến một chữ cái trong 1 block code giống như những ninja ẩn trốn trong rừng cây. Không ai có thể tìm ra họ! Kể cả công cụ search của editor (`ctrl+F` hoặc `cmd+F`) cũng phải đầu hàng trước những biến này. Mặt khác kể cả khi tìm ra, không ai (trừ gã `người Dao` bên trên) biết được ý nghĩa của biến `a` hay `b` đó là gì.

...Tuy nhiên vẫn có một ngoại lệ. Một ninja đắc đạo sẽ không bao giờ dùng biến một-chữ-cái như `i` để làm biến đếm trong vòng `for`. Lý do tại sao à, đơn giản là vì còn rất nhiều lựa chọn khác ngoài `i`, như `x` hay `y` chẳng hạn. 

Một ninja thực thụ sẽ không bao giờ để biến của anh ta dễ dàng bị bắt chỉ bởi dùng một chữ cái ai cũng biết như `i` được. Và đặc biệt, khi độ dài của vòng `loop` đó lên đến 1-2 trang (trang ở đây chỉ độ dài hiển thị source code trên một màn hình - nếu có thể, hãy cố gắng làm cho vòng for của bạn dài đến 3 trang, điều này giúp biến của bạn ẩn mình tốt hơn), khi đó bạn đã ngộ được nguyên lý để ẩn mình thực sự.

## Rút....gọn

Nếu team của bạn có quy định về cấm sử dụng biến một-chữ-cái hoặc tên-vô-nghĩa, hãy lách luật bằng cách rút gọn chúng.

Một số ví dụ như:
- list → lst.
- userAgent → ua.
- browser → brsr.
- …etc

Phải là một ninja đắc đạo hoặc là có trực giác tốt mới có thể hiểu được ý nghĩa ẩn giấu dưới những cái tên này. Hãy cố gắng rút gọn mọi thứ, nó là một lớp lọc rất tốt. Chỉ những người thực sự có năng lực mới có thể hiểu và có quyền động vào source code của bạn.

## Trừu tượng là mục tiêu

> The great square is cornerless </br>
> The great vessel is last complete, </br>
> The great note is rarified sound, </br>
> The great image has no form.
>
> -- <cite>Laozi (Tao Te Ching)</cite>

Khi đặt tên biến, trong hàng trăm lựa chọn, hay chọn cái tên trừu tượng nhất. Giống như obj, data, value, item, elem,...etc.

+ Cái tên lý tưởng để đặt cho bất cứ biến nào là `data`, lý do đơn giản vì nó là từ chính xác nhất để miêu tả nhiệm vụ của biến - lưu trữ data!

Nhưng làm thế nào khi cái tên `data` đã bị một ninja khác trong team dùng mất? Hãy thử `value`! Sau cùng thì mọi biến đều sẽ nhận một giá trị nào đó, nên cái tên value là hoàn toàn có thể chấp nhận được.

+ Mặt khác, bạn hoàn toàn có thể đặt tên cho biến bằng loại giá trị mà biến đó lưu. Ví dụ như: `str`, `num`,...

Một môn sinh trẻ tuổi có thể ban đầu cảm thấy lạc lõng và tự hỏi kĩ năng đặt tên biến như trên có thực sự giúp ích cho một ninja? Hãy tự tin và nói với anh ta "chắc chắn rồi!".

Thật vậy, những cái tên trên thực sự vẫn mang trong nó ý nghĩa: `str` thể hiện biến đó đang lưu một chuỗi gì đó,...Nhưng khi có ai đó bên ngoài thử cố gắng hiểu đoạn code của bạn, họ sẽ bất ngờ nhận ra cái tên đó chẳng mang một ý nghĩa cụ thể nào cả :)) họ sẽ phải từ bỏ việc đào bới đoạn code và như vậy biến cùng với logic của bạn được __an toàn__ là của bạn.

Không có cách nào để thực sự hiểu được đoạn code của bạn - một ninja thượng đẳng - ngoại trừ việc dành nhiều thời gian cho nó và phải thực sự tĩnh tâm :)) Bạn sẽ bất ngờ về khả năng đọc code của môn sinh mới sau vài tháng luyện tập.

+ Vậy phải làm gì khi hầu hết những cái tên phía trên đều rất dễ bị một ninja khác trước bạn dùng mất? Đơn giản, chỉ cần __THÊM SỐ VÀO__ : `data1`, `data2`, `value3`, `str4`,...etc.

## Kiên định

Sự tập trung cũng là một trong những yếu tố phân định đẳng cấp của một ninja! Chỉ những ninja đã thực sự tập trung và kiên nhẫn mới đủ tư cách đi cùng những ninja thượng đẳng khác. Vậy làm cách nào để thử thách họ - những môn sinh non trẻ?

Một cách đơn giản, hãy __sử dụng những cặp tên dễ nhầm lẫn đặt tên biến__ như là `data` & `date`. Sau đó mix chúng lại với nhau! Sẽ không ai có thể nhanh chóng đọc được source code của bạn, và rồi khi có lỗi typo (lỗi đánh máy) Uhm...chúng ta sẽ còn kẹt ở đây khá lâu, một tách trà trước khi tiếp tục không phải một ý tưởng tồi...

## Tiền tố

> Rất khó để có thể bắt được con mèo đen trong một căn phòng tối. Nhất là khi trong đó chẳng có con mèo nào.
>
> -- <cite>Confucius</cite>

Sử dụng những từ gần nghĩa là một cách khẳng định khả năng suy nghĩ linh hoạt và sáng tạo của một ninja thượng đẳng. Nó cũng làm cho code của team trở nên thú vị hơn rất nhiều :))

Xem xét ví dụ về tiền tố trong đặt tên. Khi muốn viết hàm hiển thị thông tin lên màn hình - hãy đặt tên nó với tiền tố `display`...chẳng hạn `displayMessage`!!! Khi có một chức năng khác cần hiển thị một cái gì đó khác lên màn hình, cố gắng tìm một từ gần nghĩa tương tự chẳng hạn `showName`! 

Nhấn mạnh rằng có sự khác biệt tinh tế giữa các chức năng như vậy, trong khi không có sự khác biệt nào. Hoặc theo một hướng khác, hãy thử thảo luận và đưa ra một hiệp ước với các ninja đồng đội: Nếu như đối với chức năng hiển thị, A sẽ viết các function với tên bắt đầu bằng `display`, B sẽ bắt đầu bằng `render` còn bạn sẽ bắt đầu bằng...`paint` chẳng hạn. Càng nhiều ý tưởng, code của team sẽ càng đa dạng, môn sinh mới gia nhập càng có thêm ví dụ để thực hành. Vậy là bạn đã có sáng tạo của riêng mình và tiến thêm được một bước trên con đường ninja đạo.

...Và bây giờ là thời gian dành cho mẹo vặt!

Nếu đã __đặt tiền tố khác nhau cho những chức năng tương tự nhau__, còn gì cản bước bạn không thực hiện nốt phần ngược lại __đặt tên tiền tố giống nhau cho những chức năng không mấy liên quan đến nhau__?

Ví dụ, hàm `printPage(page)` sẽ sử dụng máy in, in trang hiện tại. Và hàm `printText(text)` sẽ hiển thị văn bản lên màn hình. Hãy để môn sinh xa lạ khi nghĩ về chức năng `printMessage(message)` - một cái tên cùng tiền tố - “Nó đặt thông điệp ở đâu? Để máy in hoặc trên màn hình? ”. Sẽ là một môn sinh đầy triển vọng nếu anh ta có thể làm cho nó thực sự tỏa sáng bằng một ý tưởng: `printMessage(message)` nên xuất nó trong cửa sổ mới!

## Tái sử dụng tên (biến, hàm,...)

> Once the whole is divided, the parts need names. </br>
> There are already enough names. One must know when to stop.
>
> -- <cite>Laozi (Tao Te Ching)</cite>

Một ninja giỏi biết cách tăng tối đa hiệu quả sử dụng bộ nhớ bằng cách __chỉ tạo biến mới khi thực sự cần thiết__!

Một mặt tích cực khác là bạn đỡ tốn thời gian naming cho biến mới. Do đó tốt hơn cả là sử dụng lại biến với những cái tên đã có, chỉ cần __thay giá trị mới cho chúng__.

Một ninja thượng đẳng có thể viết ra những function hàng chục dòng logic mà chỉ sử dụng các biến được __truyền vào dưới dạng tham số__. Một môn sinh mới sẽ cảm thấy khó khăn để xác định được chính xác giá trị tại thời điểm hiện tại của một biến nào đó, hay biến đó đến từ đâu. Một người có trực giác yếu sẽ phải phân tích đoạn mã theo từng dòng, theo dõi sự thay đổi qua mỗi nhánh mã và sau cùng tuyệt vọng chạy thử đoạn mã trên giấy...

Một biến thể cao cấp của kĩ năng này là thử tráo (tạo clone) của biến đó bên trong vòng loop hoặc function. Những môn sinh yếu không hiểu rõ về những thứ như tham chiếu và tham trị thực sự sẽ phải quỳ gối trước những đoạn code như vậy.

```java
function ninjaFunction(elem) {
  // 20 lines of code working with elem

  elem = clone(elem);

  // 20 more lines, now working with the clone of the elem!
}
```

Khi muốn làm việc với biến `elem` ở nửa sau của hàm, thậm chí, ngay cả một ninja khác cũng có thể sẽ phải bất ngờ...Chỉ khi debug đoạn code trên từng dòng, anh ta mới có cơ hội nhận ra mình đang làm việc với bản clone của biến đó.

## Thể hiện tình yêu đối với những gì bạn tạo ra

Hãy để những môn sinh trẻ tuổi thấy được sự tuyệt vời của những thứ bạn tạo ra! Những cái tên như `superElement`, `megaFrame` và `niceItem` chắc chắn sẽ soi sáng họ.

Thật vậy, một cái gì đó được naming: `super...`, `mega...`, `nice...` Nhưng mặt khác - điều đó không mang lại thông tin chi tiết nào. Môn sinh trẻ tuổi có thể tự ngộ ra một ý nghĩa ẩn nào đó sau khi đã thiền định trong một hoặc hai giờ.

## Chồng chéo các biến bên ngoài

> When in the light, can’t see anything in the darkness. </br>
> When in the darkness, can see everything in the light.
>
> -- <cite>Guan Yin Zi</cite>

Sử dụng cùng một tên biến cho biến ở trong và ngoài một scope nào đó. Ví dụ 

```java
let user = authenticateUser();

function render() {
  let user = anotherValue();
  ...
  ... //many lines...
  ...
  ... // <-- a programmer wants to work with user here and...
  ...
}
```

Môn sinh trẻ tuổi đang làm việc với đoạn code bên trong function render sẽ không thể nhận ra có một biến local khác cùng tên `user` mới thực sự là biến đang được sử dụng. Anh ta vẫn đang tưởng mình đang sử dụng biến user là kết quả của `authenticateUser()`...!!! Ok happy debugging :))

## Side-effects everywhere!!!

Có những chức năng giống như chúng __không thay đổi gì cả__. Những function với cái tên như `isReady()`, `checkPermission()`, `findTags()`,... Chúng được giả định để thực hiện các phép tính, tìm và trả về dữ liệu mà __không thay đổi bất kỳ thứ gì bên ngoài chúng__. Nói cách khác, không có __"side effect"__.

+ Một ninja đắc đạo biết cách __thêm vào chúng những chức năng hữu ích__ để hỗ trợ đồng đội.

Biểu hiện của sự ngạc nhiên ngạc nhiên trên khuôn mặt của đồng nghiệp của bạn khi anh ta thấy một chức năng có tên là `check...` hoặc `find...` thay đổi một cái gì đó - chắc chắn sẽ là lý do anh ấy rời xa bạn hơn :)).

+ Một cách khác để gây ngạc nhiên cho anh bạn đồng nghiệp là __trả lại kết quả không chuẩn__.

Với cách suy nghĩ còn non nớt chưa qua rèn rũa của một môn sinh, `checkPermission()` hẳn là một thứ gì đó mà sẽ trả về `true/false`, nhưng là một ninja có trách nhiệm, bạn nên trả về nhiều hơn để giúp anh ta, hãy trả về cho anh ấy một object.

Cho đến khi môn sinh trẻ tuổi kia viết những thứ đại loại như `if(checkPermission(...))`, anh ta sẽ tự hỏi tại sao nó không hoạt động. Nói với anh ấy: “Đọc tài liệu đi!!!”. Và __đưa cho anh ấy bài viết này__.

## Powerful functions!

> The great Tao flows everywhere, both to the left and to the right.
>
> -- <cite>Laozi (Tao Te Ching)</cite>

Đừng giới hạn chức năng function của bạn chỉ bởi vì cái tên của nó. Hãy để cho nó làm được nhiều hơn thế.

Ví dụ như function `validateEmail(email)` bên cạnh việc kiểm tra tính đúng đắn của email, nó nên xuất ra thông báo về lỗi đó và gửi yêu cầu để người dùng gửi lại email chẳng hạn. Không gì tốt hơn việc __chỉ gọi một function và bạn đã có mọi thứ bạn muốn__ :)).

Những ninja giỏi biết cách giấu hàng tá logic vào trong code của họ, để không ai có thể đánh cắp chúng từ bên ngoài.

![magic](https://media.giphy.com/media/12NUbkX6p4xOO4/giphy.gif)

__Kết hợp nhiều logic vào trong cùng một chỗ giúp bảo vệ code của bạn khỏi nguy cơ bị tái sử dụng.__

Tưởng tượng một thằng ngốc nào đó trong team muốn sử dụng code của một ninja như bạn, ví dụ như hàm `validateEmail(email)` bên trên. Sau vài giờ thiền định và nhận ra function bạn viết làm được còn nhiều hơn cả những gì một gã ngốc như anh ta mong đợi (kiểm tra tính đúng đắn của email), nghiễm nhiên, anh ta sẽ bỏ cuộc và không có ý định làm phiền đến khoảng thời gian thiền định của bạn.

# TL;DR

Tất cả những __code lý__ trong __code đạo__ của ninja đạo kể trên đều từ source code có thật...Nhiều khi nó được viết bởi những developer nhiều năm kinh nghiệm, có lẽ có thể còn nhiều hơn cả bạn ;).

- Tuân theo __một vài đạo lý__ trong số này, code của bạn sẽ tràn đầy sự bất ngờ.
- Tuân theo __phần lớn đạo lý__ trong số này, code của bạn sẽ thực sự là của bạn, không ai muốn sửa hay động đến nó.
- Tuân theo __tất cả những đạo lý__ này, code của bạn sẽ trở thành một bài học có giá trị cho các môn sinh trẻ tìm kiếm sự giác ngộ.