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
