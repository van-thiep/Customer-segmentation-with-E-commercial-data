# Customer-segmentation-with-E-commercial-data
E- commercial data là tập dữ liệu chứa thông tin giao dịch của khách hàng được thực hiện trên nền tảng thương mại điện tử trong vòng một năm. Bộ dữ liệu này bao gồm 8 cột như sau:
1. InvoiceNo: số hóa đơn
2. StockCode: mã sản phẩm được mua. Mã sản phẩm bắt đầu bằng ký tự 'C' có nghĩa là đơn hàng với sản phẩm này bị hủy.
3. Description: thông tin mô tả sản phẩm
4. Quantity: số lượng sản phẩm được mua
5. InvoiceDate: ngày ghi trên hóa đơn
6. UnitPrice: Gía sản phẩm
7. CustomerID: ID của khách hàng, mỗi khách hàng sẽ có một ID
8. Country: Tên của đất nước nơi khách hàng sống
M sẽ sử dụng bộ dữ liệu này để cluster products, cluster customer và classify customer.

## The structure of repo
1. Data preparation
2. Understanding data
3. Categorize product

Trong phần này m sẽ sử dụng cột description và những thông tin về giá để phân cụm sản phẩm. Đối với dữ liệu trong cột description m sẽ lấy ra các từ khóa trong mỗi description và sử dụng chúng làm feature. Ý tưởng của phần này là những sản phẩm có description chứa các từ khóa giống nhau có thể được phân vào cùng một cụm. Ngoài ra m cũng sử dụng thông tin về giá. M chia giá của sản phẩm thành các mức khác nhau và phân sản phẩm vào từng mức giá. Ys tưởng là những sản phầm có mức giá gần giống nhau sẽ có khả năng thuộc cùng một cụm.

   Sau khi đã tạo feature xong, m sử dụng KMeans và Gausisian mixture để phân cụm sản phẩm.
   
   Ngoài ra description là dữ liệu dạng text do đó ta có thể sử dụng các kỹ thuật **topic modeling** như **Gensim Linear Discriminant Analyse** để phân loại sản phẩm

4. Customer category

Với mục đích hiểu hiểu customer segmentation nên m không quá chú trọng vào feature engineering. Do đó m sử dụng những featre cơ bản để phân cụm khách hàng. Sau khi phân cụm xong, m chia khách hàng vào 11 cụm khác nhau.

5. Classify customer

Ở phần này m sẽ sử dụng KNN, SVM, Random forest để phân loại khách hàng vào 11 cụm. M cũng sử dụng GridSearch để tuning hyper-parameters
