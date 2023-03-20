# Pre-rendering

Mặc định, __Next.js pre-renders every page__. Điều này nghĩa là __Next.js pre-render HTML cho mọi page__, thay vì việc chúng được tạo ra bởi by client-side JavaScript. Pre-rendering cho kết quả tốt hơn với **performance and SEO**.

Mỗi phần HTML được sinh ra cùng 1 lượng JS code tối thiểu cần thiết cho page đó (tức là lúc này code chỉ có hiển thị chứ chưa đầy đủ chức năng). 

Khi 1 page được load bởi trình duyệt (để lấy full code), code JS chạy và làm page hoạt động full chức năng
 __(This process is called hydration)__

* Với React.js, khi disable JS và không có pre-render -> không thể nhìn thấy app (trang trắng)
----

## Two forms of Pre-rendering

1. **Static Generation**

    + Sinh ra HTML ở lúc **build time** (khi app được build để deploy lên môi trường production -> HTML được sinh ra)
    + HTML được pre-render có thể được tái sử dụng trên mỗi request 

2. **Server-side Rendering**

    + Phương thức pre-rendering, sinh HTML trên mỗi lần request

3. Trên **môi trường develop**, mỗi request đều hỗ trợ server-rendering và static generation

Tuy nhiên, trên **môi trường production**, **static generation** chỉ được __thực hiện 1 lần duy nhất__ lúc build time 
Tương tự với __getStaticPaths__

###Note:
- Next.js cho phép chúng ta quyết định loại pre-rendering thực hiện trên mỗi page

Vậy, khi nào dùng Static generation và khi nào dùng Server-side Rendering?

- Dùng static generation bất cứ khi nào có thể, vì nó chỉ sinh HTML 1 lần và được server by CDN nhanh hơn việc sinh HTML trên mỗi request. Ví dụ thực tế

    + **Marketing pages**

    + **Blog posts**

    + **E-commerce product listings**

    + **Help and documentation**

    + Nếu ta cần render this page trước khi user request -> sử dụng Static generation

- Nếu page content thay đổi mỗi lần request hoặc page thường cập nhật data -> sử dụng Server-side rendering (tuy chậm hơn nhưng page sẽ luôn mới nhất) hoặc client-side JS
