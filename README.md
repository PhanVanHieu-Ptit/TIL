# TIL
Today I Learned

# 📚 Frontend Learning Journal

<details>
<summary><strong>📅 2026-05-24 — Frontend Interview Theory (JavaScript + React)</strong></summary>

---

# 1. `var`, `let`, `const`

## 📝 Tóm tắt
`var`, `let`, `const` khác nhau ở scope, hoisting và khả năng reassign/redeclare. Trong code hiện đại nên ưu tiên `const`, dùng `let` khi cần thay đổi giá trị và hạn chế dùng `var`.

## 💻 Ví dụ thực tế

```js
const user = { name: "Hieu" };

user.name = "Frontend Dev"; // OK
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const

## ❓ Câu hỏi còn lại
- TDZ hoạt động như thế nào?
- Vì sao `const` object vẫn sửa được property?

---

# 2. Closure trong JavaScript

## 📝 Tóm tắt
Closure là khả năng function ghi nhớ scope bên ngoài kể cả khi scope đó đã execute xong.

## 💻 Ví dụ thực tế

```js
function createCounter() {
  let count = 0;

  return () => {
    count++;
    return count;
  };
}
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures

## ❓ Câu hỏi còn lại
- Stale closure trong React xảy ra thế nào?
- Closure có gây memory leak không?

---

# 3. Event Loop

## 📝 Tóm tắt
JavaScript xử lý async bằng Event Loop. Promise (microtask) luôn chạy trước `setTimeout` (macrotask).

## 💻 Ví dụ thực tế

```js
console.log(1);

setTimeout(() => console.log(2));

Promise.resolve().then(() => console.log(3));

console.log(4);
```

Output:

```txt
1
4
3
2
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Event_loop

## ❓ Câu hỏi còn lại
- React batching liên quan Event Loop như thế nào?
- Microtask queue khác callback queue ra sao?

---

# 4. React Re-render

## 📝 Tóm tắt
React re-render khi state, props hoặc context thay đổi. Object/array được compare bằng reference.

## 💻 Ví dụ thực tế

```js
const obj1 = {};
const obj2 = {};

console.log(obj1 === obj2); // false
```

## 🔗 Link tham khảo
- https://react.dev/learn/render-and-commit

## ❓ Câu hỏi còn lại
- Khi nào React.memo thực sự hiệu quả?
- Re-render bao nhiêu thì mới thành performance issue?

---

# 5. `useMemo` vs `useCallback`

## 📝 Tóm tắt
`useMemo` cache value, `useCallback` cache function reference. Không nên optimize quá sớm.

## 💻 Ví dụ thực tế

```js
const sortedData = useMemo(() => {
  return heavySort(data);
}, [data]);
```

```js
const onClick = useCallback(() => {
  handleSubmit(id);
}, [id]);
```

## 🔗 Link tham khảo
- https://react.dev/reference/react/useMemo

## ❓ Câu hỏi còn lại
- Khi nào memoization phản tác dụng?
- useCallback có cost gì?

---

# 6. Controlled vs Uncontrolled Component

## 📝 Tóm tắt
Controlled component để React quản lý state. Uncontrolled component để DOM tự quản lý thông qua `ref`.

## 💻 Ví dụ thực tế

```tsx
<input value={value} onChange={handleChange} />
```

```tsx
<input ref={inputRef} />
```

## 🔗 Link tham khảo
- https://react.dev/reference/react-dom/components/input

## ❓ Câu hỏi còn lại
- Vì sao React Hook Form performant hơn?
- Khi nào uncontrolled phù hợp hơn?

---

# 7. Redux Toolkit

## 📝 Tóm tắt
Redux Toolkit giảm boilerplate Redux và dùng Immer để hỗ trợ immutable update theo syntax mutate.

## 💻 Ví dụ thực tế

```js
const counterSlice = createSlice({
  name: "counter",
  initialState: { count: 0 },
  reducers: {
    increment: (state) => {
      state.count += 1;
    }
  }
});
```

## 🔗 Link tham khảo
- https://redux-toolkit.js.org/

## ❓ Câu hỏi còn lại
- Immer hoạt động bên trong ra sao?
- Khi nào Redux là overkill?

---

# 8. Polling vs WebSocket vs MQTT

## 📝 Tóm tắt
Polling liên tục request server. WebSocket giữ kết nối realtime 2 chiều. MQTT là lightweight pub/sub protocol phù hợp realtime tracking và IoT.

## 💻 Ví dụ thực tế

```txt
vehicle/location/123
```

## 🔗 Link tham khảo
- https://www.hivemq.com/mqtt-essentials/

## ❓ Câu hỏi còn lại
- QoS trong MQTT hoạt động thế nào?
- Khi nào MQTT tốt hơn WebSocket?

---

# 9. CSR vs SSR vs SSG vs ISR

## 📝 Tóm tắt
Các chiến lược rendering của Next.js ảnh hưởng SEO, performance và UX.

## 💻 Ví dụ thực tế

| Type | Use case |
|---|---|
| CSR | Dashboard realtime |
| SSR | SEO pages |
| SSG | Blog/docs |
| ISR | Dynamic content |

## 🔗 Link tham khảo
- https://nextjs.org/docs/app/building-your-application/rendering

## ❓ Câu hỏi còn lại
- ISR regenerate page như thế nào?
- Khi nào SSR gây bottleneck?

---

# 10. React Performance Optimization

## 📝 Tóm tắt
Tối ưu React app tập trung vào giảm unnecessary re-render, lazy loading, caching và bundle optimization.

## 💻 Ví dụ thực tế

```js
const Table = React.memo(BigTable);
```

```js
const UserPage = lazy(() => import("./UserPage"));
```

## 🔗 Link tham khảo
- https://react.dev/learn/render-and-commit

## ❓ Câu hỏi còn lại
- Khi nào nên dùng virtualization?
- Làm sao đo performance bằng React Profiler?

</details>

<details>
<summary><strong>📅 2026-05-25 — Frontend Theory Notes</strong></summary>

---

# 11. `useEffect` hoạt động như thế nào?

## 📝 Tóm tắt
`useEffect` dùng để xử lý side effects trong React như fetch API, subscribe realtime, timer hoặc cleanup resource.

## 💻 Ví dụ thực tế

```js
useEffect(() => {
  const interval = setInterval(() => {
    console.log("running...");
  }, 1000);

  return () => clearInterval(interval);
}, []);
```

## 🔗 Link tham khảo
- https://react.dev/reference/react/useEffect

## ❓ Câu hỏi còn lại
- Dependency array hoạt động ra sao?
- Khi nào gây infinite re-render?

---

# 12. Debounce vs Throttle

## 📝 Tóm tắt
Debounce delay execution cho đến khi user ngừng action. Throttle giới hạn số lần function được gọi trong khoảng thời gian.

## 💻 Ví dụ thực tế

```js
const debouncedSearch = debounce(searchAPI, 500);
```

```js
const throttledScroll = throttle(handleScroll, 200);
```

## 🔗 Link tham khảo
- https://lodash.com/docs/#debounce

## ❓ Câu hỏi còn lại
- Search input nên dùng debounce hay throttle?
- Scroll event tối ưu thế nào?

---

# 13. Virtual DOM là gì?

## 📝 Tóm tắt
Virtual DOM là object representation của DOM thật giúp React tối ưu update UI bằng cách diffing trước khi render thật.

## 💻 Ví dụ thực tế

```jsx
const element = <h1>Hello</h1>;
```

## 🔗 Link tham khảo
- https://react.dev/learn/render-and-commit

## ❓ Câu hỏi còn lại
- Diffing algorithm hoạt động ra sao?
- Virtual DOM có luôn nhanh hơn DOM thật không?

---

# 14. Key trong React dùng để làm gì?

## 📝 Tóm tắt
`key` giúp React identify item trong list để optimize reconciliation và tránh render sai.

## 💻 Ví dụ thực tế

```jsx
users.map((user) => (
  <UserCard key={user.id} user={user} />
));
```

## 🔗 Link tham khảo
- https://react.dev/learn/rendering-lists

## ❓ Câu hỏi còn lại
- Vì sao không nên dùng index làm key?
- Key ảnh hưởng re-render như thế nào?

---

# 15. Authentication vs Authorization

## 📝 Tóm tắt
Authentication xác thực user là ai. Authorization xác định user được phép làm gì.

## 💻 Ví dụ thực tế

```txt
Login bằng JWT -> Authentication
Role admin được xoá user -> Authorization
```

## 🔗 Link tham khảo
- https://auth0.com/docs

## ❓ Câu hỏi còn lại
- Access token và refresh token khác nhau ra sao?
- JWT có thật sự stateless không?

---

# 16. LocalStorage vs SessionStorage vs Cookie

## 📝 Tóm tắt
Cả 3 đều lưu dữ liệu phía client nhưng khác nhau về lifecycle, security và cách browser xử lý.

## 💻 Ví dụ thực tế

```js
localStorage.setItem("token", accessToken);
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API

## ❓ Câu hỏi còn lại
- Vì sao không nên lưu JWT trong localStorage?
- HttpOnly cookie hoạt động ra sao?

---

# 17. CORS là gì?

## 📝 Tóm tắt
CORS là cơ chế browser kiểm soát request giữa các domain khác nhau để đảm bảo security.

## 💻 Ví dụ thực tế

```txt
Frontend:
http://localhost:3000

Backend:
http://localhost:8080
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS

## ❓ Câu hỏi còn lại
- Preflight request là gì?
- Vì sao Postman gọi được nhưng browser bị CORS?

---

# 18. Lazy Loading là gì?

## 📝 Tóm tắt
Lazy loading giúp giảm initial bundle bằng cách chỉ load component/resource khi cần.

## 💻 Ví dụ thực tế

```js
const Dashboard = lazy(() => import("./Dashboard"));
```

## 🔗 Link tham khảo
- https://react.dev/reference/react/lazy

## ❓ Câu hỏi còn lại
- Dynamic import hoạt động như thế nào?
- Lazy loading ảnh hưởng SEO không?

---

# 19. REST API vs GraphQL

## 📝 Tóm tắt
REST chia theo resource endpoint. GraphQL cho phép client query đúng dữ liệu cần lấy.

## 💻 Ví dụ thực tế

REST:

```txt
GET /users/1
```

GraphQL:

```graphql
query {
  user(id: 1) {
    name
    email
  }
}
```

## 🔗 Link tham khảo
- https://graphql.org/learn/

## ❓ Câu hỏi còn lại
- GraphQL có gây overfetching không?
- Khi nào REST tốt hơn GraphQL?

---

# 20. Memory Leak trong React

## 📝 Tóm tắt
Memory leak xảy ra khi resource không được cleanup đúng cách khiến app tốn memory theo thời gian.

## 💻 Ví dụ thực tế

```js
useEffect(() => {
  const interval = setInterval(() => {
    console.log("running");
  }, 1000);

  return () => clearInterval(interval);
}, []);
```

## 🔗 Link tham khảo
- https://react.dev/reference/react/useEffect

## ❓ Câu hỏi còn lại
- Làm sao detect memory leak?
- WebSocket/MQTT cleanup đúng cách thế nào?

</details>

<details>
<summary><strong>📅 2026-05-26 — Frontend Theory Notes</strong></summary>

---

# 21. `useRef` dùng để làm gì?

## 📝 Tóm tắt
`useRef` dùng để lưu mutable value mà không trigger re-render hoặc để truy cập trực tiếp DOM element.

## 💻 Ví dụ thực tế

```js
const inputRef = useRef(null);

inputRef.current.focus();
```

## 🔗 Link tham khảo
- https://react.dev/reference/react/useRef

## ❓ Câu hỏi còn lại
- Khi nào nên dùng useRef thay vì useState?
- useRef có lưu value giữa các lần render không?

---

# 22. Shallow Compare là gì?

## 📝 Tóm tắt
Shallow compare chỉ compare reference ở level đầu tiên thay vì compare sâu toàn bộ object.

## 💻 Ví dụ thực tế

```js
const a = { name: "A" };
const b = { name: "A" };

console.log(a === b); // false
```

## 🔗 Link tham khảo
- https://react.dev/reference/react/memo

## ❓ Câu hỏi còn lại
- React.memo dùng shallow compare như thế nào?
- Deep compare có performance issue không?

---

# 23. Hydration trong React/Next.js là gì?

## 📝 Tóm tắt
Hydration là quá trình React attach event listeners vào HTML đã render từ server.

## 💻 Ví dụ thực tế

```txt
SSR render HTML trước
↓
Client React hydrate lại page
```

## 🔗 Link tham khảo
- https://nextjs.org/docs/messages/react-hydration-error

## ❓ Câu hỏi còn lại
- Vì sao hydration mismatch xảy ra?
- Hydration ảnh hưởng performance thế nào?

---

# 24. Bundle Size là gì?

## 📝 Tóm tắt
Bundle size là kích thước file JavaScript/CSS được gửi xuống browser. Bundle quá lớn sẽ làm app load chậm.

## 💻 Ví dụ thực tế

```txt
main.js = 3MB
→ initial loading chậm
```

## 🔗 Link tham khảo
- https://web.dev/reduce-javascript-payloads-with-code-splitting/

## ❓ Câu hỏi còn lại
- Tree shaking hoạt động thế nào?
- Làm sao analyze bundle hiệu quả?

---

# 25. Tree Shaking là gì?

## 📝 Tóm tắt
Tree shaking giúp loại bỏ code không sử dụng khỏi final bundle để giảm kích thước app.

## 💻 Ví dụ thực tế

```js
import { debounce } from "lodash";
```

## 🔗 Link tham khảo
- https://webpack.js.org/guides/tree-shaking/

## ❓ Câu hỏi còn lại
- Vì sao CommonJS khó tree shaking hơn ESM?
- Side effects ảnh hưởng tree shaking thế nào?

---

# 26. WebSocket hoạt động như thế nào?

## 📝 Tóm tắt
WebSocket tạo persistent connection giữa client và server để trao đổi dữ liệu realtime 2 chiều.

## 💻 Ví dụ thực tế

```js
const ws = new WebSocket("ws://localhost:8080");
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API

## ❓ Câu hỏi còn lại
- WebSocket reconnect strategy nên làm thế nào?
- WebSocket khác SSE ra sao?

---

# 27. Optimistic Update là gì?

## 📝 Tóm tắt
Optimistic update update UI trước khi API thành công để tạo cảm giác app phản hồi nhanh hơn.

## 💻 Ví dụ thực tế

```txt
User click like
→ UI tăng like ngay
→ gọi API phía sau
```

## 🔗 Link tham khảo
- https://tanstack.com/query/latest

## ❓ Câu hỏi còn lại
- Nếu API fail thì rollback thế nào?
- Khi nào không nên dùng optimistic update?

---

# 28. Pagination vs Infinite Scroll

## 📝 Tóm tắt
Pagination chia dữ liệu thành page cố định. Infinite scroll load thêm dữ liệu khi user scroll xuống cuối.

## 💻 Ví dụ thực tế

```txt
Pagination:
Page 1 → 2 → 3

Infinite scroll:
Facebook / TikTok feed
```

## 🔗 Link tham khảo
- https://web.dev/infinite-scroll/

## ❓ Câu hỏi còn lại
- Infinite scroll ảnh hưởng SEO không?
- Khi nào pagination tốt hơn?

---

# 29. Accessibility (a11y) là gì?

## 📝 Tóm tắt
Accessibility giúp ứng dụng dễ sử dụng với mọi người, bao gồm người dùng screen reader hoặc keyboard navigation.

## 💻 Ví dụ thực tế

```html
<button aria-label="Close modal">X</button>
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/Accessibility

## ❓ Câu hỏi còn lại
- Semantic HTML ảnh hưởng accessibility thế nào?
- Làm sao test accessibility?

---

# 30. React Context có phải thay thế Redux không?

## 📝 Tóm tắt
React Context phù hợp share state đơn giản. Redux phù hợp state lớn, phức tạp hoặc cần debugging/middleware mạnh.

## 💻 Ví dụ thực tế

```js
<AuthContext.Provider value={user}>
  <App />
</AuthContext.Provider>
```

## 🔗 Link tham khảo
- https://react.dev/reference/react/useContext

## ❓ Câu hỏi còn lại
- Context gây re-render như thế nào?
- Khi nào Context trở thành anti-pattern?

</details>

<details>
<summary><strong>📅 2026-05-27 — Frontend Theory Notes</strong></summary>

---

# 31. Server Component vs Client Component

## 📝 Tóm tắt
Server Component render phía server để giảm bundle client. Client Component chạy trên browser và hỗ trợ state, event, hook.

## 💻 Ví dụ thực tế

```tsx
"use client";

import { useState } from "react";
```

## 🔗 Link tham khảo
- https://nextjs.org/docs/app/building-your-application/rendering/server-components

## ❓ Câu hỏi còn lại
- Khi nào nên dùng Server Component?
- Server Component có gọi useEffect được không?

---

# 32. Suspense trong React là gì?

## 📝 Tóm tắt
Suspense giúp hiển thị fallback UI trong lúc component hoặc data đang loading.

## 💻 Ví dụ thực tế

```tsx
<Suspense fallback={<Loading />}>
  <Dashboard />
</Suspense>
```

## 🔗 Link tham khảo
- https://react.dev/reference/react/Suspense

## ❓ Câu hỏi còn lại
- Suspense khác loading state bình thường thế nào?
- Suspense hỗ trợ data fetching ra sao?

---

# 33. Race Condition trong Frontend là gì?

## 📝 Tóm tắt
Race condition xảy ra khi nhiều async task hoàn thành không đúng thứ tự mong muốn dẫn tới dữ liệu sai.

## 💻 Ví dụ thực tế

```txt
Search "a"
↓
Search "ab"
↓
API "a" response về sau cùng
→ UI hiển thị sai data
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Event_loop

## ❓ Câu hỏi còn lại
- Làm sao cancel request cũ?
- React Query xử lý race condition thế nào?

---

# 34. Skeleton Loading là gì?

## 📝 Tóm tắt
Skeleton loading hiển thị placeholder layout thay vì spinner để tạo cảm giác app load nhanh hơn.

## 💻 Ví dụ thực tế

```tsx
<Skeleton active paragraph={{ rows: 4 }} />
```

## 🔗 Link tham khảo
- https://ant.design/components/skeleton

## ❓ Câu hỏi còn lại
- Skeleton có tốt hơn spinner không?
- Khi nào không nên dùng skeleton?

---

# 35. CDN là gì?

## 📝 Tóm tắt
CDN (Content Delivery Network) giúp phân phối static assets từ server gần user nhất để giảm latency.

## 💻 Ví dụ thực tế

```txt
Image CDN:
cdn.example.com/banner.png
```

## 🔗 Link tham khảo
- https://www.cloudflare.com/learning/cdn/what-is-a-cdn/

## ❓ Câu hỏi còn lại
- CDN cache invalidation hoạt động thế nào?
- CDN ảnh hưởng SEO ra sao?

---

# 36. HTTP Cache là gì?

## 📝 Tóm tắt
HTTP cache giúp browser lưu lại resource để giảm request và tăng tốc load page.

## 💻 Ví dụ thực tế

```http
Cache-Control: max-age=3600
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/HTTP/Caching

## ❓ Câu hỏi còn lại
- ETag hoạt động thế nào?
- Hard reload bỏ qua cache ra sao?

---

# 37. Monorepo là gì?

## 📝 Tóm tắt
Monorepo là mô hình chứa nhiều package/project trong cùng một repository.

## 💻 Ví dụ thực tế

```txt
apps/
packages/
shared-ui/
```

## 🔗 Link tham khảo
- https://turbo.build/repo/docs

## ❓ Câu hỏi còn lại
- Monorepo có nhược điểm gì?
- Turborepo optimize build thế nào?

---

# 38. Design System là gì?

## 📝 Tóm tắt
Design System là tập hợp UI component, guideline và design rule để maintain consistency giữa các project.

## 💻 Ví dụ thực tế

```txt
Button
Input
Modal
Typography
Spacing
```

## 🔗 Link tham khảo
- https://www.designsystems.com/

## ❓ Câu hỏi còn lại
- Design System khác UI library thế nào?
- Khi nào nên build internal design system?

---

# 39. CI/CD là gì?

## 📝 Tóm tắt
CI/CD giúp automate testing, build và deploy application để giảm manual work và tăng stability.

## 💻 Ví dụ thực tế

```txt
Push code
→ Run test
→ Build app
→ Deploy Vercel
```

## 🔗 Link tham khảo
- https://github.com/features/actions

## ❓ Câu hỏi còn lại
- Khi nào nên deploy preview environment?
- CI pipeline tối ưu thế nào?

---

# 40. Feature Flag là gì?

## 📝 Tóm tắt
Feature flag cho phép bật/tắt feature mà không cần deploy lại application.

## 💻 Ví dụ thực tế

```js
if (featureFlags.newDashboard) {
  return <NewDashboard />;
}
```

## 🔗 Link tham khảo
- https://launchdarkly.com/docs

## ❓ Câu hỏi còn lại
- Feature flag cleanup thế nào?
- Khi nào feature flag trở thành technical debt?


</details>

<details>
<summary><strong>📅 2026-05-28 — Frontend Theory Notes</strong></summary>

---

# 41. React Fiber là gì?

## 📝 Tóm tắt
React Fiber là kiến trúc rendering mới của React giúp chia nhỏ rendering work để app responsive hơn.

## 💻 Ví dụ thực tế

```txt
Render task lớn
↓
Fiber chia nhỏ task
↓
Browser không bị block
```

## 🔗 Link tham khảo
- https://react.dev/learn/render-and-commit

## ❓ Câu hỏi còn lại
- Concurrent rendering hoạt động ra sao?
- Fiber scheduler ưu tiên update thế nào?

---

# 42. Reconciliation trong React là gì?

## 📝 Tóm tắt
Reconciliation là quá trình React compare Virtual DOM cũ và mới để quyết định update DOM thật.

## 💻 Ví dụ thực tế

```jsx
<ul>
  {users.map(user => (
    <li key={user.id}>{user.name}</li>
  ))}
</ul>
```

## 🔗 Link tham khảo
- https://react.dev/learn/rendering-lists

## ❓ Câu hỏi còn lại
- Vì sao key rất quan trọng?
- React diffing algorithm tối ưu thế nào?

---

# 43. SSR Streaming là gì?

## 📝 Tóm tắt
SSR Streaming cho phép server gửi HTML từng phần thay vì đợi render toàn bộ page.

## 💻 Ví dụ thực tế

```txt
Header render trước
↓
Body render sau
↓
User thấy content sớm hơn
```

## 🔗 Link tham khảo
- https://nextjs.org/docs/app/building-your-application/routing/loading-ui-and-streaming

## ❓ Câu hỏi còn lại
- Streaming ảnh hưởng SEO thế nào?
- Suspense liên quan SSR Streaming ra sao?

---

# 44. Edge Runtime là gì?

## 📝 Tóm tắt
Edge Runtime chạy logic gần user hơn để giảm latency thay vì chạy ở central server.

## 💻 Ví dụ thực tế

```txt
User VN
↓
Request xử lý tại Singapore edge
↓
Response nhanh hơn
```

## 🔗 Link tham khảo
- https://vercel.com/docs/functions/edge-functions

## ❓ Câu hỏi còn lại
- Edge runtime có limitation gì?
- Khi nào nên dùng Edge Function?

---

# 45. Zustand khác Redux thế nào?

## 📝 Tóm tắt
Zustand lightweight hơn Redux và ít boilerplate hơn, phù hợp state đơn giản hoặc medium-scale app.

## 💻 Ví dụ thực tế

```js
const useStore = create((set) => ({
  count: 0,
  increment: () => set((state) => ({
    count: state.count + 1
  }))
}));
```

## 🔗 Link tham khảo
- https://zustand-demo.pmnd.rs/

## ❓ Câu hỏi còn lại
- Zustand có middleware mạnh như Redux không?
- Khi nào Redux phù hợp hơn Zustand?

---

# 46. React Query/TanStack Query dùng để làm gì?

## 📝 Tóm tắt
TanStack Query giúp quản lý server state như fetching, caching, retry và synchronization.

## 💻 Ví dụ thực tế

```js
const { data, isLoading } = useQuery({
  queryKey: ["users"],
  queryFn: fetchUsers
});
```

## 🔗 Link tham khảo
- https://tanstack.com/query/latest

## ❓ Câu hỏi còn lại
- Cache invalidation hoạt động thế nào?
- Khi nào vẫn cần Redux dù đã có React Query?

---

# 47. Code Splitting là gì?

## 📝 Tóm tắt
Code splitting chia bundle lớn thành nhiều chunk nhỏ để load khi cần.

## 💻 Ví dụ thực tế

```js
const SettingsPage = lazy(() => import("./SettingsPage"));
```

## 🔗 Link tham khảo
- https://web.dev/reduce-javascript-payloads-with-code-splitting/

## ❓ Câu hỏi còn lại
- Route-based splitting khác component splitting thế nào?
- Too many chunks có gây issue không?

---

# 48. SEO trong Frontend là gì?

## 📝 Tóm tắt
SEO giúp website dễ được search engine crawl và rank tốt hơn trên kết quả tìm kiếm.

## 💻 Ví dụ thực tế

```html
<title>Frontend Learning Journal</title>

<meta
  name="description"
  content="React and Frontend notes"
/>
```

## 🔗 Link tham khảo
- https://developers.google.com/search/docs/fundamentals/seo-starter-guide

## ❓ Câu hỏi còn lại
- CSR ảnh hưởng SEO ra sao?
- Core Web Vitals quan trọng thế nào?

---

# 49. Core Web Vitals là gì?

## 📝 Tóm tắt
Core Web Vitals là bộ metrics đo trải nghiệm người dùng thực tế trên web.

## 💻 Ví dụ thực tế

```txt
LCP → tốc độ load chính
FID → tốc độ phản hồi
CLS → độ ổn định layout
```

## 🔗 Link tham khảo
- https://web.dev/vitals/

## ❓ Câu hỏi còn lại
- Làm sao optimize CLS?
- Lighthouse đo metrics thế nào?

---

# 50. Micro Frontend là gì?

## 📝 Tóm tắt
Micro Frontend chia frontend lớn thành nhiều app nhỏ độc lập để team phát triển riêng biệt.

## 💻 Ví dụ thực tế

```txt
Auth app
Dashboard app
Admin app
```

## 🔗 Link tham khảo
- https://micro-frontends.org/

## ❓ Câu hỏi còn lại
- Shared state giữa micro frontend xử lý ra sao?
- Khi nào micro frontend trở thành over-engineering?

</details>
