# Dynamic routes

Khi mỗi page path phụ thuộc vào data bên ngoài -> __dynamic URLs__

![Dynamic routes](https://nextjs.org/static/images/learn/dynamic-routes/page-path-external-data.png)

- Path có định dạng [id] (dynamic)

- ## getStaticPaths
        Trả về một mảng data hợp lệ cho path, cụ thể ở đây là [id]
        Nếu giá trị truyền vào path nằm ngoài list data từ __getStaticPaths__ thì sẽ chuyển sang trang __404__

- ## getStaticProps
        Fetch các external  data cần thiết dựa vào list data Path

- ### 404 Pages
To create a custom 404 page, __create pages/404.js__. This file is statically generated at build time.