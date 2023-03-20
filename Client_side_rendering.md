# Client Side rendering
If you __do not need__ to pre-render the data, you can also use the __Client-side Rendering__:

- Pre-render các phần của trang không yêu cầu external data
- Khi page loads, sử dụng JS để get external data và sinh đủ các chức năng trong trang

![Client-side Rendering](https://nextjs.org/static/images/learn/data-fetching/client-side-rendering.png)

- Cách này __phù hợp với Dashboard__ page vì là trang private nên không cần SEO, lượng người dùng cụ thể, trang không cần pre-rendered. Data update thường xuyên nên yêu cầu data fetching mỗi lần request


# SWR
Đội ngũ Next.js đã tạo ra 1 React hook cho data fetching là __SWR__. Được gợi ý nếu fetching data phía client. Nó giúp xử lý caching, revalidation, focus tracking, ...
