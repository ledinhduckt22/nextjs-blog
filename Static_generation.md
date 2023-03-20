# Static Generation

## Static Generation without Data

![Static Generation without Data](https://nextjs.org/static/images/learn/data-fetching/static-generation-without-data.png)

Tuy nhiên 1 số pages cần được gọi data (query database, call external API, access file system,..) ở build time -> ta có Static generation with data

![Static Generation with data](https://nextjs.org/static/images/learn/data-fetching/static-generation-with-data.png)

- Cách dùng:
    + Sử dụng **getStaticProps**, là một hàm async được chạy lúc build time, giúp get external Data và truyền vào như props của page

- Chúng ta có thể call external API hay query DB là do **getStaticProps** chỉ chạy trên __server side__, không chạy phía client. Điều này nghĩa là mình có thể viết code trực tiếp truy cập DB mà không gửi chúng đến browsers

- Vì **Static generation** chạy lúc build time nên __không thể sử dụng data__ mà chỉ available trong mỗi request như **query parameters** or **HTTP headers** (tức là mỗi request truyền tham số lên thì ta không thể đọc được)