
.. _../pages/guide/project/howtoviet#hướng_dẫn_thân_thiện:

Hướng dẫn thân thiện
==================== 

XXX
---

XXX
^^^

.. _../pages/guide/project/howtoviet#cho_các_người_dịch_tập_tin_dạng_.po,_dành_cho_dự_án_thông_dịch_the_translation_project_tại_trường_học_đại_học_montréal:

cho các người dịch tập tin dạng .po, dành cho Dự án Thông dịch (The Translation Project) tại trường học đại học Montréal
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""

\\
Tôi đã viết tài liệu này để giúp đỡ bạn tránh làm nhiều lỗi mà tôi đã làm khi bắt đầu dịch. ;-)

Mỗi phần có dấu :!: là Mẹo Địch!
----

.. _../pages/guide/project/howtoviet#hộp_công_cụ_dịch:

Hộp công cụ dịch
----------------

Người thật sự tài tình thì chú ý đến công cụ. Rất may là hiện thời chúng ta có một số công cụ địa phương hóa tốt lắm. Để dịch một tập tin dạng .po thì bạn sẽ cần phải có phần mềm này:

.. _../pages/guide/project/howtoviet#phiên_bản_mới_nhất_của_trình_gettext:

Phiên bản mới nhất của trình gettext
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Có thể kiểm tra phiên bản dùng lệnh:

``gettext --v``

Hiện có:

``gettext (GNU gettext) 0.14.3``

tuy nhiện, vì trang này sẽ trở thành cũ hơn, bạn nên kiểm tra phiên bản mới nhất của gettext là gói tin nào. Bộ quản lý gói tin Fink không luôn luôn liệt kê phiên bản mới nhất của mọi gói tin thì vui lòng kiểm tra địa chỉ Mạng này:

http://ftp.gnu.org/gnu/gettext/

và tải về rồi cài đặt phiên bản mới nhất có tại đó.

:?: *tài liệu hướng dẫn gettext:*  `completing gettext installation: cài đặt xong phần mềm gettext <http://www.gnu.org/software/gettext/manual/html_mono/gettext.html#SEC8>`_
\\

.. _../pages/guide/project/howtoviet#một_trình_biên_soạn_văn_bản:

Một trình biên soạn văn bản
^^^^^^^^^^^^^^^^^^^^^^^^^^^

Bất cứ trình biên soạn văn bản nào cũng được. 
\\

.. _../pages/guide/project/howtoviet#tuy_nhiên:

Tuy nhiên
^^^^^^^^^
bạn có thể đơn giản hóa công việc dịch một cách đáng kể bằng cách sử dụng một trình được thiết kế để biên soạn tập tin dạng .po.
Hiện có:

  * `kbabel <http://i18n.kde.org/tools/kbabel>`_ (KDE)
  * `gtranslator <http://gtranslator.sourceforge.net/>`_ (GNOME)
  * `emacs <http://www.gnu.org/software/emacs/emacs.html>`_ (đa nền tảng, gồm giao diện người dùng độ họa sở hữu của Mac OSX)
  * `poedit <http://www.poedit.org/index.php>`_ (đa nền tảng)
  * `LocFactoryEditor <http://www.triplespin.com/en/products/locfactoryeditor.html>`_ (giao diện người dùng độ họa sở hữu của Mac OSX)

.. _../pages/guide/project/howtoviet#cộng_đồng_quốc_tế_hóa:

Cộng đồng quốc tế hóa
^^^^^^^^^^^^^^^^^^^^^ 
đã làm rất nhiều việc để giúp đỡ chúng ta thông dịch một cách dễ dàng hơn. Thế cũng công bố:

  * `Bộ công cụ dịch <http://sourceforge.net/project/showfiles.php?group_id=91920&package_id=97082>`_ (Translate Toolkit), mà chứa một số công cụ thật sự hữu ích
  * `Tài liệu hướng dẫn thông dịch <http://translate.sourceforge.net/doc/index.html>`_ bao gồm wiki (và trang) này
  * Công cụ thông dịch đưa vào Mạng `Pootle <http://pootle.locamotion.org/>`_: cho phép nhiều người khác nhau thông dịch cùng những tập tin đồng thời và/hay trên khắp thế giới
  * `po4a <http://po4a.alioth.debian.org/>`_, một dự án Debian chứa nhiều công cụ chuyển đổi giữa định dạng khác (v.d. (n)roff <-> .po)

Ba mục đầu công bố trong wiki này, hay trong nơi Mạng của `Dự án Translate <http://translate.sourceforge.net/>`_ tại Sourceforge.

:!: Dùng po4a và Bộ công cụ dịch thì bạn có thể chuyển đổi gần bất cứ định dạng nào sang hay từ .po, có lẽ ngay cả hình dang hữu cơ... :-)

:?: **cũng xem** những phần khác trong wiki này, để tìm tải nguyên khóa và thông tin hữu ích về nhiều khía cạnh của công việc thông dịch trong cộng đồng phần mềm nguồn mở (OSS). Những người dịch có nhiều kinh nghiệm đã mất lâu để đóng góp cùng wiki này, để tiết kiệm thời gian và tránh sự khó khăn cho các chúng ta. Mọi ý kiến về kinh nghiệm của bạn, vui lòng đóng góp cùng tải nguyên chung này vào bất cứ lúc nào nhé. :-)

Vào lúc này, chúng ta xem lại cộng việc thông dịch...

\\
----

.. _../pages/guide/project/howtoviet#dịch_tập_tin_dạng_.po:

Dịch tập tin dạng .po
---------------------

Một tập tin PO (Portable Object: đối tượng có thể mang) là một định dạng được tạo dành cho hành động cần thiết của chúng ta: lấy thông tin và di chuyển nó sang nơi khác. Bạn có thể dùng mọi trình biên soạn văn bản, lập gần mọi bộ ký tự (dù UTF-8 là an toàn nhất vì lý do khác), ngay cả cho con chó ăn nó, và nó sẽ vẫn còn kết thức chính xác là cùng điều trước ... một tập tin văn bản: chỉ chữ thôi.

:!: Sự khác duy nhất giữa tập tin văn bản thường và t
.. _../pages/guide/project/howtoviet#dịch_tập_tin_dạng_.po:

Dịch tập tin dạng .po
---------------------

Một tập tin PO (Portable Object: đối tượng có thể mang) là một định dạng được tạo dành cho hành động cần thiết của chúng ta: lấy thông tin và di chuyển nó sang nơi khác. Bạn có thể dùng mọi trình biên soạn văn bản, lập gần mọi bộ ký tự (dù UTF-8 là an toàn nhất vì lý do khác), ngay cả cho con chó ăn nó, và nó sẽ vẫn còn kết thức chính xác là cùng điều trước ... một tập tin văn bản: chỉ chữ thôi.

:!: Sự khác duy nhất giữa tập tin văn bản thường và tập tin .po là khối dòng đầu và cấu trúc của khối chuỗi. Trước bạn đóng góp một tập tin dịch xong, cần phải kiểm tra xem không có lỗi nào còn lại, gồm lỗi về cấu trúc này. Hơn nữa, khi bạn đóng góp tập tin .po cùng Dự án Thông dịch thì trình rô-bốt sẽ kiểm tra lại tập tin, và nó thử ra các dòng đầu một cách chính xác, thì hữu ích để biết cách lập cho đúng. Như thế thì sẽ tránh cần phải đóng góp lại tập tin ấy, và tránh rô-bốt từ chối nó với sự sửa -- mà có thể làm bực tức một chút.  :-\

.. _../pages/guide/project/howtoviet#khối_dòng_đầu:

Khối dòng đầu
^^^^^^^^^^^^^

Đây là một khối dòng đầu chưa lập:

::

    # SOME DESCRIPTIVE TITLE.
    # Copyright (C) YEAR THE PACKAGE'S COPYRIGHT HOLDER
    # This file is distributed under the same license as the PACKAGE package.
    # FIRST AUTHOR <EMAIL@ADDRESS>, YEAR.
    #
    #, fuzzy
    msgid ""
    msgstr ""
    "Project-Id-Version: PACKAGE VERSION\n"
    "POT-Creation-Date: 2003-07-24 09:35+0200\n"
    "PO-Revision-Date: YEAR-MO-DA HO:MI+ZONE\n"
    "Last-Translator: FULL NAME <EMAIL@ADDRESS>\n"
    "Language-Team: LANGUAGE <LL@li.org>\n"
    "MIME-Version: 1.0\n"
    "Content-Type: text/plain; charset=CHARSET\n"
    "Content-Transfer-Encoding: 8bit\n"

Bình thường, bạn sẽ gặp một khối hoàn thành chưa lập, như khối này, trong một tập tin chưa dịch chuỗi nào cả, một tập tin PO Template (mẫu) có phần mở rộng .pot

:!: Rất dễ dàng để chuyển đổi tập tin .pot sang .po! Chỉ đơn giản điền đầy đủ khối dòng đầu, và thay đổi phần mở rộng thành .po. Xong rồi.

Khi bạn cập nhật một tập tin đã dịch một cách bộ phận, hay tập tin đã dịch cũ, thì có lẽ sẽ gặp một số dòng đầu vẫn còn chưa lập, hay quá hạn. 

:!: Vậy luôn luôn cần phải kiểm tra khối dòng đầu: hãy làm việc này trước hết, hãy làm nó sau hết (trước đệ trình tập tin dịch xong) thì bạn sẽ tránh sự khó.

Có hai dòng đầu có lẽ không xuất hiện trong khối ấy, nhưng mà tốt hơn nếu *có*. Bạn có thể tự thêm hai dòng ấy:

::

    "Report-Msgid-Bugs-To: \n"

và

::

    "Plural-Forms: nplurals=INTEGER; plural=EXPRESSION\n"

thế ở dưới đây chúng ta có một khối dòng đầu hoàn thành (hãy ghi chú vị trí của hai dòng đầu thêm):

::

    # SOME DESCRIPTIVE TITLE.
    # Copyright (C) YEAR THE PACKAGE'S COPYRIGHT HOLDER
    # This file is distributed under the same license as the PACKAGE package.
    # FIRST AUTHOR <EMAIL@ADDRESS>, YEAR.
    #
    #, fuzzy
    msgid ""
    msgstr ""
    "Project-Id-Version: PACKAGE VERSION\n"
    "Report-Msgid-Bugs-To: \n"
    "POT-Creation-Date: 2003-07-24 09:35+0200\n"
    "PO-Revision-Date: YEAR-MO-DA HO:MI+ZONE\n"
    "Last-Translator: FULL NAME <EMAIL@ADDRESS>\n"
    "Language-Team: LANGUAGE <LL@li.org>\n"
    "MIME-Version: 1.0\n"
    "Content-Type: text/plain; charset=CHARSET\n"
    "Content-Transfer-Encoding: 8bit\n"
    "Plural-Forms: nplurals=INTEGER; plural=EXPRESSION\n"

Mỗi dòng đầu làm một việc có ích, vì vậy chúng ta sẽ xem từng dòng:

\\

.. _../pages/guide/project/howtoviet#dòng_đầu_tên_gói:

Dòng đầu tên gói
""""""""""""""""

::

    # SOME DESCRIPTIVE TITLE.

  * Một tên diễn tả nào đó

cung cấp thông tin nhanh về tên của gói phần mềm này. Ở đây thì bạn hãy gõ *tên* của chương trình (không phải số phiên bản). Trong lời thí dụ bên dưới, tôi sẽ sử dụng chương trình `Tuxpaint <http://www.newbreedsoftware.com/tuxpaint/>`_ (một chương trình vẽ/sơn rất tốt cho đứa bé) và ngôn ngữ tôi, Việt ngữ.

::

    # Vietnamese translation of TuxPaint.

  * Bản dịch Việt ngữ của chương trình TuxPaint.

:!: Ghi chú rằng mọi dòng đầu này có *một dấu thăng # và một dấu cách* trước thông tin ấy. Trình kiểm tra, gồm rô-bốt, chỉ chấp nhận dấu đúng, vì hai dấu này là tin hiệu gettext của dòng đầu thông tin. Trình gettext thật phân tách thông tin này, và toàn tập tin. Như thế thì, khi chúng ta bảo đảm định dạng là đúng, sẽ không phải mất thời gian sửa lỗi khi trình gettext không phân tách được tập tin ấy.

\\

.. _../pages/guide/project/howtoviet#dòng_đầu_bản_quyền:

Dòng đầu bản quyền
""""""""""""""""""

::

    # Copyright (C) YEAR THE PACKAGE'S COPYRIGHT HOLDER

  * Bản quyền [ký hiệu bản quyền] năm nhà cầm quyền gói này

Trong trường hợp gói nào tại Dự án Thông dịch thì phần mềm thường là phần mềm nguồn mở, phần mềm tự do. Cho phần mềm loại này, thông tin thường là (dùng năm này):

::

    # Copyright © 2005 Free Software Foundation, Inc.

  * Bản quyền [ký hiệu bản quyền] năm 2005 Tổ chức Phần mềm Tự do

Nếu bạn có truy cập được ký hiệu bản quyền © một cách hơi dễ dàng trong bố trị bàn phím hay tính năng gõ ký tự đặc biệt, khi gõ nó thì hình như nghề nghiệp hơn. ;-)

Đôi khi gặp một tập tin có dòng đầu bản quyền sở hữu: một người nào đó đã tạo, và có quyền yêu sách tập tin ấy (lấy thí dụ):

::

    # Copyright © 2001-2005 Nguyễn Thị Hoa.

  * Bản quyền [ký hiệu] năm 2001-2005 của Nguyễn Thị Hoa

Trong trường hợp ấy thì bạn phải theo dòng đầu đã có. Đừng sửa đổi nó.

:!: Nếu tập tin của bạn có phải có dòng đầu bản quyền sở hữu, và trình rô-bốt từ chối nó vì không có dòng đầu bản quyền Tổ chức Phần mềm Tự do, như thế thì bản chỉ đơn giản hãy viết thư điện tử cho người điều hợp của Dự án Thông dịch tại:

translation AT iro d0t umontreal d0t ca((Phải viết địa chỉ thư điện từ như thế vì người gởi thư rác sẽ ăn cấp địa chỉ... :-( -- AT là dấu a-công; d0t là dấu chấm; không có dấu cách nào cả))

vì vấn đề ấy thuộc về dự án, không phải thuộc về bạn, dù đôi khi chúng ta có cảm thấy phật lòng khi tập tin mình bị từ chối vì có lỗi không phải của mình. Điều hợp viên cần phải lập một tùy chọn cho mỗi tập tin loại ấy, để tránh rô-bố từ chối nó khi bạn, hay người dịch khác, đệ trình nó lần kế tiếp. Hơn nữa, mỗi lúc chúng ta có thể đóng góp thời gian hay kinh nghiệm, chúng ta giúp nhau. ^_^
\\

.. _../pages/guide/project/howtoviet#dòng_đầu_bản_quyền_liên_quan:

Dòng đầu bản quyền liên quan
""""""""""""""""""""""""""""

::

    # This file is distributed under the same license as the PACKAGE package.

  * Tập tin này được phát hành với điều kiện của cùng quyền với gói TÊN này.

Dòng đầu này (không phải luôn luôn có trong tập tin, dù nên có) phát hành bản dịch với điều kiện của bản quyền tập tin gốc. Làm như thế tránh người khác yêu cầu bản quyền của bản dịch. Nếu bạn đang dịch trong Dự án Thông dịch thì đã điền đầy đủ một đơn từ chối trách nhiệm mà gán quyền bạn cho Tổ chức Phần mềm Tự do: làm như thế tránh nhiều sự khó, thì đơn giản hóa vấn đề quyền cho mọi người.

Ở đây thì bạn chỉ cần chèn lại tên của gói:

::

    # This file is distributed under the same license as the TuxPaint package.

  * Tập tin này được phát hành với điều kiện của cùng quyền với gói TuxPaint.

\\

.. _../pages/guide/project/howtoviet#danh_sách_các_người_dịch:

Danh sách các người dịch
""""""""""""""""""""""""

::

    # FIRST AUTHOR <EMAIL@ADDRESS>, YEAR.

  * Tác giả thứ nhất <địa chỉ thư điện từ>, năm.

Dòng đầu này có chưa lập chỉ nếu bạn là người thứ nhất để dịch tập tin ấy. Nếu nó đã được dịch, ngay cả bộ phận, trước đó, thì sẽ có ở đây tên của mỗi người dịch trước, trên từng dòng. Vậy nếu chỉ có một người dịch (tôi sẽ sử dụng tên mình):

::

    # Clytie Siddall <clytie@máy_chủ_nào.net.au>, 2005.

  * Tên họ tôi, địa chỉ thư, năm này.

Tuy nhiên, nếu đã có người dịch trước, sẽ có nhiều dòng đầu người dịch. Lấy thí dụ:

::

    # pclouds <pmây@máy_chủ_khác.com>, 2002.
    # Tran Minh Thanh <tmt@yahhooo.com>, 2004.
    # Clytie Siddall <clytie@máy_chủ_nào.net.au>, 2005.

Vậy về lý thuyết, tập tin có thể chứa rất nhiều dòng đầu loại này, riêng từng, nhưng mà trong thực hành, thường gặp một đến năm dòng đầu.

:!: Đừng sửa đổi dòng đầu người dịch trước nào, chỉ hãy chèn dòng đầu mình bên dưới dòng đầu người dịch trước mới nhất. Những dòng đầu người dịch này bảo đảm mọi người đã cố dịch tập tin này thì cả hai được thừa nhận, và nhận trách nhiệm làm cộng việc của mình.

\\

.. _../pages/guide/project/howtoviet#dòng_đầu_rỗng:

Dòng đầu rỗng
"""""""""""""

::

    #

Có lẽ bạn xem một dòng đầu rỗng giữa hai phần khối đầu tập tin. Nó cho bạn đọc khối này một cách dễ hơn. Bạn không cần làm gì ở đây. ;-)

\\

.. _../pages/guide/project/howtoviet#dòng_đầu_mờ:

Dòng đầu mờ
"""""""""""

::

    #, fuzzy

  * mờ

Hãy ghi chú rằng tại đầu dòng này, có một dấu phẩy sau dấu thăng #. Hai dấu này đều ngú ý là trình gettext đọc dòng đầu này như là *thông tin* về các khối chuỗi trong tập tin ấy. Nếu tập tin có dòng đầu này thì vẫn còn chứa chuỗi chưa dịch hay/và chuỗi có lỗi trong nó. Trình biên soạn .po có lẽ sẽ tự động loại bỏ nó một khi bạn đã dịch xong tập tin ấy, hoặc nếu bạn đang sử dụng một trình biên soạn văn bản thường mà không phải được thiết kế để quản lý những dòng đầu .po, thì bạn có thể tự loại bỏ nó. Chỉ xóa bỏ toàn dòng. Xong rồi.

Chuỗi *mờ* là chuỗi chưa dịch hay không đúng. Trình gettext quyết định đánh dấu ấy ở đâu, đựa vào (lấy thí dụ) nếu mọi dấu nháy kép, mọi biến và mọi ký tự ngắt dòng trong mỗi chuỗi của cặp thì khớp với nhau hay không. Nó sé cũng quyết định nó bằng cách kiểm tra nếu chuỗi từ điển nào do trình *msgmerge* đệ nghị thì khớp chuỗi gốc hay không. Mỗi chuỗi mờ có dấu mờ: cần phải kiểm tra nó một cách cẩn thận. Có thông tin thêm về tiến trình ấy xuống trang này. 8-)

*Tài liệu hướng dẫn gettext:* `fuzzy strings: chuỗi mờ <http://www.gnu.org/software/gettext/manual/html_mono/gettext.html#SEC46>`_ 

\\

.. _../pages/guide/project/howtoviet#cặp_chuỗi:

Cặp chuỗi
"""""""""

::

    msgid ""
    msgstr ""

Cặp chuỗi rỗng này ngụ ý cho trình gettext, tôi giả sử, cấu trúc của các chuỗi trong tập tin ấy. Chuỗi **msgid** (MeSsaGe ID: mã nhận diện thông điệp) là đoạn trong ngôn ngữ gốc, còn chuỗi **msgstr** (MeSsaGeS TRanslated) là bản dịch. 

:!: Tập tin xuất thì phải chứa mỗi cặp chuỗi, "được bao bằng dấu nháy kép". Đừng sửa đổi dòng đầu này.

\\

.. _../pages/guide/project/howtoviet#dòng_đầu_phiên_bản_gói:

Dòng đầu phiên bản gói
""""""""""""""""""""""

::

    "Project-Id-Version: PACKAGE VERSION\n"

  * Phiên bản mã nhận diện dự án: phiên bản gói

Ở đây, phiên bản gói có phải là quan trọng: cần phải theo dõi dòng đầu này khi cập nhật tập tin nào. 

:!: Trình rô-bốt của Dự án Thông dịch cần thiết tên của chương trình và phiên bản có định giới bằng một dấu cách, không phải bằng một dấu gạch dưới hay dấu gạch nối. Trong cách ấy, dòng đầu này khác với tên tập tin gốc.

Tên tập tin gốc: tuxpaint-2.1pre

::

    "Project-Id-Version: Tuxpaint 2.1pre\n"

:!: Hãy nhớ để sửa đổi dòng đầu này mọi khi cập nhật tập tin nào

Bạn nên sử dụng tất cả thông tin trong phần phiên bản của tên tập tin: 0.03a2, 2.01b, 0-03.2pre2, có phải là thông tin có ích về giai đoạn phát triển của gói này.

  * **a** có thể có nghĩa an-pha, một bản phát hành rất sớm, thường hơi bất ổn, chỉ nhằm mục đích thử nghiệm thôi; 
  * **b** có thể có nghĩa bê-ta, một bản thử nghiệm sau, thường hơi ổn định nhưng mà chưa bảo đảm gì hay hỗ trợ gì. Bạn có thể học biết nhiều và giúp đỡ phát triển phần mềm bằng cách thử nghiệm phần mềm bê-ta, dành cho cách hỗ trợ ngôn ngữ khác. :-)  
  * **pre** có thể có nghĩa là *trước* phát hành hoàn thành, phiên bản cuối cùng trước phiên bản phát hành hoàn thành: đã thử ra xong rồi. Rất có thể có nghĩa là phiên bản hoàn thành sẽ xuất hiện trước lâu thì bạn sẽ cần phải cập nhật lại tập tin ấy. 

Nếu bạn đang sử dụng chương trình nào đã dịch mình, hãy nhớ để kiểm tra phiên bản và thông tin tại nơi Mạng của nó, để quyết định nếu trình ấy ổn định chưa. Nếu bạn chọn giúp đỡ thử nghiệm một chương trình nào đó, hay lắm! với điều kiện là bạn không ngờ nó có ổn định hoàn thành hay cung cấp sự hỗ trợ kỹ thuật. Còn những lập trình viên và người khác đóng góp cùng với bạn bằng cách thử nghiệm, có phải sẽ vui lòng thỏa luận chương trình ấy và hỗ trợ nhau trong hộp thư chung của trình ấy. ;-)

\\

.. _../pages/guide/project/howtoviet#dòng_đầu_thông_báo_lỗi_chuỗi:

Dòng đầu thông báo lỗi chuỗi
""""""""""""""""""""""""""""

::

    "Report-Msgid-Bugs-To: \n"

  * Thông báo lỗi trong chuỗi msgid cho

Bình thường, lập trình viên bỏ sót hay không điền vào dòng đầu này, mà làm phiền chúng ta, vì nó là địa chỉ liên lạc để sử dụng khi một chuỗi ngôn ngữ gốc là không đúng (thiếu dấu, thiếu từ, cú pháp hay gõ/chính tả sai), hoặc khi chúng ta chưa hiểu một chuỗi nào đó đủ khá để dịch nó.

Có mất thời gian nhiều nếu chúng ta cần phải trở về trang nhóm chúng ta tại Dự án Thông dịch, nhắp vào tên tập tin ấy để đi tới miền văn bản của nó (trang dành cho nó tại dự án ấy), rồi tìm kiếm trang chủ của chương trình, hoặc thông tin liên lạc khác nào. Thường cần phải Google trong một thời gian để tìm nó.

Khi bạn tìm được địa chỉ liên lạc ấy, vui lòng điền nó vào tập tin của bạn. Vậy người kế tiếp, có thể bạn :-) , sẽ không cần phải mất thời gian để tìm kiếm nó. Ý kiến tốt là đệ nghị lập trình viên điền vào dòng đầu này.

:?: Đã tìm biết một số điều hữu ích về địa chỉ thông báo:

  * mọi gói GNU có địa chỉ thông báo lỗi này:

bug-TÊN_GÓI@gnu(chấm)org

  * mọi lỗi GNOME được thông báo thông qua trang Mạng `Bugzilla <http://bugzilla.gnome.org/>`_

  * mọi lỗi Debian được thông báo bằng cách gởi thư điện tử cho

owner(a-còng)bugs(chấm)debian(chấm)org 

có tên tập tin là chủ đề, và thận thư bắt đầu với:

::

    Package: TÊN_TẬP_TIN
    Version: SỐ_PHIÊN_BẢN
    Severity: wishlist
    Tags: l10n, patch

\\

.. _../pages/guide/project/howtoviet#ngày_tạo_tập_tin_này:

Ngày tạo tập tin này
""""""""""""""""""""

::

    "POT-Creation-Date: 2004-07-24 09:35+0200\n"

  * Ngày đã tạo tập tin mẫu gốc [.pot]: năm-tháng-ngày giờ:phút+múi_giờ_thế_giới

Tập tin .pot là tập tin gốc, chưa dịch, thì ngày ấy là lúc trình gettext tạo phiên bản tập tin này. Tập tin đã cập nhật sẽ có ngày tạo .po.

Thông tin này không quan trọng cho bạn (đừng sửa đổi nó), trừ:

:!: bạn sẽ cần phải kiểm tra xem ngày sửa đổi (ngày khi bạn hiệu chỉnh tập tin này) là **sau** ngày tạo: nếu không thì trình gettext hay rô-bốt sẽ nói «Không phải!» và đúng vậy. Chúng ta người dịch chưa tìm biết cách đảo ngược thời gian. LOL

\\

.. _../pages/guide/project/howtoviet#dòng_đầu_ngày_sửa_đổi_cuối_cùng:

Dòng đầu ngày sửa đổi cuối cùng
"""""""""""""""""""""""""""""""

::

    "PO-Revision-Date: YEAR-MO-DA HO:MI+ZONE\n"

  *Ngày sửa đổi tập tin .po: năm-tháng-ngày giờ:phút+múi giờ thế giới

Dòng đầu này chưa điền trong tập tin .pot gốc, vì chưa sửa đổi (dịch) nó. Trong một tập tin đã cập nhật thì sẽ có một ngày sửa đổi. Chúng ta chỉ cần phải nhớ:

:!: để cập nhật ngày nào trước khi đệ trình tập tin dịch xong 

Một trình biên soạn tập tin .po có lẽ sẽ tự động cập nhật ngày nào. Bạn có thể tự làm như thế trong bất cứ giai soạn nào. Trong trình BBEdit (Mac OSX) có thể tạo một mục bản chú giải dùng biến strftime (chỉ hãy lưu nó và sử dụng nó, không cần phải hiểu cách hoặt động):

::

    "PO-Revision-Date: #LOCALTIME %F %R%z#\n"

Mục này, nếu trình hay hệ thống của bạn có thể thay thế giá trị strftime, sẽ hiển thị dòng đầu này đúng cho bạn, tại bất cứ nơi nào trên khắp thế giới. Trong trường hợp tôi, khi viết câu này thì xem:

::

    "PO-Revision-Date: 2005-05-25 16:08+0930\n"

:!: Hãy ghi chú thứ tự ngày ấy: năm-tháng-ngày, năm có bốn số tự, tháng có hai số và ngày cũng có hai số. Thì cần phải gồm số không đi trước khi số ấy nhỏ hơn số mười, như trong tháng hiện có: 05 (tháng năm).

Ghi chú số hiệu giờ thế giới. Nó nói là múi giờ tôi (thành phố Adelaide tại Úc, thời gian Trung Úc, không phải thời gian Mùa Hè) là 9.5 giờ, chín giờ nửa, sau giờ thế giợi (GMT hay UTC: 00:00).

:!: Nếu bạn không có trình như BBEdit có thể thay thế giá trị strftime cho bạn thì cần phải nhớ để điền múi giờ mình ở đây. Cần phải nhớ để gõ số không đi trước nếu, như trong trường hợp tôi, chỗ bạn nhỏ hơn mười giờ sau hay trước UTC.

\\

.. _../pages/guide/project/howtoviet#dòng_đầu_người_dịch_mới_nhất_cuối_cùng:

Dòng đầu người dịch mới nhất (cuối cùng)
""""""""""""""""""""""""""""""""""""""""

::

    "Last-Translator: FULL NAME <EMAIL@ADDRESS>\n"

  * Người dịch cuối cùng: TÊN HỌ <ĐỊA CHỈ THƯ ĐIỆN TỪ

Khi bạn là người dịch *duy nhất* thì tên bạn sẽ xuất hiện cả hai trong dòng đầu Người Dịch Thứ Nhất, và đây trong dòng đầu Người Dịch Cuối Cùng, mà có lẽ sẽ làm cho bạn cảm thấy như là Người Dịch Có Thể Duy Nhất. LOL

Bạn chỉ hãy điền tên và địa chỉ thư vào đây, lần nữa, nhưng mà đừng gồm năm, như trong dòng đâù Người Dịch Thứ Nhất, vì Ngày sửa đổi .po có cung cấp nó.

Nếu có tên của người dịch trước điền vào đây, bạn cần phải sửa đổi nó để hiển thị tên bạn. Hãy chắc chắn có tên người dịch trước ấy trong phần thứ nhất của khối đầu (người dịch thứ nhất, thứ hai, thứ ba v.v.).

Vậy trong trường hợp tôi, dòng đầu này sẽ hiển thị"

::

    "Last-Translator: Clytie Siddall <clytie@máy_chủ_nào.net.au>\n"

  * Người dịch cuối cùng: tên họ <địa chỉ thư>

\\

.. _../pages/guide/project/howtoviet#dòng_đầu_nhóm_ngôn_ngữ:

Dòng đầu nhóm ngôn ngữ
""""""""""""""""""""""

::

    "Language-Team: LANGUAGE <LL@li.org>\n"

  * Nhóm ngôn ngữ: NGÔN NGỮ <ngôn_ngữ@hộp_thư_chung.org>

Ở đây có nơi công nhận nhóm ngôn ngữ bạn cho các sứ cố gắng của họ. Nó cũng cung cấp một địa chỉ liên lạc thêm cho người nào viết cho bạn về bản dịch. Nó thật có ích khi địa chỉ thư điện tử trở thành cũ, khi người nào dụ lịch hay thay đổi chi tiết.

Nhóm ngôn ngữ của bạn sẽ là tên của ngôn ngữ, và đôi khi của dự án. Địa chỉ sẽ thường là hộp thư chung nhóm. Vậy trong trường hợp tôi, dòng đầu này là:

::

    "Language-Team: Vietnamese <gnomevi-list@lists.máy_chủ_đó.net>\n"

  * Nhóm ngôn ngữ: Việt Nam <địa chỉ hộp thư chung

hay

::

    "Language-Team: Gnome-Vi <gnomevi-list@lists.máy_chủ_đó.net>\n"

  * Nhóm ngôn ngữ: nhóm Việt Nam tại dự án GNOME <địa chỉ hộp thư chung

\\

.. _../pages/guide/project/howtoviet#dòng_đầu_phiên_bản_mime:

Dòng đầu phiên bản MIME
"""""""""""""""""""""""

::

    "MIME-Version: 1.0\n"

  * Phiên bản MIME: 1.0

:!: Để tìm lời nghĩa của nhiều từ cấu tạo và kỹ thuật Mạng, bạn thăm gia trang tôi nhé: `Những từ cấu tạo bằng chữ đầu của những từ khác thường nhất của Mạng <http://www.riverland.net.au/~clytie/viet/netacrvn.html>`_ . Tôi sẽ cố cập nhật nó một cách đều đặn.

Dòng đầu phiên bản MIME thường đã điền vào rồi. Bạn không cần làm gì. Hay quá, phải không? :-D

\\

.. _../pages/guide/project/howtoviet#dòng_đầu_kiểu_nội_dung:

Dòng đầu kiểu nội dung
""""""""""""""""""""""

::

    "Content-Type: text/plain; charset=CHARSET\n"

  * Kiểu nội dung: chữ/thô; bộ ký tự=BỘ_KÝ_TỰ

:!: Đây thật sự là quan trọng. Dòng đầu này lập bộ ký tự cho ngôn ngữ bạn. UTF-8 (Unicode: mã hoàn thành) là tùy chọn tốt nhất, nhưng mà nếu ngôn ngữ bạn cần thiết bộ ký tự khác, hãy điền nó vào đây. Cho ngôn ngữ tôi:

::

    "Content-Type: text/plain; charset=UTF-8\n"

  * Kiểu nội dung: chữ/thô; bộ ký tự=Unicode

Unicode là tuyệt vời! Dễ hơn rất nhiều để có thể quên về các mã chữ khó quá cũ ấy ... Lúc này chỉ cần mọi hệ điều hành hỗ trợ Unicode một cách tốt hơn. 8-O

\\

.. _../pages/guide/project/howtoviet#dòng_đầu_cách_mã_hóa_nội_dung_để_truyền:

Dòng đầu cách mã hóa nội dung để truyền
"""""""""""""""""""""""""""""""""""""""

::

    "Content-Transfer-Encoding: 8bit\n"

  * Dòng đầu cách mã hóa nội dung để truyền: 8bit

Dòng đầu này cũng nên đã điền vào rồi. Nếu chưa, bạn hãy gõ **8bit**, cách mã hóa có thể quản lý UTF-8 và bộ ký tự phức tạp khác trong khi truyền. Bạn không muốn bản dịch đã làm việc nhiều của tôi sẽ bị hỏng trong khi đệ trình nó, hoặc khi nó được gởi cho lập trình viên.

\\

.. _../pages/guide/project/howtoviet#dòng_đầu_hình_dạng_số_nhiều:

Dòng đầu hình dạng số nhiều
"""""""""""""""""""""""""""

::

    "Plural-Forms: nplurals=INTEGER; plural=EXPRESSION\n"

  * Các hình dạng số nhiều: nplurals=SỐ_NGUYÊN; plural=BIỂU_THỨC -- nplurals và plural là tên biến

Thường dòng đầu này không có trong khối đầu tập tin, nhưng mà *nên* gồm nó. Khi bạn gặp chuỗi số nhiều (plural: diễn tả nhiều người hay điều) thì dòng đầu số nhiều này bảo đảm có số trường đúng cần gõ chuỗi đã dịch. Số này biến thay từ một ngôn ngữ đến ngôn ngữ khác. Cho ngôn ngữ tôi:

::

    "Plural-Forms: nplurals=1; plural=0\n"

  * Hình dạng số nhiều: cần chỉ một trường cho chuỗi đã dịch, không cần trường thêm

vì Việt ngữ không có hình dạng số nhiều về ý nghĩa đó. Một quyển, hai quyển. Nhưng mà bạn nên xem tập hợp đại từ... 8-)

Một số ngôn ngữ có vài hình dạng số nhiều. Một chuỗi gốc (msgid) số nhiều hình như đây:

::

    msgid "Found and replaced %d occurrence."
    msgid_plural "Found and replaced %d occurrences."

  * chuỗi gốc: đã tìm và thay thế một lần
  * chuỗi số nhiều gốc: đã tìm và thay thế nhiều lần

vì Anh ngữ, ngôn ngữ gốc trong tập tin này, *có phải* có hình dạng số nhiều về ý nghĩa này. Nếu ngôn ngữ bạn hành vi cùng với Anh ngữ thì bạn sẽ gặp hai trường msgstr để gõ, như dưới:

::

    msgid "Found and replaced %d occurrence."
    msgid_plural "Found and replaced %d occurrences."
    msgstr[0] ""
    msgstr[1] ""

  * [0] là chuỗi một
  * [1] là chuỗi số nhiều

nhưng mà trong trường hợp tôi, nó nên là:

::

    msgid "Found and replaced %d occurrence."
    msgid_plural "Found and replaced %d occurrences."
    msgstr[0] "Đã tìm được và thay thế %d lần"

Nếu dòng đầu số nhiều trong tập tin bạn được lập cho đúng thì bạn sẽ gặp trường gõ bản dịch (msgstr) số đúng và kiểu đúng. Vậy nó hữu ích lắm. 

:!: Bạn hãy hỏi người chủ nhóm về dòng đầu số nhiều đúng cho ngôn ngữ bạn, rồi điền nó vào khối đầu của mọi tập tin .po: nó sẽ tiết kiệm thời gian và tránh sự khó cho bạn.

Cũng có thể thỏa thuận thiết kê số nhiều, và bất cứ điều về dịch nào, trong :doc:`hộp thư chung Dự án Thông dịch <https///lists.sourceforge.net/lists/listinfo/translation-i18n>`, một nơi rất tốt để hỏi câu và chia kinh nghiệm.

\\
Các dòng đầu ấy là tất cả cần điền. Hết rồi. Mọi dòng đầu này có tiết kiệm thời gian khi địa phương hóa một ứng dụng nào đó. Bạn có thể lập chúng trong trình biên soạn .po, hoặc chỉ đơn giản lưu một bản sao của chúng để dán trên khối dòng đầu cũ hay gốc.

:!: Khi bạn cố điền các dòng đầu này cho đúng, và tìm biết cách mình để quản lý chúng, bạn trở thành một người dịch tốt hơn, vì người thông mình làm việc thì sử dụng công cụ một cách tốt nhất. Định dạng .po là một công cụ của chúng ta.

:?: *tài liệu hướng dẫn gettext:* 

`the po format: định dạng .po <http://www.gnu.org/software/gettext/manual/html_mono/gettext.html#SEC9>`_

`filling in the header entry: điền vào mục nhập đầu <http://www.gnu.org/software/gettext/manual/html_mono/gettext.html#SEC35>`_
----ập tin .po là khối dòng đầu và cấu trúc của khối chuỗi. Trước bạn đóng góp một tập tin dịch xong, cần phải kiểm tra xem không có lỗi nào còn lại, gồm lỗi về cấu trúc này. Hơn nữa, khi bạn đóng góp tập tin .po cùng Dự án Thông dịch thì trình rô-bốt sẽ kiểm tra lại tập tin, và nó thử ra các dòng đầu một cách chính xác, thì hữu ích để biết cách lập cho đúng. Như thế thì sẽ tránh cần phải đóng góp lại tập tin ấy, và tránh rô-bốt từ chối nó với sự sửa -- mà có thể làm bực tức một chút.  :-\

.. _../pages/guide/project/howtoviet#khối_dòng_đầu:

Khối dòng đầu
^^^^^^^^^^^^^

Đây là một khối dòng đầu chưa lập:

::

    # SOME DESCRIPTIVE TITLE.
    # Copyright (C) YEAR THE PACKAGE'S COPYRIGHT HOLDER
    # This file is distributed under the same license as the PACKAGE package.
    # FIRST AUTHOR <EMAIL@ADDRESS>, YEAR.
    #
    #, fuzzy
    msgid ""
    msgstr ""
    "Project-Id-Version: PACKAGE VERSION\n"
    "POT-Creation-Date: 2003-07-24 09:35+0200\n"
    "PO-Revision-Date: YEAR-MO-DA HO:MI+ZONE\n"
    "Last-Translator: FULL NAME <EMAIL@ADDRESS>\n"
    "Language-Team: LANGUAGE <LL@li.org>\n"
    "MIME-Version: 1.0\n"
    "Content-Type: text/plain; charset=CHARSET\n"
    "Content-Transfer-Encoding: 8bit\n"

Bình thường, bạn sẽ gặp một khối hoàn thành chưa lập, như khối này, trong một tập tin chưa dịch chuỗi nào cả, một tập tin PO Template (mẫu) có phần mở rộng .pot

:!: Rất dễ dàng để chuyển đổi tập tin .pot sang .po! Chỉ đơn giản điền đầy đủ khối dòng đầu, và thay đổi phần mở rộng thành .po. Xong rồi.

Khi bạn cập nhật một tập tin đã dịch một cách bộ phận, hay tập tin đã dịch cũ, thì có lẽ sẽ gặp một số dòng đầu vẫn còn chưa lập, hay quá hạn. 

:!: Vậy luôn luôn cần phải kiểm tra khối dòng đầu: hãy làm việc này trước hết, hãy làm nó sau hết (trước đệ trình tập tin dịch xong) thì bạn sẽ tránh sự khó.

Có hai dòng đầu có lẽ không xuất hiện trong khối ấy, nhưng mà tốt hơn nếu *có*. Bạn có thể tự thêm hai dòng ấy:

::

    "Report-Msgid-Bugs-To: \n"

và

::

    "Plural-Forms: nplurals=INTEGER; plural=EXPRESSION\n"

thế ở dưới đây chúng ta có một khối dòng đầu hoàn thành (hãy ghi chú vị trí của hai dòng đầu thêm):

::

    # SOME DESCRIPTIVE TITLE.
    # Copyright (C) YEAR THE PACKAGE'S COPYRIGHT HOLDER
    # This file is distributed under the same license as the PACKAGE package.
    # FIRST AUTHOR <EMAIL@ADDRESS>, YEAR.
    #
    #, fuzzy
    msgid ""
    msgstr ""
    "Project-Id-Version: PACKAGE VERSION\n"
    "Report-Msgid-Bugs-To: \n"
    "POT-Creation-Date: 2003-07-24 09:35+0200\n"
    "PO-Revision-Date: YEAR-MO-DA HO:MI+ZONE\n"
    "Last-Translator: FULL NAME <EMAIL@ADDRESS>\n"
    "Language-Team: LANGUAGE <LL@li.org>\n"
    "MIME-Version: 1.0\n"
    "Content-Type: text/plain; charset=CHARSET\n"
    "Content-Transfer-Encoding: 8bit\n"
    "Plural-Forms: nplurals=INTEGER; plural=EXPRESSION\n"

Mỗi dòng đầu làm một việc có ích, vì vậy chúng ta sẽ xem từng dòng:

\\

.. _../pages/guide/project/howtoviet#dòng_đầu_tên_gói:

Dòng đầu tên gói
""""""""""""""""

::

    # SOME DESCRIPTIVE TITLE.

  * Một tên diễn tả nào đó

cung cấp thông tin nhanh về tên của gói phần mềm này. Ở đây thì bạn hãy gõ *tên* của chương trình (không phải số phiên bản). Trong lời thí dụ bên dưới, tôi sẽ sử dụng chương trình `Tuxpaint <http://www.newbreedsoftware.com/tuxpaint/>`_ (một chương trình vẽ/sơn rất tốt cho đứa bé) và ngôn ngữ tôi, Việt ngữ.

::

    # Vietnamese translation of TuxPaint.

  * Bản dịch Việt ngữ của chương trình TuxPaint.

:!: Ghi chú rằng mọi dòng đầu này có *một dấu thăng # và một dấu cách* trước thông tin ấy. Trình kiểm tra, gồm rô-bốt, chỉ chấp nhận dấu đúng, vì hai dấu này là tin hiệu gettext của dòng đầu thông tin. Trình gettext thật phân tách thông tin này, và toàn tập tin. Như thế thì, khi chúng ta bảo đảm định dạng là đúng, sẽ không phải mất thời gian sửa lỗi khi trình gettext không phân tách được tập tin ấy.

\\

.. _../pages/guide/project/howtoviet#dòng_đầu_bản_quyền:

Dòng đầu bản quyền
""""""""""""""""""

::

    # Copyright (C) YEAR THE PACKAGE'S COPYRIGHT HOLDER

  * Bản quyền [ký hiệu bản quyền] năm nhà cầm quyền gói này

Trong trường hợp gói nào tại Dự án Thông dịch thì phần mềm thường là phần mềm nguồn mở, phần mềm tự do. Cho phần mềm loại này, thông tin thường là (dùng năm này):

::

    # Copyright © 2005 Free Software Foundation, Inc.

  * Bản quyền [ký hiệu bản quyền] năm 2005 Tổ chức Phần mềm Tự do

Nếu bạn có truy cập được ký hiệu bản quyền © một cách hơi dễ dàng trong bố trị bàn phím hay tính năng gõ ký tự đặc biệt, khi gõ nó thì hình như nghề nghiệp hơn. ;-)

Đôi khi gặp một tập tin có dòng đầu bản quyền sở hữu: một người nào đó đã tạo, và có quyền yêu sách tập tin ấy (lấy thí dụ):

::

    # Copyright © 2001-2005 Nguyễn Thị Hoa.

  * Bản quyền [ký hiệu] năm 2001-2005 của Nguyễn Thị Hoa

Trong trường hợp ấy thì bạn phải theo dòng đầu đã có. Đừng sửa đổi nó.

:!: Nếu tập tin của bạn có phải có dòng đầu bản quyền sở hữu, và trình rô-bốt từ chối nó vì không có dòng đầu bản quyền Tổ chức Phần mềm Tự do, như thế thì bản chỉ đơn giản hãy viết thư điện tử cho người điều hợp của Dự án Thông dịch tại:

translation AT iro d0t umontreal d0t ca((Phải viết địa chỉ thư điện từ như thế vì người gởi thư rác sẽ ăn cấp địa chỉ... :-( -- AT là dấu a-công; d0t là dấu chấm; không có dấu cách nào cả))

vì vấn đề ấy thuộc về dự án, không phải thuộc về bạn, dù đôi khi chúng ta có cảm thấy phật lòng khi tập tin mình bị từ chối vì có lỗi không phải của mình. Điều hợp viên cần phải lập một tùy chọn cho mỗi tập tin loại ấy, để tránh rô-bố từ chối nó khi bạn, hay người dịch khác, đệ trình nó lần kế tiếp. Hơn nữa, mỗi lúc chúng ta có thể đóng góp thời gian hay kinh nghiệm, chúng ta giúp nhau. ^_^
\\

.. _../pages/guide/project/howtoviet#dòng_đầu_bản_quyền_liên_quan:

Dòng đầu bản quyền liên quan
""""""""""""""""""""""""""""

::

    # This file is distributed under the same license as the PACKAGE package.

  * Tập tin này được phát hành với điều kiện của cùng quyền với gói TÊN này.

Dòng đầu này (không phải luôn luôn có trong tập tin, dù nên có) phát hành bản dịch với điều kiện của bản quyền tập tin gốc. Làm như thế tránh người khác yêu cầu bản quyền của bản dịch. Nếu bạn đang dịch trong Dự án Thông dịch thì đã điền đầy đủ một đơn từ chối trách nhiệm mà gán quyền bạn cho Tổ chức Phần mềm Tự do: làm như thế tránh nhiều sự khó, thì đơn giản hóa vấn đề quyền cho mọi người.

Ở đây thì bạn chỉ cần chèn lại tên của gói:

::

    # This file is distributed under the same license as the TuxPaint package.

  * Tập tin này được phát hành với điều kiện của cùng quyền với gói TuxPaint.

\\

.. _../pages/guide/project/howtoviet#danh_sách_các_người_dịch:

Danh sách các người dịch
""""""""""""""""""""""""

::

    # FIRST AUTHOR <EMAIL@ADDRESS>, YEAR.

  * Tác giả thứ nhất <địa chỉ thư điện từ>, năm.

Dòng đầu này có chưa lập chỉ nếu bạn là người thứ nhất để dịch tập tin ấy. Nếu nó đã được dịch, ngay cả bộ phận, trước đó, thì sẽ có ở đây tên của mỗi người dịch trước, trên từng dòng. Vậy nếu chỉ có một người dịch (tôi sẽ sử dụng tên mình):

::

    # Clytie Siddall <clytie@máy_chủ_nào.net.au>, 2005.

  * Tên họ tôi, địa chỉ thư, năm này.

Tuy nhiên, nếu đã có người dịch trước, sẽ có nhiều dòng đầu người dịch. Lấy thí dụ:

::

    # pclouds <pmây@máy_chủ_khác.com>, 2002.
    # Tran Minh Thanh <tmt@yahhooo.com>, 2004.
    # Clytie Siddall <clytie@máy_chủ_nào.net.au>, 2005.

Vậy về lý thuyết, tập tin có thể chứa rất nhiều dòng đầu loại này, riêng từng, nhưng mà trong thực hành, thường gặp một đến năm dòng đầu.

:!: Đừng sửa đổi dòng đầu người dịch trước nào, chỉ hãy chèn dòng đầu mình bên dưới dòng đầu người dịch trước mới nhất. Những dòng đầu người dịch này bảo đảm mọi người đã cố dịch tập tin này thì cả hai được thừa nhận, và nhận trách nhiệm làm cộng việc của mình.

\\

.. _../pages/guide/project/howtoviet#dòng_đầu_rỗng:

Dòng đầu rỗng
"""""""""""""

::

    #

Có lẽ bạn xem một dòng đầu rỗng giữa hai phần khối đầu tập tin. Nó cho bạn đọc khối này một cách dễ hơn. Bạn không cần làm gì ở đây. ;-)

\\

.. _../pages/guide/project/howtoviet#dòng_đầu_mờ:

Dòng đầu mờ
"""""""""""

::

    #, fuzzy

  * mờ

Hãy ghi chú rằng tại đầu dòng này, có một dấu phẩy sau dấu thăng #. Hai dấu này đều ngú ý là trình gettext đọc dòng đầu này như là *thông tin* về các khối chuỗi trong tập tin ấy. Nếu tập tin có dòng đầu này thì vẫn còn chứa chuỗi chưa dịch hay/và chuỗi có lỗi trong nó. Trình biên soạn .po có lẽ sẽ tự động loại bỏ nó một khi bạn đã dịch xong tập tin ấy, hoặc nếu bạn đang sử dụng một trình biên soạn văn bản thường mà không phải được thiết kế để quản lý những dòng đầu .po, thì bạn có thể tự loại bỏ nó. Chỉ xóa bỏ toàn dòng. Xong rồi.

Chuỗi *mờ* là chuỗi chưa dịch hay không đúng. Trình gettext quyết định đánh dấu ấy ở đâu, đựa vào (lấy thí dụ) nếu mọi dấu nháy kép, mọi biến và mọi ký tự ngắt dòng trong mỗi chuỗi của cặp thì khớp với nhau hay không. Nó sé cũng quyết định nó bằng cách kiểm tra nếu chuỗi từ điển nào do trình *msgmerge* đệ nghị thì khớp chuỗi gốc hay không. Mỗi chuỗi mờ có dấu mờ: cần phải kiểm tra nó một cách cẩn thận. Có thông tin thêm về tiến trình ấy xuống trang này. 8-)

*Tài liệu hướng dẫn gettext:* `fuzzy strings: chuỗi mờ <http://www.gnu.org/software/gettext/manual/html_mono/gettext.html#SEC46>`_ 

\\

.. _../pages/guide/project/howtoviet#cặp_chuỗi:

Cặp chuỗi
"""""""""

::

    msgid ""
    msgstr ""

Cặp chuỗi rỗng này ngụ ý cho trình gettext, tôi giả sử, cấu trúc của các chuỗi trong tập tin ấy. Chuỗi **msgid** (MeSsaGe ID: mã nhận diện thông điệp) là đoạn trong ngôn ngữ gốc, còn chuỗi **msgstr** (MeSsaGeS TRanslated) là bản dịch. 

:!: Tập tin xuất thì phải chứa mỗi cặp chuỗi, "được bao bằng dấu nháy kép". Đừng sửa đổi dòng đầu này.

\\

.. _../pages/guide/project/howtoviet#dòng_đầu_phiên_bản_gói:

Dòng đầu phiên bản gói
""""""""""""""""""""""

::

    "Project-Id-Version: PACKAGE VERSION\n"

  * Phiên bản mã nhận diện dự án: phiên bản gói

Ở đây, phiên bản gói có phải là quan trọng: cần phải theo dõi dòng đầu này khi cập nhật tập tin nào. 

:!: Trình rô-bốt của Dự án Thông dịch cần thiết tên của chương trình và phiên bản có định giới bằng một dấu cách, không phải bằng một dấu gạch dưới hay dấu gạch nối. Trong cách ấy, dòng đầu này khác với tên tập tin gốc.

Tên tập tin gốc: tuxpaint-2.1pre

::

    "Project-Id-Version: Tuxpaint 2.1pre\n"

:!: Hãy nhớ để sửa đổi dòng đầu này mọi khi cập nhật tập tin nào

Bạn nên sử dụng tất cả thông tin trong phần phiên bản của tên tập tin: 0.03a2, 2.01b, 0-03.2pre2, có phải là thông tin có ích về giai đoạn phát triển của gói này.

  * **a** có thể có nghĩa an-pha, một bản phát hành rất sớm, thường hơi bất ổn, chỉ nhằm mục đích thử nghiệm thôi; 
  * **b** có thể có nghĩa bê-ta, một bản thử nghiệm sau, thường hơi ổn định nhưng mà chưa bảo đảm gì hay hỗ trợ gì. Bạn có thể học biết nhiều và giúp đỡ phát triển phần mềm bằng cách thử nghiệm phần mềm bê-ta, dành cho cách hỗ trợ ngôn ngữ khác. :-)  
  * **pre** có thể có nghĩa là *trước* phát hành hoàn thành, phiên bản cuối cùng trước phiên bản phát hành hoàn thành: đã thử ra xong rồi. Rất có thể có nghĩa là phiên bản hoàn thành sẽ xuất hiện trước lâu thì bạn sẽ cần phải cập nhật lại tập tin ấy. 

Nếu bạn đang sử dụng chương trình nào đã dịch mình, hãy nhớ để kiểm tra phiên bản và thông tin tại nơi Mạng của nó, để quyết định nếu trình ấy ổn định chưa. Nếu bạn chọn giúp đỡ thử nghiệm một chương trình nào đó, hay lắm! với điều kiện là bạn không ngờ nó có ổn định hoàn thành hay cung cấp sự hỗ trợ kỹ thuật. Còn những lập trình viên và người khác đóng góp cùng với bạn bằng cách thử nghiệm, có phải sẽ vui lòng thỏa luận chương trình ấy và hỗ trợ nhau trong hộp thư chung của trình ấy. ;-)

\\

.. _../pages/guide/project/howtoviet#dòng_đầu_thông_báo_lỗi_chuỗi:

Dòng đầu thông báo lỗi chuỗi
""""""""""""""""""""""""""""

::

    "Report-Msgid-Bugs-To: \n"

  * Thông báo lỗi trong chuỗi msgid cho

Bình thường, lập trình viên bỏ sót hay không điền vào dòng đầu này, mà làm phiền chúng ta, vì nó là địa chỉ liên lạc để sử dụng khi một chuỗi ngôn ngữ gốc là không đúng (thiếu dấu, thiếu từ, cú pháp hay gõ/chính tả sai), hoặc khi chúng ta chưa hiểu một chuỗi nào đó đủ khá để dịch nó.

Có mất thời gian nhiều nếu chúng ta cần phải trở về trang nhóm chúng ta tại Dự án Thông dịch, nhắp vào tên tập tin ấy để đi tới miền văn bản của nó (trang dành cho nó tại dự án ấy), rồi tìm kiếm trang chủ của chương trình, hoặc thông tin liên lạc khác nào. Thường cần phải Google trong một thời gian để tìm nó.

Khi bạn tìm được địa chỉ liên lạc ấy, vui lòng điền nó vào tập tin của bạn. Vậy người kế tiếp, có thể bạn :-) , sẽ không cần phải mất thời gian để tìm kiếm nó. Ý kiến tốt là đệ nghị lập trình viên điền vào dòng đầu này.

:?: Đã tìm biết một số điều hữu ích về địa chỉ thông báo:

  * mọi gói GNU có địa chỉ thông báo lỗi này:

bug-TÊN_GÓI@gnu.org

  * mọi lỗi GNOME được thông báo thông qua trang Mạng `Bugzilla <http://bugzilla.gnome.org/>`_

  * mọi lỗi Debian được thông báo thông qua thư điện tử cho

owner AT bugs d0t debian D0t org 

với tên tập tin là chủ đề, và thận thư bắt đầu với:

::

    Package: TÊN_TẬP_TIN
    Version: SỐ_PHIÊN_BẢN
    Severity: wishlist
    Tags: l10n, patch

\\

.. _../pages/guide/project/howtoviet#ngày_tạo_tập_tin_này:

Ngày tạo tập tin này
""""""""""""""""""""

::

    "POT-Creation-Date: 2004-07-24 09:35+0200\n"

(Ngày đã tạo tập tin mẫu gốc [.pot]: năm-tháng-ngày giờ:phút+múi_giờ_thế_giới)

Tập tin .pot là tập tin gốc, chưa dịch, thì ngày ấy là lúc trình gettext tạo phiên bản tập tin này. Tập tin đã cập nhật sẽ có ngày tạo .po.

Thông tin này không quan trọng cho bạn (đừng sửa đổi nó), trừ:

:!: bạn sẽ cần phải kiểm tra xem ngày sửa đổi (ngày khi bạn hiệu chỉnh tập tin này) là **sau** ngày tạo: nếu không thì trình gettext hay rô-bốt sẽ nói «Không phải!» và đúng vậy. Chúng ta người dịch chưa tìm biết cách đảo ngược thời gian. LOL

\\

.. _../pages/guide/project/howtoviet#dòng_đầu_ngày_sửa_đổi_cuối_cùng:

Dòng đầu ngày sửa đổi cuối cùng
"""""""""""""""""""""""""""""""

::

    "PO-Revision-Date: YEAR-MO-DA HO:MI+ZONE\n"

(Ngày sửa đổi tập tin .po: năm-tháng-ngày giờ:phút+múi giờ)

Dòng đầu này chưa điền trong tập tin .pot gốc, vì chưa sửa đổi (dịch) nó. Trong một tập tin đã cập nhật thì sẽ có một ngày sửa đổi. Chúng ta chỉ cần phải nhớ:

:!: để cập nhật ngày nào trước khi đóng góp tập tin dịch xong 

Một trình biên soạn tập tin .po có lẽ sẽ tự động cập nhật ngày nào. Bạn có thể tự làm như thế trong bất cứ giai soạn nào. Trong trình BBEdit (Mac OSX) có thể tạo một mục từ điển cổ ngữ dùng biến strftime (chỉ hãy lưu nó và sử dụng nó, không cần phải hiểu cách hoặt động):

::

    "PO-Revision-Date: #LOCALTIME %F %R%z#\n"

Mục này, nếu trình hay hệ thống của bạn có thể điền giá trị strftime, sẽ hiển thị dòng đầu này đúng cho bạn, tại bất cứ nơi nào trên khắp thế giới. Trong trường hợp tôi, khi viết câu này

::

    "PO-Revision-Date: 2005-05-24 20:11+0930\n"

:!: Hãy ghi chú thứ tự ngày ấy: năm-tháng-ngày, năm có bốn số tự, tháng có hai số và ngày cũng có hai số. Đây có nghĩa cần phải gồm số không đi trước khi số ấy nhỏ hơn số mười, như trong tháng hiện có: 05 (tháng năm).

Ghi chú số hiệu giờ thế giới. Nó nói là múi giờ tôi (thành phố Adelaide tại Úc, thời gian Trung Úc, không phải thời gian mùa hè) là 9.5 giờ, chín giờ nửa, sau giờ thế giợi (GMT hay UTC: 00:00).

:!: Nếu bạn không có trình như BBEdit có thể điền giá trị strftime cho bạn thì cần phải nhớ để điền múi giờ mình ở đây. Cần phải nhớ để gõ số không đi trước nếu, như trong trường hợp tôi, chỗ bạn nhỏ hơn mười giờ sau hay trước UTC.

\\

.. _../pages/guide/project/howtoviet#dòng_đầu_người_dịch_mới_nhất_cuối_cùng:

Dòng đầu người dịch mới nhất (cuối cùng)
""""""""""""""""""""""""""""""""""""""""

::

    "Last-Translator: FULL NAME <EMAIL@ADDRESS>\n"

(Người dịch cuối cùng: TÊN HỌ <ĐỊA CHỈ THƯ ĐIỆN TỪ)

Khi bạn là người dịch *duy nhất* thì tên bạn sẽ xuất hiện cả hai trong dòng đầu Người Dịch Thứ Nhất, và đây trong dòng đầu Người Dịch Cuối Cùng, mà có lẽ sẽ làm cho bạn cảm thấy như là Người Dịch Có Thể Duy Nhất. LOL

Bạn chỉ hãy điền tên và địa chỉ thư vào đây, lần nữa, nhưng mà đừng gồm năm, như trong dòng đâù Người Dịch Thứ Nhất, vì Ngày sửa đổi .po có cung cấp nó.

Nếu có tên của người dịch trước điền vào đây, bạn cần phải sửa đổi nó để hiển thị tên bạn. Hãy chắc chắn có tên người dịch trước trong phần đầu của khối đầu (người dịch thứ nhất, thứ hai, thứ ba v.v.).

Vậy trong trường hợp tôi, dòng đầu này sẽ hiển thị"

::

    "Last-Translator: Clytie Siddall <clytie@máy_chủ_nào.net.au>\n"

(Người dịch cuối cùng: tên họ <địa chỉ thư>)

\\

.. _../pages/guide/project/howtoviet#dòng_đầu_nhóm_ngôn_ngữ:

Dòng đầu nhóm ngôn ngữ
""""""""""""""""""""""

::

    "Language-Team: LANGUAGE <LL@li.org>\n"

(Nhóm ngôn ngữ: NGÔN NGỮ <ngôn_ngữ@hộp_thư_chung.org>)

Ở đây có nơi công nhận nhóm ngôn ngữ bạn cho các sứ cố gắng của họ. Nó cũng cung cấp một địa chỉ liên lạc thêm cho người nào viết cho bạn về bản dịch. Nó thật có ích khi địa chỉ thư điện tử trở thành cũ, khi người nào dụ lịch hay thay đổi chi tiết.

Nhóm ngôn ngữ của bạn sẽ là tên của ngôn ngữ, và đôi khi của dự án. Địa chỉ sẽ thường là hộp thư chung nhóm. Vậy trong trường hợp tôi, dòng đầu này là:

::

    "Language-Team: Vietnamese <gnomevi-list@lists.thatserver.net>\n"

(Nhóm ngôn ngữ: Việt Nam <địa chỉ hộp thư chung)

hay

::

    "Language-Team: Gnome-Vi <gnomevi-list@lists.thatserver.net>\n"

(Nhóm ngôn ngữ: nhóm Việt Nam tại dự án GNOME <địa chỉ hộp thư chung)

\\

.. _../pages/guide/project/howtoviet#dòng_đầu_phiên_bản_mime:

Dòng đầu phiên bản MIME
"""""""""""""""""""""""

::

    "MIME-Version: 1.0\n"

(Phiên bản MIME: 1.0)

:!: Để tìm lời nghĩa của nhiều từ cấu tạo và kỹ thuật Mạng, bạn thăm gia trang tôi: `Những từ cấu tạo bằng chữ đầu của những từ khác thường nhất của Mạng <http://www.riverland.net.au/~clytie/viet/netacrvn.html>`_ mà tôi sẽ cố cập nhật một cách đều đặn.

Dòng đầu phiên bản MIME thường đã điền vào rồi. Bạn không cần làm gì. Hay quá, phải không? :-D

\\

.. _../pages/guide/project/howtoviet#dòng_đầu_kiểu_nội_dung:

Dòng đầu kiểu nội dung
""""""""""""""""""""""

::

    "Content-Type: text/plain; charset=CHARSET\n"

(Kiểu nội dung: chữ/thô; bộ ký tự=BỘ_KÝ_TỰ)

:!: Đây thật sự là quan trọng. Dòng đầu này lập bộ ký tự cho ngôn ngữ bạn. UTF-8 (Unicode: mã hoàn thành) là tùy chọn tốt nhất, nhưng mà nếu ngôn ngữ bạn cần thiết bộ ký tự khác, hãy điền nó vào đây. Cho ngôn ngữ tôi:

::

    "Content-Type: text/plain; charset=UTF-8\n"

(Kiểu nội dung: chữ/thô; bộ ký tự=Unicode)

Unicode là tuyệt vời! Dễ hơn rất nhiều để có thể quên các mã chữ khó quá cũ ấy ... Lúc này chỉ cần mọi hệ điều hành hỗ trợ Unicode một cách tốt hơn. 8-O

\\

.. _../pages/guide/project/howtoviet#dòng_đầu_cách_mã_hóa_nội_dung_để_truyền:

Dòng đầu cách mã hóa nội dung để truyền
"""""""""""""""""""""""""""""""""""""""

::

    "Content-Transfer-Encoding: 8bit\n"

(Dòng đầu cách mã hóa nội dung để truyền: 8bit)

Dòng đầu này cũng nên đã điền vào rồi. Nếu chưa, bạn hãy gõ **8bit**, cách mã hóa có thể quản lý UTF-8 và bộ ký tự phức tạp khác trong khi truyền. Bạn không muốn bản dịch đã làm việc nhiều của tôi sẽ bị hỏng trong khi đóng góp nó, hoặc khi nó được gởi cho lập trình viên.

\\

.. _../pages/guide/project/howtoviet#dòng_đầu_hình_dạng_số_nhiều:

Dòng đầu hình dạng số nhiều
"""""""""""""""""""""""""""

::

    "Plural-Forms: nplurals=INTEGER; plural=EXPRESSION\n"

(Các hình dạng số nhiều: nplurals=SỐ_NGUYÊN; plural=BIỂU_THỨC -- nplurals và plural là tên biến)

Thường dòng đầu này không có trong khối đầu tập tin, nhưng mà *nên* gồm nó. Khi bạn gặp chuỗi số nhiều (plural: diễn tả nhiều người hay điều) thì dòng đầu số nhiều này bảo đảm có số trường đúng cần gõ chuỗi đã dịch. Số này biến thay từ một ngôn ngữ đến ngôn ngữ khác. Cho ngôn ngữ tôi:

::

    "Plural-Forms: nplurals=1; plural=0\n"

(Hình dạng số nhiều: cần chỉ một trường cho chuỗi đã dịch, không cần trường thêm)

vì Việt ngữ không có hình dạng số nhiều về ý nghĩa đó. Một quyển, hai quyển. Nhưng mà bạn nên xem tập hợp đại từ... 8-)

Một số ngôn ngữ có vài hình dạng số nhiều. Một chuỗi msgid số nhiều hình như đây:

::

    msgid "Found and replaced %d occurrence."
    msgid_plural "Found and replaced %d occurrences."

(chuỗi gốc: đã tìm và thay thế một lần
chuỗi số nhiều gốc: đã tìm và thay thế nhiều lần)

vì Anh ngữ, ngôn ngữ gốc trong tập tin này, *có phải* có hình dạng số nhiều về ý nghĩa này. Nếu ngôn ngữ bạn hành vi cùng với Anh ngữ thì bạn sẽ gặp hai trường msgstr để gõ, như dưới:

::

    msgid "Found and replaced %d occurrence."
    msgid_plural "Found and replaced %d occurrences."
    msgstr[0] ""
    msgstr[1] ""

[0] là chuỗi một
[1] là chuỗi số nhiều

nhưng mà trong trường hợp tôi, nó nên là:

::

    msgid "Found and replaced %d occurrence."
    msgid_plural "Found and replaced %d occurrences."
    msgstr[0] ""

Nếu dòng đầu số nhiều trong tập tin bạn được lập cho đúng thì bạn sẽ gặp trường msgstr số đúng và kiểu đúng. Vậy nó hữu ích lắm. 

:!: Find out what yours is, and make sure you fill it in for all your files: it will save you hassle.

Nếu bạn chưa chắc về dòng đầu số nhiều nên lập cho ngôn ngữ bạn, hãy hỏi người chủ nhóm ngôn ngữ -- và nếu họ chưa chắc, thì có thể thỏa thuận trường hợp ấy trong :doc:`hộp thư chung Dự án Thông dịch <https///lists.sourceforge.net/lists/listinfo/translation-i18n>`, một nơi rất tốt để hỏi câu và chia kinh nghiệm.

\\
Các dòng đầu ấy là tất cả cần điền. Hết rồi. Mọi dòng đầu này có tiết kiệm thời gian khi địa phương hóa một ứng dụng nào đó. Bạn có thể lập chúng trong trình biên soạn .po, hoặc chỉ đơn giản lưu một bản sao của chúng để dán trên khối dòng đầu cũ hay gốc.

:!: Khi bạn cố điền các dòng đầu này cho đúng, và tìm biết cách mình để quản lý chúng, bạn trở thành một người dịch tốt hơn, vì người thông mình làm việc thì sử dụng công cụ một cách tốt nhất. Định dạng .po là một công cụ của chúng ta.

:?: *tập tin hướng dẫn gettext:* 

`the po format: định dạng .po <http://www.gnu.org/software/gettext/manual/html_mono/gettext.html#SEC9>`_

`filling in the header entry: điền vào mục nhập đầu <http://www.gnu.org/software/gettext/manual/html_mono/gettext.html#SEC35>`_
----

.. _../pages/guide/project/howtoviet#lấy_tập_tin_từ_đâu:

Lấy tập tin từ đâu?
------------------- 

`Trang nhóm bạn <http://www.iro.umontreal.ca/translation/registry.cgi?team=index>`_ ((Nếu ngôn ngữ bạn chưa có nhóm thì hãy liên lạc với địều hợp viên về tạo một nhóm.)) tại Dự án Thông dịch sẽ liệt kê các tập tin công bố để dịch. Bạn cần phải hỏi người chủ nhóm về tập tin cần dịch, hay hỏi để dịch tập tin nào đó, và họ sẽ thông báo dự án ấy là bạn được gán cho tập tin ấy. Tên bạn sẽ xuất hiện cạnh nó trong trang nhóm bạn. Vậy có trở thành người dịch của Dự án Thông dịch (TP: Translation Project) thế nào?

.. _../pages/guide/project/howtoviet#để_trở_thành_một_người_dịch_tp:

Để trở thành một người dịch TP
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Bạn hãy đăng ký với `TP <http://www.iro.umontreal.ca/translation/HTML/index.html>`_. Làm như thế là đơn giản, dù có một trì hoãn: đơn từ chối trách nhiệm.

  * Người chủ nhóm bạn có thể gởi thư cho điều hợo viên TP

Họ sẽ thông báo điều hợp viên biết rằng bạn muốn gia nhập dự án ấy, hoặc họ có thể hỏi bạn làm như thế với quyền họ, nhưng mà quan trọng là bạn có *cùng nhóm*, vì vậy có người chủ nhóm.

Một nhóm ngôn ngữ có thể hỗ trợ nhau, và chắc chắn làm việc thông dịch một cách bền bỉ. Không tốt khi có nhiều người khác dịch một cách riêng sang cùng một ngôn ngữ, không phải liên lạc với nhau, hoặc cộng tác với nhau. Dự án Thông dịch yêu cầu mọi thay đổi do người chủ nhóm quản lý, để tránh xung đột và lẫn lộn về ai làm gì, thế nào và sao. 8-)  

:!: Kiểm tra nói chuyện với người chủ nhóm bạn, mà sẽ giúp đỡ bạn nhiều, tham gia hộp thư chung của nhóm, và gia nhập TP.

  * Một khi bạn đã đang ký với TP 

(bạn tự làm với quyền người chủ nhóm, hoặc thông qua người chủ nhóm), bạn hãy điền vào `đơn từ chối trách nhiệm TP <http://www.iro.umontreal.ca/translation/HTML/disclaim.html>`_ (disclaimer), ký tên nó, và gởi nó qua điện thư hay bữu điện cho Tổ chức Phần mềm Tự do.

Nếu bạn gặp khó khăn hiểu thông tin ấy, hoặc gởi đơn ấy, người chủ nhóm sẽ giúp đỡ bạn.

Bạn cũng có thể in đơn ấy, điền vào nó và ký tên nó, quét nó và đính nó kèm thư điện tử. Cách nào là tốt, với điều kiện là đơn ấy được nhận tại Tổ chức Phần mềm Tự do (Free Software Foundation: FSF), và có được ghi lưu với họ tên bạn. Khi đã làm như thế, tên bạn trong trang nhóm sẽ hiển thị:

|             |  Disclaimer  |  
|(Họ tên bạn) |     Yes      |

(đơn từ chối trách nhiệm: Có)

Tại sao làm như thế? Thêm vào đơn giản hóa vấn đề bản quyền, như nói trên, lý do có, hầu hết tập tin TP không phải công bố để dịch tới khi đã ghi lưu đơn từ chối trách nhiệm tại FSF. Khi bạn nhắp vào ten tập tin trong trang nhóm, và đi tới trang dành cho tập tin (miền văn bản: textual domain) thì hãy kiểm tra xem xuống trang ấy có nên nói cần phải hoàn thành tiến trình đơn từ chối trách nhiệm.

:!: Cho đến khi đã ghi lưu đơn từ chối trách nhiệm bạn tại FSF thì bạn chỉ có thể dịch tập tin không cần đơn ấy, nhưng mà có một số tập tin ấy thì dịch đi nhé. ;-D

.. _../pages/guide/project/howtoviet#lấy_tập_tin_mới_nhất_thế_nào:

Lấy tập tin mới nhất thế nào?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Danh sách các tập tin trong `trang nhóm bạn <http://www.iro.umontreal.ca/translation/registry.cgi?team=index>`_ *nên* là những tập tin mới nhất. Lập trình viên gởi mỗi tập tin cho TP để dịch, và nên tự động gởi nó khi cập nhật. Rất quan trọng để dịch tập tin mới nhất: nếu không thì có lẽ sẽ không bao giờ sử dụng bản dịch của bạn, hoặc phần lớn người sẽ không sử dụng nó. Tải tập tin xuống trang nhóm bạn tại TP nên bảo đảm bạn lấy tập tin mới nhất.

:!: Nếu bạn gập tập tin nào không phải mới nhất (rất ít khi, nhưng mà có thể) thì vui lòng gởi thư cho điều hợp viên TP để mà có thể sửa nó.

Phương pháp tạo và bảo trì tập tin mới nhất thì gồm CVS, SVN và kho riêng. TP tránh bạn phải học biết quản lý hệ thống phiên bản hóa ấy, bằng cách bảo trì những tập tin mới nhất công bố cho bạn. Bạn chỉ hãy tải chúng xuống trang nhóm bạn. Nhắp vào tên tập tin, mà sẽ mang bạn tới trang dành cho tập tin ấy. Nhắp vào liên kết có tên tập tin (liên kết thứ nhất trong trang ấy). Bạn đã lấy một tập tin rồi! ;-)

.. _../pages/guide/project/howtoviet#tự_động_cập_nhật:

Tự động cập nhật
^^^^^^^^^^^^^^^^

Nếu bạn đã xin TP gởi cho địa chỉ bạn mọi tập tin mà cập nhật tập tin của bạn, thì nó sẽ đơn giản đến vào Hộp Đến của bạn. Bạn không cần tải nó về. :-D 

Việc cập nhật thường là nhanh, vì vậy là tốt để nhận tự động tâp tin ấy. Một tập tin nào đó có thể được tải lên TP với vài chuỗi mới hay đã sửa đổi, được gởi cho người dịch mà sửa đổi nó và trở nó về, toàn trong cùng ngày. *Làm như thế* là hệ thống hiện thời. 8-)

:?: Dự án khác có tài liệu hướng dẫn về lấy tập tin mới nhất: hãy hỏi người chủ nhóm bạn.
----

.. _../pages/guide/project/howtoviet#tập_tin_mới_tạo:

Tập tin mới tạo
--------------- 

Bạn có bắt đầu rõ: không có ai đã sửa đổi tập tin này trước này. ;-)

.. _../pages/guide/project/howtoviet#sửa_đổi_khối_dòng_đầu:

Sửa đổi khối dòng đầu
^^^^^^^^^^^^^^^^^^^^^ 

như nói và hiển thị trên.

.. _../pages/guide/project/howtoviet#không_phải_lập_lại:

Không phải lập lại
^^^^^^^^^^^^^^^^^^

Tin tức tốt, vào lúc này, là bạn không phải tự gõ mọi chuỗi riêng vào tập tin mới tạo ấy, nếu bạn có tập tin từ điển nào (compendium). Một bản trích yếu là một bản chú giải do gettext tạo. Người chủ nhóm bạn nên có thể cho bạn biết bản chú giải hiện thời cho ngôn ngữ bạn. Chũng ta cần định dạng bản chú giải *Compendium*, bản trích yếu, cho tiến trình dòng lệnh bên dưới.

Tốt nhất là để sử dụng cùng những bản chú giải với các người nhóm, vì tự vựng bền bỉ là quan trọng. Nó làm cho người dùng ít lẫn lộn hơn, và cho họ ít kỹ thuật mới hơn để quản lý. Khi bạn đang bắt đầu sử dụng máy tính, hay sử dụng một chương trình mới (mọi người đang học biết suốt đời) thì vô ích để cần phải lo lăng về nhiều cách khác để nói cùng một điều.

Một **compendium** (bản trích yếu) là một tập tin văn bản do gettext xây dụng, bằng hợp nhất nội dung của nhiều tập tin .po đã dịch xong. Bạn có lẽ sẽ muốn lưu nhiều bản trích yếu khác nhau cho kiểu tập tin khác nhau: tôi có bản trích yếu khác cho tập tin chương trình chính, trò chơi, tập tin ISO và chương trình tính. Bạn có thể áp dụng bất cứ số bản trích yếu nào vào một tập tin .po.

Khi bạn áp dụng một bản trích yếu vào một tập tin .pot mới tạo, được gọi là *khởi động* tập tin ấy, thì trình gettext cố khớp mỗi chuỗi gốc với chuỗi và bản dịch được ghi lưu vào bản trích yếu. Nếu khớp chính xác thì trình gettext sẽ điền vào chuỗi msgstr hoàn thành cho bạn. Nếu khớp gần đúng ((trong ý kiến của gettext, và nhiều người thảo luận vấn đề này :-))) thì nó điền chuỗi đã dịch vào trường msgstr, nhưng mà cũng áp dụng thẻ **mờ** vào khối chuỗi ấy. Dấu mờ có nghĩa là «Hãy kiểm tra chuỗi này, vì tôi chưa chắc.» Dù nếu chuỗi ấy chưa dịch xong, nó có lẽ sẽ tiết kiệm thời gian bạn: có lẽ một chữ hoa hay sự chấm câu là khác, hay một phần câu ... hoặc có lẽ nó khác hoàn thành, nhưng mà thường nó khớp được, và giúp đỡ chúng ta nhiều.

:!: Áp dụng bản trích yếu như thế nào? Đây là lệnh ấy (hãy lưu nó vào nơi dễ tìm):

::

    msgmerge --compendium bản_trích_dẫn.po -o tập_tin.po /dev/null tập_tin.pot

Lệnh này nói:

*Chương trình msgmerge* (chương trình làm hợp nhất của gettext), *dùng thông tin trong một tập tin bản trích yếu (compendium) có tên* (trong trường hợp này) *là bản_trích_dẫn.po* (có thể có bất cứ tên nào.po) *rồi xuất* (-o) *các dữ liệu đã hợp nhất từ bản trích yếu và tập tin .pot vào một tập tin tên tập_tin.po, vào /dev/null* (vì bạn không muốn dữ liệu đã hợp nhất, bạn muốn những dữ liệu khớp với nhau: «/dev/null» là giống như nói «bỏ đi», *và khởi động tập tin tên tập_tin.pot.*

Vì vậy, lệnh ấy có thể là:

::

    msgmerge --compendium bản_chú_giải1.po -o tập_tin.po /dev/null gnubiff.pot

Các phần lệnh ấy:

**msgmerge** - chương trình làm việc ấy

**--compendium** - tùy chọn nói «tạo một tập tin bản chú giải với các dữ liệu này»

**bản_chú_giải1.po** - tên tập tin của tập tin bảnchú giải đã có, hay tên tập tin cho bản mới

**-o** - xuất sự hợp nhất của hai tập tin ấy

**tập_tin.po** - vào tập tin này

**/dev/null** - rồi mất nó, vì tôi không muốn dữ liệu hợp nhất ấy

**gnubiff.pot** - còn để các chuỗi khớp được vào tập tin này (tập tin bạn muốn dịch)

Vậy bạn chỉ hãy gõ tên của bản chú giải, compendium, thay vào *bản_chú_giải* ở trên, và gõ tên của tập tin bạn muốn dịch, thay vào *gnubiff.pot*.

:!: Ghi chú là toàn đường dẫn, mọi thư mục mà trình msgmerge cần phải đi qua để tìm tập tin ấy, là phần của tên tập tin. Hai tập tin trong lời thí dụ ở đây có thể là:

::

    Tài_liệu/Bản_chủ_giải_/bản_chủ_giải.po

and

::

    Tài_liệu/TP/gnubiff-2.1.3/gnubiff.pot

:!: Khi gõ tên tập tin trong thiết bị cuối, hãy sử dụng phím Tab để điền các tên còn lại, một khi bạn đã gõ các chữ khớp với tập tin khác trong thư mục ấy.

Dùng lệnh msgmerge này có lẽ được nhiều chuỗi khớp, hay có lẽ không được: nó phụ thuộc vào số lượng dữ liệu trong bản chú giải mà liên quan đến tập tin mới của bạn. Bạn có thể liệt kê nhiều bản chú giải, riêng từng, nếu bạn muốn áp dụng nhiều bản:

::

    msgmerge --compendium bản1.po bản2.po bảnA.po -o tập_tin.po /dev/null gnubiff.pot

Nhất là, khi bạn dịch một số tập tin làm việc giống nhau, hoặc bạn quyết định lần kế tiếp người nào hỏi bạn dịch nút «OK» thì bạn sẽ kêu thét lên và ném cái nào, vào lúc ấy trình msgmerge có thể tránh nhiều sự khó cho bạn. Nó là một công cụ thông dịch hữu ích nữa của chúng ta. (Toàn công việc thông dịch đã rất phức tạp trước khi có trình gettext.)
----

.. _../pages/guide/project/howtoviet#tập_tin_chưa_xong:

Tập tin chưa xong
----------------- 

Trước hết, hãy cập nhật khối đầu tập tin, như được hiển thị ở trên. Số phiên bản, chi tiết người dịch và ngày sửa đổi là đoạn khóa khi cập nhật.

Bạn có thể sử dụng lệnh msgmerge với một tập tin chưa xong: nó sẽ đơn giản cố khớp chuỗi nào chưa dịch.

Trước khi chúng ta sửa đổi thận tập tin, đây là một số từ nữa tiết kiệm thời gian về xây dụng bản trích yếu cho mình.
----

.. _../pages/guide/project/howtoviet#bản_chú_giải_mình:

Bản chú giải mình
-----------------

Tạo bản chú giải mình, bản trích yếu (compendia ((compendium là một từ Latinh: một compendium, nhiều compendia [một mẫu số nhiều La-tinh]))) là một tiến trình đơn giản mà một số trình biên soạn .po có sẵn. Trong trình `LocFactoryEditor <http://www.triplespin.com/en/products/locfactoryeditor.html>`_, lấy thí dụ, tôi có thể tạo, hợp nhất và áp dụng bất cứ số bản chu giải nào trong nhiều định dạng khác nhau (tôi thường sử dụng .tmx).

Nếu bạn đang sử dụng dòng lệnh thì vẫn còn có thể làm việc ấy như bên dưới, mỗi lúc bạn dịch xong một tập tin và muốn thêm các bản dịch trong nó vào tập tin bản trích yếu (compendium):

::

    msgcat -o bản_trích_yếu.po tập_tin.po tập_tin.po

Lệnh này nói: *chương trình msgcat* (chương trình phân loại của gettext), *để các dữ liệu xuất* (-o) * công việc này vào một tập tin tên bản_trích_yếu.po* (nếu có một tập tên tên ấy trong vị trí ấy thì sẽ hợp nhất với nó -- có ích để cập nhật bản trích yếu). *Lấy mọi dữ liệu từ những tập tin này: tập_tin1.po và tập_tin2.po*

vậy nó có thể là:

::

    msgcat -o bản_chú_giảiA.po gnubiff.po

nếu bạn đang thêm chỉ một tập tin vào bản_chú_giảiA, hoặc

::

    msgcat -o bản_chú_giải_đứa_bé.po tuxpaint.po gcompris.po

nếu bạn đang thêm hai tập tin ấy vào bản trích yếu chương trình đứa bé của bạn.

Tiến trình compendium tiết kiệm nhiều thời gian cho chúng ta thì vui lòng mất thời gian ít cần thiết để sử dụng nó. Bạn có thể hỏi câu, hay xin giúp đỡ, trong :doc:`hộp thư chung TP <https///lists.sourceforge.net/lists/listinfo/translation-i18n>`, như nói trên.

:!: Tôi đã ghi lưu hai lệnh ấy vào một nơi dễ xem, vậy khi tôi cần chúng, tôi có thể sao chép chúng vào thiết bị cuối. Nếu bạn sử dụng chúng nhiều lần, có lẽ chúng sẽ bám vào trí nhớ bạn. Hiện thời, trí nhớ tôi không hơi bám dính. Giống như hơn bùn đặc, tôi nghĩ. :-/

*tập tin hướng dẫn gettext:*

`invoking the msgmerge program: gọi chương trình msgmerge <http://www.gnu.org/software/gettext/manual/html_mono/gettext.html#SEC37>`_

`using translation compendia: sử dụng bản trích yếu thông dịch <http://www.gnu.org/software/gettext/manual/html_mono/gettext.html#SEC54>`_
----

.. _../pages/guide/project/howtoviet#dịch_tập_tin:

Dịch tập tin
------------

Bạn đã lập khối dòng đầu, bạn đã sử dụng những bản trích yếu để cung cấp chuỗi có thể nào, và bạn rất muốn xem các điều hơi lạ mà lập trình viên đã gian lận lồng vào chúng ta lần này -- ừm, là thời gian dịch. ^_^

Tập tin .po của bạn, ngoại lệ khối đầu, chứa hoàn thành khối chuỗi. Mỗi khối chuỗi tiêu biểu một chuỗi sẽ được hiển thị dạng đã dịch trong chương trình mà tập tin .po đã tạo ra từ nó. Nó có lẽ là chữ trên cái nút, trên thanh công cụ, trong thông điệp lỗi hay cửa sổ mẹo, bất cứ nơi nào trong chương trình gặp nó, nó là một khối chuỗi trong tập tin .po của chúng ta. Khối chuỗi tại khắp nơi! :-D

Đây là cấu trúc của khối chuỗi:

::

    #.Type: boolean
    #.Description
    #:../exim4-base.templates.master:4
    msgid "Remove undelivered mails in spool directory?"
    msgstr ""

Khối này có cấu trúc thật tốt, từ dự thông dịch án trình cài đặt Debian. Hãy ghi chú có hai dòng bắt đầu với dấu # và dấu chấm. -- #.  mà ngụ ý:

.. _../pages/guide/project/howtoviet#chú_thích_lập_trình_viên:

Chú thích lập trình viên
^^^^^^^^^^^^^^^^^^^^^^^^

::

    #.Tôi là một chú trích lập trình viên. :)

Lập trình viên có thể giúp đỡ chúng ta rất nhiều bằng cách chèn chú thích diễn tả mỗi chuỗi, hoặc hướng dẫn cách định dạng nó. Hầu hết tập tin .po chưa có chú thích lập trình viên có ích, vì vậy tập tin này là bất thường. Vui lòng đệ nghị lập trình viên chèn chú thích, thêm vào dòn đầu Thông báo lỗi msgid. 8-)

Đây là một lời thí dụ thật sự tuyệt vời của chú thích lập trình viên, từ dự án thông dịch trình cài đặt Debian lần nữa:

::

    #.Type: select
    #.Choices
    #.Translators beware! the following six strings form a single
    #.Choices menu. - Every one of these strings has to fit in a standard
    #.80 characters console, as the fancy screen setup takes up some space
    #.try to keep below ~71 characters.
    #.DO NOT USE commas (,) in Choices translations otherwise
    #.this will break the choices shown to users
    #:../exim4-config.templates.master:9
    msgid "internet site; mail is sent and received directly using SMTP"
    msgstr ""

Các thông tin này là rất hữu ích.

Trong lời thí dụ trước, mà vẫn còn diễn tả chuỗi khá hơn tập tin .po thường:

::

    #.Type: boolean
    #.Description
    #:../exim4-base.templates.master:4
    msgid "Remove undelivered mails in spool directory?"
    msgstr ""

những hai chú thích lập trình viên cho bạn biết:

  - Chuỗi ấy có kiểu (type) chỉ có trả lời Đúng hay Không đúng (boolean) (trong máy tính, trả lời chỉ 1 hay 0).

  - Chuỗi diễn tả điều cho người dùng (description).

Dòng kế tiếp diễn tả nơi trong chương trình chứa chuỗi ấy. Đôi khi những dòng này có thể giúp đỡ chúng ta hiểu công việc của chuỗi ấy, nhưng không phải thường. Chúng là tham chiếu nội bộ của chương trình. :-/

Trong khi chúng ta nói chuyện về chú thích, chúng ta cũng có thể chèn chú thích. 

.. _../pages/guide/project/howtoviet#chú_thích_người_dịch:

Chú thích người dịch
^^^^^^^^^^^^^^^^^^^^

::

    # Tôi là một chú thích người dịch. ;)

:!: Chú thích loại này thật sự hữu ích khi nhiều người dịch cùng một tập tin.

Trong bất cứ trường hợp nào, trong tương lai có lẽ người khác sẽ sửa đổi bản dịch trong tập tin này, vì vậy có ích để chèn một chú thích khi hãy ghi chú gì.

Chú thích người dịch phải được chèn tại đầu khối chuỗi, sau khoảng cách sau khối trước (khoảng cách «trắng»): hãy ghi chú một toàn dòng rỗng trước mỗi chú thích người dịch mà tôi đã trích dẫn ở đây. Chú thích người dịch có một dấu #, rồi một dấu cách, không phải dấu chấm câu. Lấy thí dụ, chị đã chèn chú thích giống như điều này nhiều lần:

::

    # Don't translate this: it's a variable. Đừng dịch chuỗi này vì là biến.

Thế có thẻ gặp:

::

    # Don't translate this: it's a variable. Đừng dịch chuỗi này vì là biến.
    #. login window data
    #:../exim4-base.templates.master:4
    msgid "(${NAME})"
    msgstr "(${NAME})"

hoặc bạn có thể đệ nghị một cách nào đó để diễn tả hay định dạng m điều nào. Đừng dè dặt không muốn chèn chú thích người dịch: người dùng chương trình ấy không thể xem nó. Có lẽ bạn tự hỏi một số lập trình viên biết trường chú thích lập trình viên là dành cho cho chúng ta biết gì: một số chương trình chứa chỉ chú thích lập trình viên nói chuyện với nhau, ngay cả lăng mạ người dùng. Không tốt. :-(

:!: Trong thời gian dịch mỗi khối chuỗi, đừng cần biết mọi điều. Các chúng ta cần phải hỏi câu, tham chiếu đến thông tin đặc biệt, thỏa thuận với nhóm ngôn ngữ. Có rất nhiều chương trình khác nhau tạo ra tập tin .po -- không có ai biết mọi điều trong hết.

Một số chuỗi (có lẽ nhiều chuỗi) sẽ làm cho chúng ta lẫn lỗn, có lẽ chúng rất khó hiểu: nhiều lập trình viên không có khả năng diễn tả tốt, ngay cả trong ngôn ngữ mình. Mọi ý kiến về cú pháp tốt hơn, vui lòng gồm khi tạo chuỗi đã dịch. Công việc chúng ta là diễn ta chuỗi ấy một cách tốt nhất cho cộng đồng ngôn ngữ chúng ta.

:!: Mức đích không phải là để dịch từ hay kỹ thuật chính xác, vì kỹ thuật máy tính được chọn vì vắn.

Từ giống như «icon» và «text» đã không phải thường dùng trong Anh ngữ trước khi có máy tính cá nhân. Vì vậy bạn có thể chọn một từ hay biểu thức vắn mà tiêu biểu nghĩa được. Lấy thí dụ, từ «icon» trong Việt ngữ là «biểu tượng» mà dài hơn nhiều. Khi chỗ là quan trọng, trong mục trình đơn hay chữ trên cái nút, hoặc là tên của cột trong bảng, thì tôi sử dụng từ «hình» hay «ảnh», vì hai từ ấy có gần cùng kích thước với từ «icon» và, trong văn cảnh ấy, nơi người dùng ngờ một hình nhỏ, thì có nghĩa thích hợp. Đang tạo và phát triển các kỹ thuật máy tính trong mọi ngôn ngữ: bạn có dịp giúp đỡ tạo và sửa đổi nó cho cộng đồng ngôn ngữ mình.

Rất có thể là cộng đồng ngôn ngữ bạn sẽ có một dự án xây dụng bản chú giải các kỹ thuật máy tính, nơi bạn có thể đệ nghị, tìm và thỏa thuận kỹ thuật thích hợp. Chúng tôi (nhóm Việt ngữ) có một dự án xây dụng bản chú giải loại ấy trực tuyến tại `đây <http://vnoss.org/evgs/index.php?action=search>`_. 

:!: Ý kiến gõ của bạn là quan trọng: mức đích là để truyền thông một cách hữu ích với người dùng, không phải để mô phỏng chính xác lập trình viên nói bằng tiếng Anh.

Công việc này cũng đầy thách thức hơn nếu văn hóa bạn khác nhiều với văn hóa Anh. Như thế thì bạn hãy cho phép mình dịp nghĩ cẩn thận về công việc của mỗi chuỗi, và về cách truyền thông nó với người dùng trong cộng đồng ngôn ngữ mình.

Lấy thí dụ, bằng Việt ngữ, chúng tôi hiển thị nhận mạnh nhiều bằng chọn từ dứt khoát hơn với dấu chấm than. Hơn nữa, dấu trích dẫn xung đột với nghĩa, vì ngôn ngữ chúng tôi dùng nhiều dấu phụ để diễn tả nghĩa khác trong từ có cùng chữ La-tinh, vì vậy khi dịch, tôi sử dụng «dấu ngoặc này» thay vào dấu trích dẫn. Cách nói chuyện từ máy tính với người dùng gần luôn luôn không thích hợp trong văn hóa Việt Nam: tôi cần phải tìm thấy cách thích hợp để diễn đạt công việc của chuỗi ấy. Lấy thí dụ:

::

    msgid "Choosing a simple root password is a really dumb idea."

(Chọn một mật khẩu chủ đơn giản là một ý kiến ngu lắm.)

Máy tính nói câu này là vô lễ trong văn hóa Việt Nam, và hoàn thành không thích hợp, vì vậy câu tôi bằng Việt ngữ giống như hơn:

::

    msgstr "It is not a good idea to choose a simple root password."

(Không phải ý kiến tốt để chọn mật khẩu chủ đơn giản.)

vì hình dạng ấy là nhiều mạnh trong văn hóa Việt Nam hơn trong văn hóa Anh, hơi đủ mạnh để lôi cuốn sự chú ý của người dùng tại mức độ đúng.

:!: Hãy ghi chú: còn lập trình viên có lẽ là nhà chuyên môn về cách hoạt động của chương trình ấy, bạn và các bạn nhóm ngôn ngữ có phải là người hiểu được ngôn ngữ và văn hóa mình, thì *bạn* cần chọn cách diễn đạt nghĩa, và cách thích hợp nhất nói với người dùng.

.. _../pages/guide/project/howtoviet#chuỗi_cũ:

Chuỗi cũ
^^^^^^^^

::

    #~ msgid "I am an obsolete string. Nobody loves me. Boo-hoo. :("
    #~ msgstr "Tôi là một chuỗi cũ. Không có ai thương tôi. Hu-hu. :(" 

Mọi chuỗi cũ bắt đầu với dấu băm # và dấu sóng ~.

::

    #~ msgid "Forward _Quoted"
    #~ msgstr "Chuyển tiếp _trích dẫn"

Một số tập tin (không phải mọi tập tin) có một số chuỗi tại kết thức tập tin mà cặp chuỗi msgid và msgstr cả hai bắt đầu với dấu băm, và thường cũng với dấu sóng mà trên mấy tính đánh dấu thư mục người dùng trên đĩa cứng. *Nó không phải có nghĩa ấy ở đây.*

:!: Trong tập tin .po, các chuỗi bắt đầu #~ hiện thời do chương trình ấy không dùng.

Vậy tại sao giữ lại chúng? Tôi cũng đã hỏi câu này. Về lý thuyết, có lẽ sẽ dùng lại chuỗi ấy lần sau. Như thế thì không cho phép chung ta xóa bỏ chúng, và phải dịch chúng. Tuy nhiên, bạn có thể tự quyết định mất bao nhiều thời gian và sức mạnh làm công việc ấy. Chắc chắn có lỗi trong tiến trình giữ lại chuỗi cũ: tôi đã gặp tập tin gần hoàn thành chuỗi cũ à.

Trình biên soạn .po của bạn có lẽ ẩn các chuỗi ấy. Trình LocFactoryEditor chỉ hiển thị chuỗi cũ nếu có dấu mờ, hoặc nếu tôi hỏi.

*tập tin hướng dẫn gettext:* `obsolete strings: chuỗi cũ <http://www.gnu.org/software/gettext/manual/html_mono/gettext.html#SEC48>`_
----

.. _../pages/guide/project/howtoviet#mẹo_kiểu_dạng:

Mẹo kiểu dạng
-------------

Để tiết kiệm thời gian gỡ lỗi ra tập tin này sau dịch thì có vài điều bạn cần phải nhớ trong khi dịch.

:!: Không bao giờ sửa đổi chuỗi gốc (msgid). 

Thông tin trong chuỗi này thuộc về chương trình ấy thì nếu bạn sửa đổi nó bằng bất cứ cách nào, sửa đổi ngay cả một dấu cách hoặc di chuyển một từ lên hay xuống một dòng, hành động ấy sẽ làm cho lập trình viên gặp khó khăn khi cố hợp nhất lại tập tin ấy vào chương trình gốc. 

:!: Nếu bạn gặp lỗi trong chuỗi msgid, vui lòng thông báo cho lập trình viên.

Bạn có làm như thế dùng địa chỉ Report-Msgid-Bugs-To (Thông báo các lỗi trong msgid cho) trong khối đầu, hoặc, nếu không có nó thì bạn cần phải đi tới trang miền văn bản cho tập tin này (nhắp vào liên kết là tên nó trong trang nhóm bạn), và theo liên kết để tìm được một địa chỉ liên lạc (có thể cần phải Google để tìm được nó). Một khi bạn đã tìm nó, vui lòng điền nó vào dòng đầu Report-Msgid-Bugs-To vì vậy không có người dịch tập tin này trong tương lại sẽ phải mất thời gian tìm kiếm lại nó. ;-)

Ghi nhớ: khi bạn viết thư cho lập trình viên, hãy lễ phép. Rất dễ để cảm thấy nôn nóng khi đang gỡ lỗi tập tin hỗn độn thứ n, nhưng mà vui lòng ghi nhớ rằng lập trình viên cũng đóng góp thời gian cá nhân, và có lẽ họ không có khả năng tiếng Anh hơi tốt, hoặc ngay cả hiểu cách hoạt động của tiến trình gettext. Hãy kết bạn nhé: có dịp hay quá. :-D

:!: Mỗi chuỗi phải "Bắt đầu và kết thức với một dấu trích dẫn đôi."

  * Nhiều tập tin vẫn còn có cấu trúc cũ mà mỗi nơi ngắt dòng phải kết thức và bắt đầu lại dùng dấu trích dẫn. Hành động này có kết quả này:

::

    #: ../gedit/gedit-document.c:1964
    msgid ""
    "The disk where you are trying to save the file has a limitation on file "
    "sizes.  Please try saving a smaller file or saving it to a disk that does "
    "not have this limitation."

Kiểu dạng này đã trở thành bị phản đối thì dù bạn không bao giờ có sửa đổi được chuỗi gốc, bạn có thể định dạng *chuỗi dịch* dùng kiểu dạng hiện có: một dấu trích dẫn đôi tại đầu và cuối. Vậy trong tập tin tôi:

::

    #: ../gedit/gedit-document.c:1964
    msgid ""
    "The disk where you are trying to save the file has a limitation on file "
    "sizes.  Please try saving a smaller file or saving it to a disk that does "
    "not have this limitation."
    msgstr "Đĩa được dùng để lưu tập tin này có giới hạn về kích thước tập tin. 
    Hãy lưu một tập tin nhỏ hơn hoặc lưu tập tin này vào đĩa không đặt ra giới 
    hạn trên."

Trong kinh nghiệm tôi, chúng ta có thể loại bỏ dấu trích dẫn thêm khi không có ký tự ngắt dòng hình thức (\n). Khi có ký tự \n thì tôi đã tìm biết có phải để các dấu trích dẫn thêm, tại đầu và cuỗi của mỗi dòng trong chuỗi dịch, cùng định dạng với chuỗi gốc msgid.

((Khối chuỗi này bắt đầu với một chú thích người dịch của tôi.))

::

    # Do not translate the upper-case quoted terms: they are values for the configuration. Đừng dịch kỹ thuật đã trích dẫn bằng chữ hoa vì là giá trị cho cấu hình.
    #: ../data/gedit.schemas.in.h:77
    msgid ""
    "Style for the toolbar buttons. Possible values are \"GEDIT_TOOLBAR_SYSTEM\"\n"
    "to use the system's default style, \"GEDIT_TOOLBAR_ICONS\" to display icons\n"
    "only, \"GEDIT_TOOLBAR_ICONS_AND_TEXT\" to display both icons and text, and\n"
    "\"GEDIT_TOOLBAR_ICONS_BOTH_HORIZ\" to display prioritized text beside icons.\n"
    "Note that the values are case-sensitive, so make sure they appear exactly as\n"
    "mentioned here."
    msgstr "Kiểu dáng cho nút thanh công cụ. Giá trị có thể là \"GEDIT_TOOLBAR_SYSTEM\"\n"
    "cho kiểu mặc định của hệ thống, \"GEDIT_TOOLBAR_ICONS\" nếu chỉ hiện thị các\n"
    "biểu tượng, \"GEDIT_TOOLBAR_ICONS_AND_TEXT\" nếu hiện cả biểu tượng và chữ.\n"
    "Và \"GEDIT_TOOLBAR_ICONS_BOTH_HORIZ\" để hiển thị chữ ưu tiên cạnh biểu\n"
    "tượng. Chú ý là phải viết hoa các giá trị để đảm bảo chúng được hiển thị\n"
    "đúng như đã nói."

mà hình như nhiều xe đi mua hàng va nhẹ vào nhau. :-/

:!: Mỗi dòng kết thức với ký tự ngắt dòng (\n) trong chuỗi gốc msgid phải cũng kết thức với ký tự ấy trong chuỗi dịch msgstr.

Quy tắc này không có nghĩa là bạn phải giữ cùng tổng số dòng: chuỗi dịch có thể có nhiều hay ít dòng hơn chuỗi gốc. Tuy nhiên, khi chuỗi gốc có ký tự ngắt dòng thì mỗi nơi ngắt dòng trong chuỗi dịch phải có ký tự ngắt dòng (\n). Lấy vài thí dụ:

::

    #: ../data/gedit.schemas.in.h:74
    msgid ""
    "Specifies the number of spaces that should be displayed instead of Tab\n"
    "characters."
    msgstr "Xác định số khoảng trắng được hiển thị thay vì ký tự Tab."

Chuỗi dịch là đúng, vì nó vắn hơn thì *không* cần phải ngắt dòng.

::

    #: ../data/gedit.schemas.in.h:74
    msgid ""
    "Specifies the number of spaces that should be displayed instead of Tab\n"
    "characters."
    msgstr "Xác định số khoảng trắng được hiển thị thay vì ký tự Tab, và một 
    số từ thêm nữa không cần thiết."

Chuỗi dịch không đúng, vì nó *có* cần phải ngắt dòng, cùng với chuỗi gốc, nhưng mà chưa dùng ký tự \n cùng với nó.

Vì vậy, chuỗi dịch này là đúng:

::

    #: ../data/gedit.schemas.in.h:74
    msgid ""
    "Specifies the number of spaces that should be displayed instead of Tab\n"
    "characters."
    msgstr "Xác định số khoảng trắng được hiển thị thay vì ký tự Tab, và một\n
    số từ thêm nữa không cần thiết."

và ngay cả chuỗi dịch này là đúng:

::

    #: ../data/gedit.schemas.in.h:74
    msgid ""
    "Specifies the number of spaces that should be displayed instead of Tab\n"
    "characters."
    msgstr "Xác định số khoảng trắng được hiển thị thay vì ký tự Tab, và một\n
    số từ thêm nữa không cần thiết. Hơn nữa, tôi có thể nói chuyện bằng cách\n
    này được mấy ngày."

Để tóm tắt: chuỗi dịch phải có định dạng cùng với chuỗi gốc. Nếu chuỗi gốc cần phải ngắt dòng (dùng ký tự \n) tại một số ký tự nào đó (thường 70 hay 80), thì chúng ta phải làm cũng vậy, bất cháp cần phải sử dụng bao nhiều dòng.

Bạn đã thấy ký tự chéo ngược \ có trong ký tự ngắt dòng (\n). Chéo ngược là một ký tự đặc biệt trong tập tin .po (cũng trong nhiều định dạng khác). Còn «n» là chữ thường, và «N» là chữ hoa, «\n» là một ký tự ngắt dòng. 

:!: Cách thường khác để dùng chéo ngược trong tập tin .po là để *thoát* dấu trích dẫn đôi.

Như bạn đã thấy biết, dấu trích dẫn đôi có công việc trong khối chuỗi rồi. Chũng nói:

*Chuỗi gốc hay dịch bắt đầu **"đây**, và kết thức **đó"***

Vậy khi trình gettext phân tách có kiểm tra cú pháp trong tập tin .po thì nó không cố đọc thông tin giữa hai dấu trích dẫn đôi như là lệnh của nó. Nó có thể làm biếng đọc gì cho đến khi dấu trích dẫn đôi kế tiếp báo nó kết thức làm biếng và bắt đầu làm việc lại. :-) 

Đúng vậy, nhưng mà nếu chuỗi chính nó chứa dấu trích dẫn đôi thì hãy làm gì? Ối... chúng ta xem đây nhé:

::

    #:../src/window-commands.c:162
    msgid "See the "Quick Help" for a list of commands."
    msgstr "" 

Có làm gì vậy? Này, chúng ta biết rằng trình phân tách sẽ xử lý dấu trích dấn đôi thứ hai là kết thức chuỗi. Cũng hơi tốt... Sau đó, nó sẽ cố đọc mọi điều là lệnh cho nó ... cho đến nó gặp một dấu trích dẫn đôi nữa, mà nó sẽ xử lý là bắt đầu chuỗi khác.

::

    #:../src/window-commands.c:162
    msgid "See the "
    Quick Help" for a list of commands."
    msgstr "" 

Không tốt. Bạn sẽ thấy biết cách lẫn lộn của trình gettext trong trường hợp ấy, khi bạn quên chèn dấu trích dẫn đôi, hoặc chèn một dấu thêm. :-D

Máy là chúng ta có thể *thoát* trường hợp này, bằng cách sử dụng ký tự chéo ngược có ích. Ký tự chéo ngược báo trình phân tách bỏ qua cách hoạt động thường của dấu trích dẫn đôi ấy. Như thế thì có kết quả:

::

    #:../src/window-commands.c:162
    msgid "See the \"Quick Help\" for a list of commands."
    msgstr "Hãy xem «Trợ giúp nhanh» để tìm danh sách các lệnh." 

Chuỗi gốc này hình như lạ một chút, nhưng mà chỉ có dấu chéo ngược *thoát* mỗi dấu trích dẫn đôi thêm. Nếu bạn sử dụng dấu trích dẫn đôi trong chuỗi dịch, chỉ cần phải nhớ để *thoát* mỗi dấu. Tuy nhiên, có lẽ ngôn ngữ bạn sử dụng «dấu này», như ngôn ngữ tôi, và dấu này không có công việc trong tập tin .po thì không cần phải thoát nó. Hết rồi. ;-)

:!: Tổng số và loại biến trong chuỗi gốc và chuỗi dịch phải khớp với nhau.

Biến thường có định dạng nào đó, chính strftime và printf, nhưng mà một quy tắc chung tốt là mọi điều không phải là từ bình thường thì rất có thể là một biến. **Không** bao giờ sửa đổi biến nào, vì nó là bộ giữ chỗ cho chương trình gốc. Lệnh trong chương trình ấy, lấy thí dụ, báo nó: khi gặp biến %s trong chuỗi có mã c:219 thì phải thay thế tên người dùng của người dùng hiện thời. Trong trường hợp ấy, chuỗi này trong tập tin .po ấy:

::

    #: src/gbiff2.c:219
    #, c-format
    msgid "Welcome to gnubiff, %s!\n"

sẽ do chương trình ấy sẽ dùng để hiển thị:

***Welcome to gnubiff, Clytie!***

nếu «Clytie» là tên dùng của tôi trên hệ thống ấy.

Trong trường hợp ấy, đơn giản có thể dịch câu ấy, không di chuyển biến, rất có thể hoặt động được:

::

    #: src/gbiff2.c:219
    #, c-format
    msgid "Welcome to gnubiff, %s!\n"
    msgstr "Chúc mừng vào gnubiff, %s!\n"

Ghi chú rằng chuỗi này ngắt dòng, dù nó hơi vắn. Chương trình ấy sẽ cần phải làm như thế vì lý do hiển thị, vậy chúng ta đơn giản theo cùng định dạng.

Dù chúng ta có thể theo cấu trúc của câu ấy khi dịch, chèn biến... 

:!: Bạn sẽ luôn luôn tạo một bản dịch có rất nhiều chất lượng hơn khi bạn mất thời gian một chút để nghĩ về công việc của chuỗi ấy trong chương trình gốc.

Có thể gặp khó khăn làm như thế khi không có chú thích của lập trình viên mà diễn tả chuỗi gốc. Tuy nhiên, trong chuỗi loại này, bạn có thể thấy biết rằng chương trình thường nói chuyện với người dùng bằng cách thuyết hình người này. Trong trường hợp này, trong ngôn ngữ và văn hóa tôi, tốt hơn để loại bỏ dấu chấm than (mà không phải thích hợp), chọn động từ «dùng» thay vào «vào», và để biến người dùng trước khi động từ ngầm (dùng), như dưới:

::

    #: src/gbiff2.c:219
    #, c-format
    msgid "Welcome to gnubiff, %s!\n"
    msgstr "Chúc mừng %s dùng gnubiff.\n"

**Welcome, Clytie, to using gnubiff.**

Bạn có thể thay đổi vị trí của biến, như trong thí dụ này, với điều kiện là bạn không phải thay đổi **thứ tự** của các biến trong chuỗi ấy. Một số chuỗi gốc có nhiều biến (láy thí dụ):

::

    #: src/gbiff2.c:219
    #, c-format
    msgid "Welcome to %s, %s!\n"

mà báo chương trình thay thế vào nơi thứ nhất, tên của phần chương trình hoạt động hiện thời, và thay thế vào nơi thứ hai, tên dùng của người dùng hiện có:

**Welcome to gnubiff configuration widget, Clytie!**

(Chào mừng dùng ô điều khiển cấu hình gnubiff, Clytie.)

Vì lý do nói trên, khi dịch thì tôi để biến tên dùng sau «Chào mừng (dùng)», trong chuỗi này hành động ấy sẽ sửa đổi thứ tự của hai biến:

::

    #: src/gbiff2.c:219
    #, c-format
    msgid "Welcome to %s, %s!\n"
    msgstr "Chúc mừng %s dùng %s.\n"

**Welcome, gnubiff configuration widget, to Clytie.**

(Chào mừng ô điều khiển cấu hình gnubiff dùng Clytie.)

:-X

Trong trường hợp loại này, chúng ta chỉ cần ngụ ý cách sửa đổi thứ tự:

::

    #: src/gbiff2.c:219
    #, c-format
    msgid "Welcome to %s, %s!\n"
    msgstr "Chúc mừng %2$s dùng %1$s.\n"

bằng cách chèn hai chữ «2$» (mà nói «biến thứ hai») và «1$» (biến thứ nhất) giữa «%» và «s» của biến. Thay đổi này báo chương trình gốc rằng, dù biến «%2$s» có nơi thứ nhất trong chuỗi ấy, nó thật là biến thứ hai trong chương trình. «%1$s» có nơi thứ hai trong chuỗi, còn đã nhận diện nó là biến thứ hai. Như thế thì chương trình gốc có thể thay thế hai giá trị hiện thời thì tôi xem:

**Welcome, Clytie, to using gnubiff configuration widget.**

(Chừng mừng Clytie dùng ô điều khiển cấu hình gnubiff.)

=
_  
=
=

:!: Vậy bạn hãy giữ tổng số, hình thức chính xác và thứ tự biến trong chuỗi dịch cùng với chuỗi gốc. Nếu bạn cần thay đổi thứ tự biến thì hãy sử dụng tiến trình hiển thị ở trên.
----

.. _../pages/guide/project/howtoviet#kiểm_tra_tập_tin:

Kiểm tra tập tin
----------------

Nếu bạn quên điều nào, hay nhầm lẫn chúng bằng bắt cứ cách nào, đừng nản bạn, vì khi kết thức dịch tập tin ấy (hoặc vào bất cứ lúc nào) thì bạn có chạy được một lệnh sẽ kiểm tra có lỗi thường nào:

::

    msgfmt -cv /dev/null TÊN_TẬP_TIN

Lệnh này nói:

*chương trình msgfmt, phải kiểm tra* (-c) *các quy tắc ngôn ngữ (xuất* (-o) * các kết quả vào /dev/null vì tôi không muốn lưu một bản) vào tập tin này.*

Như thế thì trình msgfmt sẽ liệt kê (trong thiết bị cuối) bất cứ lỗi còn lại nào, có số thứ tự dòng và mô tả để bạn sửa. Nó sẽ báo bạn biết nếu có chuỗi vẫn còn mờ nào, và loại lỗi còn lại. Trình msgfmt là một công cụ rất hữu ích. :-)

Khi tôi chạy lệnh kiểm tra ấy trên tập tin dịch hiện có:

::

    Pearl:~/gnome/HEAD clytie$ msgfmt -cv gedit/po/vi.po

Ghi chú rằng vào lúc này tôi xuống hai mức độ từ thư mục chính (người dùng ~), ở trong danh mục «HEAD» mà ở trong danh mục «gnome», và tôi cần phải báo trình msgfmt rằng tập tin vi.po xuống hai mức độ từ chỗ tôi: ở trong danh mục «po» mà lần lượt ở trong danh mục «gedit». Bạn hiểu chưa? Mong hiểu rồi. Chung ta xem kết quả lệnh ấy nhé:

::

    Pearl:~/gnome/HEAD clytie$ msgfmt -cv gedit/po/vi.po
    gedit/po/vi.po:504: parse error
    gedit/po/vi.po:643: missing `msgstr' section
    gedit/po/vi.po:644: keyword "t" unknown
    gedit/po/vi.po:1385: keyword "C" unknown
    gedit/po/vi.po:1386: keyword "C" unknown
    gedit/po/vi.po:1402: keyword "C" unknown
    gedit/po/vi.po:1403: keyword "C" unknown
    gedit/po/vi.po:1409: keyword "C" unknown
    gedit/po/vi.po:1468: missing `msgstr' section
    gedit/po/vi.po:1469: keyword "n" unknown
    gedit/po/vi.po:1483: missing `msgstr' section
    gedit/po/vi.po:1484: keyword "ang" unknown
    found 12 fatal errors

  * parse error: lỗi phân tách
  * missing `msgstr' section: thiếu phần msgstr
  * keyword unknown: không biết từ khóa ấy

«Lỗi nghiêm trộng» không phải thật giết bạn, nhưng mà nó sẽ ngăn cản bạn  tập tin bạn đệ trình tập tin là hoàn thành. Ghi chú có số thứ tự dòng có ích: tôi sẽ không gặp khó khăn tìm xem lỗi ấy. Kinh nghiệm tôi đệ nghị tập tin này thiếu một số dấu trích dẫn đôi: đó là lý đó trình phân tách ((một chương trình đọc cú pháp, trong trường hợp này cú pháp của lệnh chương trình)) đang cố đọc chuỗi ấy như là lệnh, và không hiểu từ khóa (từ thứ nhất sau dếu trích dẫn đôi kết thức chuỗi).

Bạn có thể kiểm tra tập tin mình nhiều lần (bấm phím mũi tên lên để gõ lại lệnh mới dùng) cho đến khi nhận kết quả loại này:

::

    msgfmt -cv dasher/po/vi.po
    133 translated messages.

(133 thông điệp đã dịch: không có chuỗi vẫn còn mờ, không có chuỗi chưa dịch, không có lỗi.)

Vào lúc ấy, bạn có thể đệ trình tập tin mình. ;-)
----

.. _../pages/guide/project/howtoviet#đệ_trình_tập_tin:

Đệ trình tập tin
----------------

Để đệ trình một tập tin dịch xong ((hãy hỏi người chủ nhóm về tập tin nào không thể dịch xong)) thì bạn chỉ đơn giản hãy đính nó kèm thư điện từ rồi gởi nó cho địa chỉ của trình rô-bốt tại Dự án Thông dịch (TP).

:!: Phải bảo đảm chạy lệnh kiểm tra msgfmt trên tập tin ấy không có lỗi, chuỗi vẫn còn mờ hay chuỗi chưa dịch, trước khi gởi.

:!: Phải bảo đảm gõ chi tiết đúng vào dòng chủ đề: nếu không thì sẽ không chấp nhận tập tin bạn.

:!: Hãy bảo đảm đã sửa đổi tên tập tin thành «mã_ngôn_ngữ.po» (trong trường hợp tôi, thành «vi.po».

**Ghi chú: bạn có lẽ muốn giữ tên tập tin hoàn thành, v.d. (trong trường hợp tôi, cho tập tin gnubiff-2.3pre1) **gnubiff-2.3pre1.vi.po**, để tránh nhầm lẫn nhiều tập tin có cùng tên. Một sự phòng ngừa nữa là để «gzip» (nén) tập tin bạn trước khi đính nó kèm thư điện tử: hành động này tránh bộ ký tự bị hỏng trong khi truyền.
\\

**Địa chỉ thư điện tử nơi đệ trình tập tin:**

<file>
<translation AT iro đ0t umontreal Đ0t ca>
</file>

**Dòng chủ đề của thư ấy:**

<file>
TP Robot TÊN_GÓI.MÃ_NGÔN_NGỮ.po
</file>

Lấy thí dụ, cho tập tin gnubiff bằng Việt ngữ:

<file>
TP Robot gnubiff-2.1.3.vi.po
</file>

:!: Hãy bảo đảm gõ tên gói một cách chính xác, có một dấu gạch nối tên chương trình và số phiên bản, và có dấu chấm trong số phiên bản.

:!: Hãy bảo đảm có một dấu chấm giữa số phiên bản và mã ngôn ngữ, và giữa mã ngôn ngữ và phần mở rộng po.

Tôi đã tạo một mẫu trong trình thư:

  * Địa chỉ Cho -- translation(a-còng)iro(chấm)umontreal(chấm)ca

  * Chủ đề -- TP Robot TÊN_TẬP_TIN.vi.po

  * thận không có chữ ký hay mật mã

 vậy khi tôi muốn đệ trình tập tin, chỉ cần phải gõ chi tiết gói và đính kèm tập tin. Mẫu ấy tranh tôi làm lỗi trong các trường ấy, và dễ dàng để quên gõ một dấu cách/chấm, hay chèn dấu cách/chấm nhiều quá. Có lẽ bạn muốn thiết lập mẫu như vậy. Cho chương trình thư điện từ tôi, Mail trên hệ điều hành Mac OSX, tôi dùng `Mail Template <http://www.abracode.com/MailTemplate/moreinfo.html>`_, một chương trình tốt lắm để tiết kiệm thời gian và sự khó khi gởi cùng thư nhiều lần, ngay cả để xử lý thư đã nhận.

:?: gettext 0.14.3: trợ lý học tập nội bộ
----

.. _../pages/guide/project/howtoviet#sau_tài_liệu_này:

Sau tài liệu này
----------------

Mong bạn đã tìm biết thông tin này, mà tôi đã học biết bằng cách làm gần mọi lỗi có thể :-D , có ích. Mọi ý kiến về tài liệu này, vui lòng thêm vào nó. Tôi trông chờ đọc kinh nghiệm bạn.

:?: Nếu bạn gặp khó khăn hiểu bất cứ phần nào trong tài liệu này, vui lòng đóng góp thông điệp vào `diễn dàn VNOSS <http://forum.vnoss.org/index.php>`_ hay trong :doc:`hộp thư chung nhóm Việt Nam <https///lists.sourceforge.net/lists/listinfo/gnomevi-list>` của chúng ta, và tôi sẽ cố giải thích cho bạn hiểi được.

:?: Chúng tôi vui lòng nhận bản dịch của tài liệu này, hoặc của hướng dẫn nào về công việc thông dịch, bằng ngôn ngữ bạn.

Chúc bạn dịch vui trong cộng đồng Phần mềm Tự do sôi nổi và thân thiện.

Clytie