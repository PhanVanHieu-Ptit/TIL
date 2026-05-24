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
