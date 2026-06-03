# TIL
Today I Learned

# 📚 Frontend Learning Journal

<details>
<summary><strong>📅 2026-06-03 — React State Management & Reactivity</strong></summary>

---

# 101. React Context Re-render Problem là gì?

## 📝 Tóm tắt
Khi value của Context thay đổi, tất cả component đang subscribe Context đều có thể re-render.

## 💻 Ví dụ thực tế

```tsx
<AuthContext.Provider value={user}>
  <App />
</AuthContext.Provider>
```

## 🔗 Link tham khảo
- https://react.dev/reference/react/useContext

## ❓ Câu hỏi còn lại
- Context Selector giải quyết vấn đề này thế nào?
- Khi nào nên dùng Redux/Zustand thay Context?

---

# 102. Context Selector là gì?

## 📝 Tóm tắt
Context Selector cho phép component chỉ subscribe phần dữ liệu cần thiết thay vì toàn bộ context.

## 💻 Ví dụ thực tế

```txt
UserProfile
↓
Chỉ subscribe user.name
```

## 🔗 Link tham khảo
- https://github.com/dai-shi/use-context-selector

## ❓ Câu hỏi còn lại
- Context Selector hoạt động nội bộ ra sao?
- Performance cải thiện bao nhiêu?

---

# 103. React Compiler là gì?

## 📝 Tóm tắt
React Compiler tự động tối ưu memoization để giảm việc sử dụng thủ công `useMemo` và `useCallback`.

## 💻 Ví dụ thực tế

```txt
React Compiler
↓
Tự động optimize render
```

## 🔗 Link tham khảo
- https://react.dev/learn/react-compiler

## ❓ Câu hỏi còn lại
- React Compiler thay thế React.memo được không?
- Khi nào vẫn cần useMemo?

---

# 104. Fine-Grained Reactivity là gì?

## 📝 Tóm tắt
Fine-grained reactivity chỉ update đúng phần dữ liệu thay đổi thay vì re-render cả component tree.

## 💻 Ví dụ thực tế

```txt
Signal thay đổi
↓
Chỉ update node liên quan
```

## 🔗 Link tham khảo
- https://docs.solidjs.com/

## ❓ Câu hỏi còn lại
- Signal khác State của React thế nào?
- React tương lai có hỗ trợ signal không?

---

# 105. Signals là gì?

## 📝 Tóm tắt
Signal là primitive reactive giúp tracking dependency tự động và update UI hiệu quả.

## 💻 Ví dụ thực tế

```js
const count = signal(0);
```

## 🔗 Link tham khảo
- https://preactjs.com/guide/v10/signals/

## ❓ Câu hỏi còn lại
- Signal khác useState thế nào?
- Signal có thay thế Redux được không?

---

# 106. Server-Side Cache là gì?

## 📝 Tóm tắt
Server-side cache lưu dữ liệu ở phía server để giảm số lần truy vấn database hoặc gọi API.

## 💻 Ví dụ thực tế

```txt
Request
↓
Redis Cache
↓
Database
```

## 🔗 Link tham khảo
- https://redis.io/docs/

## ❓ Câu hỏi còn lại
- Cache invalidation xử lý thế nào?
- Khi nào cache gây stale data?

---

# 107. CDN Cache là gì?

## 📝 Tóm tắt
CDN cache lưu static assets tại edge location gần user để giảm latency.

## 💻 Ví dụ thực tế

```txt
User VN
↓
Cloudflare Singapore
↓
Image
```

## 🔗 Link tham khảo
- https://www.cloudflare.com/learning/cdn/what-is-caching/

## ❓ Câu hỏi còn lại
- Cache purge hoạt động ra sao?
- CDN cache khác browser cache thế nào?

---

# 108. Stale-While-Revalidate là gì?

## 📝 Tóm tắt
Stale-While-Revalidate trả về cache cũ ngay lập tức và fetch dữ liệu mới ở background.

## 💻 Ví dụ thực tế

```txt
Return cache
↓
Fetch background
↓
Update cache
```

## 🔗 Link tham khảo
- https://web.dev/stale-while-revalidate/

## ❓ Câu hỏi còn lại
- React Query áp dụng SWR thế nào?
- Khi nào không nên dùng SWR?

---

# 109. Resource Hint là gì?

## 📝 Tóm tắt
Resource Hint giúp browser biết trước resource nào cần tải để tối ưu tốc độ load.

## 💻 Ví dụ thực tế

```html
<link rel="dns-prefetch" href="//example.com">

<link rel="preconnect" href="https://api.example.com">
```

## 🔗 Link tham khảo
- https://web.dev/learn/performance/resource-hints

## ❓ Câu hỏi còn lại
- Preconnect khác prefetch thế nào?
- Khi nào resource hint gây phản tác dụng?

---

# 110. Critical Rendering Path là gì?

## 📝 Tóm tắt
Critical Rendering Path là chuỗi bước browser thực hiện để hiển thị nội dung đầu tiên lên màn hình.

## 💻 Ví dụ thực tế

```txt
HTML
↓
DOM
↓
CSSOM
↓
Render Tree
↓
Paint
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/Performance/Critical_rendering_path

## ❓ Câu hỏi còn lại
- CSS ảnh hưởng Critical Rendering Path thế nào?
- Làm sao rút ngắn First Paint?

</details>

<details>
<summary><strong>📅 2026-06-02 — React Internals, Rendering Pipeline & Build System</strong></summary>

---

# 91. React Scheduler là gì?

## 📝 Tóm tắt
React Scheduler giúp React ưu tiên các task quan trọng để UI responsive hơn.

## 💻 Ví dụ thực tế

```txt
Typing input
↓
Ưu tiên render input trước
↓
Render list nặng sau
```

## 🔗 Link tham khảo
- https://react.dev/blog/2022/03/29/react-v18

## ❓ Câu hỏi còn lại
- Scheduler khác Event Loop thế nào?
- React priority level hoạt động ra sao?

---

# 92. Tearing trong React là gì?

## 📝 Tóm tắt
Tearing xảy ra khi UI hiển thị dữ liệu không đồng bộ giữa các component trong concurrent rendering.

## 💻 Ví dụ thực tế

```txt
Component A:
count = 1

Component B:
count = 2
```

## 🔗 Link tham khảo
- https://react.dev/reference/react/useSyncExternalStore

## ❓ Câu hỏi còn lại
- useSyncExternalStore giúp tránh tearing thế nào?
- Zustand/Redux xử lý tearing ra sao?

---

# 93. `useSyncExternalStore` là gì?

## 📝 Tóm tắt
`useSyncExternalStore` giúp React subscribe external store an toàn trong concurrent rendering.

## 💻 Ví dụ thực tế

```js
const state = useSyncExternalStore(
  subscribe,
  getSnapshot
);
```

## 🔗 Link tham khảo
- https://react.dev/reference/react/useSyncExternalStore

## ❓ Câu hỏi còn lại
- Khi nào cần useSyncExternalStore?
- Hook này khác useEffect subscription thế nào?

---

# 94. Render Blocking Resource là gì?

## 📝 Tóm tắt
Render blocking resource là resource khiến browser chưa thể render page ngay.

## 💻 Ví dụ thực tế

```html
<link rel="stylesheet" href="style.css" />
```

## 🔗 Link tham khảo
- https://web.dev/render-blocking-resources/

## ❓ Câu hỏi còn lại
- CSS vì sao render blocking?
- Async/defer ảnh hưởng script loading ra sao?

---

# 95. Async vs Defer trong Script

## 📝 Tóm tắt
`async` load và execute script ngay khi tải xong. `defer` đợi parse HTML xong mới execute.

## 💻 Ví dụ thực tế

```html
<script async src="analytics.js"></script>

<script defer src="main.js"></script>
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script

## ❓ Câu hỏi còn lại
- Khi nào async gây lỗi dependency?
- Vì sao main bundle thường dùng defer?

---

# 96. Source Map là gì?

## 📝 Tóm tắt
Source map giúp mapping code production/minified về source code gốc để debug dễ hơn.

## 💻 Ví dụ thực tế

```txt
main.min.js
↓
Map về App.tsx
```

## 🔗 Link tham khảo
- https://developer.chrome.com/docs/devtools/javascript/source-maps/

## ❓ Câu hỏi còn lại
- Có nên disable source map production không?
- Source map ảnh hưởng security thế nào?

---

# 97. Dead Code là gì?

## 📝 Tóm tắt
Dead code là code không bao giờ được execute nhưng vẫn tồn tại trong bundle.

## 💻 Ví dụ thực tế

```js
if (false) {
  console.log("dead code");
}
```

## 🔗 Link tham khảo
- https://webpack.js.org/guides/tree-shaking/

## ❓ Câu hỏi còn lại
- Tree shaking remove dead code thế nào?
- Dynamic import ảnh hưởng dead code ra sao?

---

# 98. Hot Reload vs Live Reload

## 📝 Tóm tắt
Hot reload update module mà không reload toàn page. Live reload reload toàn browser page.

## 💻 Ví dụ thực tế

```txt
Change CSS
↓
UI update ngay
↓
State vẫn giữ nguyên
```

## 🔗 Link tham khảo
- https://vitejs.dev/guide/features.html#hot-module-replacement

## ❓ Câu hỏi còn lại
- HMR hoạt động bên trong ra sao?
- Khi nào hot reload fail?

---

# 99. ESM là gì?

## 📝 Tóm tắt
ESM (ECMAScript Module) là chuẩn module hiện đại của JavaScript hỗ trợ import/export.

## 💻 Ví dụ thực tế

```js
export const sum = (a, b) => a + b;

import { sum } from "./math";
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

## ❓ Câu hỏi còn lại
- ESM khác CommonJS thế nào?
- Vì sao ESM tree shaking tốt hơn?

---

# 100. Dependency Injection là gì?

## 📝 Tóm tắt
Dependency Injection giúp inject dependency từ bên ngoài thay vì tạo trực tiếp bên trong component/module.

## 💻 Ví dụ thực tế

```js
function UserService(apiClient) {
  return {
    getUsers: () => apiClient.get("/users")
  };
}
```

## 🔗 Link tham khảo
- https://martinfowler.com/articles/injection.html

## ❓ Câu hỏi còn lại
- React Context có phải dependency injection không?
- Khi nào DI làm code phức tạp hơn?

</details>

<details>
<summary><strong>📅 2026-06-01 — Advanced React & Web Performance Concepts</strong></summary>

---

# 81. React Portal là gì?

## 📝 Tóm tắt
React Portal cho phép render component ra ngoài DOM hierarchy hiện tại.

## 💻 Ví dụ thực tế

```tsx
createPortal(
  <Modal />,
  document.body
);
```

## 🔗 Link tham khảo
- https://react.dev/reference/react-dom/createPortal

## ❓ Câu hỏi còn lại
- Vì sao modal thường dùng portal?
- Event bubbling hoạt động thế nào với portal?

---

# 82. Error Boundary là gì?

## 📝 Tóm tắt
Error Boundary giúp catch JavaScript error trong component tree và hiển thị fallback UI.

## 💻 Ví dụ thực tế

```tsx
<ErrorBoundary fallback={<ErrorPage />}>
  <Dashboard />
</ErrorBoundary>
```

## 🔗 Link tham khảo
- https://react.dev/reference/react/Component#catching-rendering-errors-with-an-error-boundary

## ❓ Câu hỏi còn lại
- Error Boundary catch async error được không?
- Khi nào nên chia nhỏ error boundary?

---

# 83. React Lazy Hydration là gì?

## 📝 Tóm tắt
Lazy hydration trì hoãn hydrate component đến khi cần để giảm initial JS execution.

## 💻 Ví dụ thực tế

```txt
Footer hydrate khi scroll tới
```

## 🔗 Link tham khảo
- https://web.dev/progressive-hydration/

## ❓ Câu hỏi còn lại
- Lazy hydration khác code splitting thế nào?
- Khi nào hydrate quá muộn gây UX xấu?

---

# 84. Island Architecture là gì?

## 📝 Tóm tắt
Island architecture chỉ hydrate interactive component thay vì hydrate toàn page.

## 💻 Ví dụ thực tế

```txt
Static page
↓
Chỉ search bar interactive
```

## 🔗 Link tham khảo
- https://docs.astro.build/en/concepts/islands/

## ❓ Câu hỏi còn lại
- Island architecture khác SSR truyền thống thế nào?
- Khi nào island phù hợp hơn SPA?

---

# 85. React Server Actions là gì?

## 📝 Tóm tắt
Server Actions cho phép gọi server-side function trực tiếp từ React component.

## 💻 Ví dụ thực tế

```tsx
async function createPost(formData) {
  "use server";
}
```

## 🔗 Link tham khảo
- https://nextjs.org/docs/app/building-your-application/data-fetching/server-actions-and-mutations

## ❓ Câu hỏi còn lại
- Server Actions khác API route thế nào?
- Khi nào Server Actions không phù hợp?

---

# 86. Long Task là gì?

## 📝 Tóm tắt
Long task là JavaScript task chạy quá lâu khiến browser bị block và UI lag.

## 💻 Ví dụ thực tế

```txt
Heavy loop chạy 300ms
↓
UI freeze
```

## 🔗 Link tham khảo
- https://web.dev/long-tasks-devtools/

## ❓ Câu hỏi còn lại
- Web Worker giúp xử lý long task thế nào?
- React concurrent rendering giảm long task ra sao?

---

# 87. Web Worker là gì?

## 📝 Tóm tắt
Web Worker cho phép chạy JavaScript background thread mà không block main UI thread.

## 💻 Ví dụ thực tế

```js
const worker = new Worker("worker.js");
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API

## ❓ Câu hỏi còn lại
- Web Worker communicate với main thread thế nào?
- Khi nào không nên dùng worker?

---

# 88. Main Thread Blocking là gì?

## 📝 Tóm tắt
Main thread blocking xảy ra khi JavaScript execution làm browser không render hoặc không phản hồi user interaction.

## 💻 Ví dụ thực tế

```txt
Heavy JSON parse
↓
Button click bị lag
```

## 🔗 Link tham khảo
- https://web.dev/off-main-thread/

## ❓ Câu hỏi còn lại
- Làm sao detect main thread blocking?
- Bundle lớn ảnh hưởng main thread ra sao?

---

# 89. HTTP/2 khác HTTP/1.1 thế nào?

## 📝 Tóm tắt
HTTP/2 hỗ trợ multiplexing giúp gửi nhiều request trên cùng một connection nhanh hơn HTTP/1.1.

## 💻 Ví dụ thực tế

```txt
HTTP/1.1:
Nhiều TCP connection

HTTP/2:
Một connection nhiều stream
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Glossary/HTTP_2

## ❓ Câu hỏi còn lại
- HTTP/3 khác HTTP/2 thế nào?
- Multiplexing giúp giảm waterfall ra sao?

---

# 90. Prefetch vs Preload là gì?

## 📝 Tóm tắt
Preload ưu tiên load resource hiện tại. Prefetch load trước resource có thể dùng ở tương lai.

## 💻 Ví dụ thực tế

```html
<link rel="preload" href="main.js" />

<link rel="prefetch" href="next-page.js" />
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/rel/preload

## ❓ Câu hỏi còn lại
- Preload quá nhiều có gây chậm page không?
- Next.js tự động prefetch hoạt động thế nào?

</details>

<details>
<summary><strong>📅 2026-05-31 — React Advanced Rendering, Concurrency & Web Performance</strong></summary>

---

# 71. React Strict Mode là gì?

## 📝 Tóm tắt
React Strict Mode giúp detect potential issue trong development như side effect không an toàn hoặc deprecated API.

## 💻 Ví dụ thực tế

```tsx
<React.StrictMode>
  <App />
</React.StrictMode>
```

## 🔗 Link tham khảo
- https://react.dev/reference/react/StrictMode

## ❓ Câu hỏi còn lại
- Vì sao useEffect chạy 2 lần trong Strict Mode?
- Strict Mode có ảnh hưởng production không?

---

# 72. Stale Closure là gì?

## 📝 Tóm tắt
Stale closure xảy ra khi function giữ giá trị state/props cũ do closure capture dữ liệu trước đó.

## 💻 Ví dụ thực tế

```js
useEffect(() => {
  setInterval(() => {
    console.log(count);
  }, 1000);
}, []);
```

## 🔗 Link tham khảo
- https://react.dev/reference/react/useEffect

## ❓ Câu hỏi còn lại
- Dependency array ảnh hưởng stale closure ra sao?
- useRef giúp xử lý stale closure thế nào?

---

# 73. Concurrent Rendering là gì?

## 📝 Tóm tắt
Concurrent Rendering giúp React interrupt hoặc prioritize rendering để UI responsive hơn.

## 💻 Ví dụ thực tế

```js
startTransition(() => {
  setSearch(keyword);
});
```

## 🔗 Link tham khảo
- https://react.dev/reference/react/useTransition

## ❓ Câu hỏi còn lại
- Concurrent rendering khác sync rendering thế nào?
- Khi nào nên dùng transition?

---

# 74. `useTransition` dùng để làm gì?

## 📝 Tóm tắt
`useTransition` giúp đánh dấu update không urgent để tránh block UI.

## 💻 Ví dụ thực tế

```js
const [isPending, startTransition] = useTransition();
```

## 🔗 Link tham khảo
- https://react.dev/reference/react/useTransition

## ❓ Câu hỏi còn lại
- useTransition khác debounce thế nào?
- Khi nào transition không hiệu quả?

---

# 75. `useDeferredValue` là gì?

## 📝 Tóm tắt
`useDeferredValue` giúp defer update của value để giảm lag UI khi rendering nặng.

## 💻 Ví dụ thực tế

```js
const deferredSearch = useDeferredValue(search);
```

## 🔗 Link tham khảo
- https://react.dev/reference/react/useDeferredValue

## ❓ Câu hỏi còn lại
- useDeferredValue khác useMemo thế nào?
- Khi nào deferred value hữu ích?

---

# 76. Batch Update trong React là gì?

## 📝 Tóm tắt
Batch update giúp React gom nhiều state update thành một lần render để optimize performance.

## 💻 Ví dụ thực tế

```js
setCount(c => c + 1);
setLoading(true);
```

## 🔗 Link tham khảo
- https://react.dev/learn/queueing-a-series-of-state-updates

## ❓ Câu hỏi còn lại
- React batch update trong async event thế nào?
- flushSync dùng để làm gì?

---

# 77. `flushSync` là gì?

## 📝 Tóm tắt
`flushSync` buộc React update DOM ngay lập tức thay vì chờ batching.

## 💻 Ví dụ thực tế

```js
flushSync(() => {
  setOpen(true);
});
```

## 🔗 Link tham khảo
- https://react.dev/reference/react-dom/flushSync

## ❓ Câu hỏi còn lại
- Khi nào cần flushSync?
- flushSync có gây performance issue không?

---

# 78. Layout Shift là gì?

## 📝 Tóm tắt
Layout shift xảy ra khi UI bị nhảy layout trong lúc load page gây trải nghiệm xấu.

## 💻 Ví dụ thực tế

```txt
Image chưa có width/height
↓
Content bị đẩy xuống
```

## 🔗 Link tham khảo
- https://web.dev/cls/

## ❓ Câu hỏi còn lại
- CLS được tính thế nào?
- Skeleton loading giúp giảm CLS ra sao?

---

# 79. Time To Interactive (TTI) là gì?

## 📝 Tóm tắt
TTI là thời điểm page có thể tương tác ổn định với user.

## 💻 Ví dụ thực tế

```txt
Page render xong
↓
Button click được
↓
Không bị lag
```

## 🔗 Link tham khảo
- https://web.dev/interactive/

## ❓ Câu hỏi còn lại
- Bundle size ảnh hưởng TTI ra sao?
- Lighthouse đo TTI thế nào?

---

# 80. Request Waterfall là gì?

## 📝 Tóm tắt
Request waterfall xảy ra khi request phụ thuộc nhau khiến loading chậm hơn.

## 💻 Ví dụ thực tế

```txt
Fetch user
↓
Fetch posts
↓
Fetch comments
```

## 🔗 Link tham khảo
- https://developer.chrome.com/docs/devtools/network/

## ❓ Câu hỏi còn lại
- Parallel fetching tối ưu waterfall thế nào?
- React Query hỗ trợ tránh waterfall ra sao?

</details>

<details>
<summary><strong>📅 2026-05-30 — Frontend Performance, Realtime Data & Architecture Patterns</strong></summary>

# 61. Hydration Mismatch là gì?

## 📝 Tóm tắt
Hydration mismatch xảy ra khi HTML render từ server khác với HTML render phía client.

## 💻 Ví dụ thực tế

```tsx
const date = new Date().toLocaleTimeString();
```

Server và client render khác thời gian → mismatch.

## 🔗 Link tham khảo
- https://nextjs.org/docs/messages/react-hydration-error

## ❓ Câu hỏi còn lại
- Làm sao debug hydration mismatch?
- `useEffect` giúp tránh mismatch thế nào?

---

# 62. Memoization là gì?

## 📝 Tóm tắt
Memoization là kỹ thuật cache kết quả computation để tránh tính toán lại không cần thiết.

## 💻 Ví dụ thực tế

```js
const expensiveValue = useMemo(() => {
  return heavyCalculation(data);
}, [data]);
```

## 🔗 Link tham khảo
- https://react.dev/reference/react/useMemo

## ❓ Câu hỏi còn lại
- Memoization có cost gì?
- Khi nào không nên dùng useMemo?

---

# 63. Runtime vs Build Time

## 📝 Tóm tắt
Build time xảy ra khi app được build trước deploy. Runtime xảy ra khi app đang chạy thực tế trên browser/server.

## 💻 Ví dụ thực tế

```txt
Build time:
Next.js generate static page

Runtime:
Fetch API khi user mở page
```

## 🔗 Link tham khảo
- https://nextjs.org/docs

## ❓ Câu hỏi còn lại
- ISR nằm giữa build time và runtime như thế nào?
- Runtime config xử lý ra sao?

---

# 64. Image Optimization là gì?

## 📝 Tóm tắt
Image optimization giúp giảm dung lượng ảnh và tăng tốc load page.

## 💻 Ví dụ thực tế

```tsx
<Image
  src="/banner.png"
  width={800}
  height={400}
  alt="banner"
/>
```

## 🔗 Link tham khảo
- https://nextjs.org/docs/pages/api-reference/components/image

## ❓ Câu hỏi còn lại
- WebP và AVIF khác nhau thế nào?
- Lazy loading image hoạt động ra sao?

---

# 65. WebSocket Reconnect Strategy là gì?

## 📝 Tóm tắt
Reconnect strategy giúp app tự reconnect khi WebSocket bị disconnect.

## 💻 Ví dụ thực tế

```js
setTimeout(connectWebSocket, 3000);
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API

## ❓ Câu hỏi còn lại
- Exponential backoff là gì?
- Khi nào nên stop reconnect?

---

# 66. Data Normalization là gì?

## 📝 Tóm tắt
Data normalization giúp lưu dữ liệu dạng phẳng để tránh duplicate và dễ update state.

## 💻 Ví dụ thực tế

```js
{
  users: {
    byId: {
      1: { id: 1, name: "Hieu" }
    },
    allIds: [1]
  }
}
```

## 🔗 Link tham khảo
- https://redux.js.org/usage/structuring-reducers/normalizing-state-shape

## ❓ Câu hỏi còn lại
- Khi nào normalized state là overkill?
- RTK entity adapter hoạt động thế nào?

---

# 67. Optimistic UI vs Pessimistic UI

## 📝 Tóm tắt
Optimistic UI update giao diện trước khi API thành công. Pessimistic UI đợi API xong mới update UI.

## 💻 Ví dụ thực tế

```txt
Optimistic:
Like post → tăng like ngay

Pessimistic:
Đợi API success → mới update
```

## 🔗 Link tham khảo
- https://tanstack.com/query/latest

## ❓ Câu hỏi còn lại
- Khi nào optimistic update nguy hiểm?
- Rollback strategy nên làm sao?

---

# 68. Thundering Herd Problem là gì?

## 📝 Tóm tắt
Thundering herd xảy ra khi quá nhiều request cùng retry hoặc fetch cùng lúc gây overload server.

## 💻 Ví dụ thực tế

```txt
1000 client reconnect WebSocket cùng lúc
```

## 🔗 Link tham khảo
- https://en.wikipedia.org/wiki/Thundering_herd_problem

## ❓ Câu hỏi còn lại
- Exponential backoff giảm issue này thế nào?
- Cache giúp hạn chế thundering herd ra sao?

---

# 69. State Machine trong Frontend là gì?

## 📝 Tóm tắt
State machine giúp quản lý state transition rõ ràng và predictable.

## 💻 Ví dụ thực tế

```txt
idle
↓
loading
↓
success / error
```

## 🔗 Link tham khảo
- https://xstate.js.org/docs/

## ❓ Câu hỏi còn lại
- Khi nào state machine hữu ích hơn Redux?
- XState hoạt động thế nào?

---

# 70. Module Federation là gì?

## 📝 Tóm tắt
Module Federation cho phép nhiều app share module runtime mà không cần build chung.

## 💻 Ví dụ thực tế

```txt
Host app
↓
Load remote component
↓
Remote app
```

## 🔗 Link tham khảo
- https://webpack.js.org/concepts/module-federation/

## ❓ Câu hỏi còn lại
- Shared dependency xử lý thế nào?
- Khi nào Module Federation gây complexity lớn?

</details>

<details>
<summary><strong>📅 2026-05-29 — Browser Rendering, PWA, Accessibility, CSS & Events</strong></summary>

---

# 51. Browser Rendering Pipeline là gì?

## 📝 Tóm tắt
Browser rendering pipeline là quá trình browser parse HTML/CSS/JS để hiển thị UI lên màn hình.

## 💻 Ví dụ thực tế

```txt
HTML
↓
DOM
↓
CSSOM
↓
Render Tree
↓
Layout
↓
Paint
↓
Composite
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/Performance/How_browsers_work

## ❓ Câu hỏi còn lại
- Reflow và repaint khác nhau thế nào?
- CSS animation ảnh hưởng rendering ra sao?

---

# 52. Reflow vs Repaint

## 📝 Tóm tắt
Reflow xảy ra khi layout thay đổi. Repaint xảy ra khi chỉ thay đổi giao diện mà không đổi layout.

## 💻 Ví dụ thực tế

```css
width: 100px; /* Reflow */
background: red; /* Repaint */
```

## 🔗 Link tham khảo
- https://web.dev/avoid-large-complex-layouts-and-layout-thrashing/

## ❓ Câu hỏi còn lại
- Layout thrashing là gì?
- Làm sao giảm reflow?

---

# 53. Service Worker là gì?

## 📝 Tóm tắt
Service Worker là script chạy background giúp hỗ trợ offline mode, push notification và caching.

## 💻 Ví dụ thực tế

```js
navigator.serviceWorker.register("/sw.js");
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API

## ❓ Câu hỏi còn lại
- Service Worker cache update thế nào?
- Khi nào không nên dùng PWA?

---

# 54. PWA là gì?

## 📝 Tóm tắt
PWA (Progressive Web App) giúp web app có trải nghiệm giống native app như offline mode hoặc install app.

## 💻 Ví dụ thực tế

```txt
Add to Home Screen
Offline support
Push notification
```

## 🔗 Link tham khảo
- https://web.dev/progressive-web-apps/

## ❓ Câu hỏi còn lại
- PWA limitation trên iOS là gì?
- PWA khác native app ra sao?

---

# 55. Web Accessibility Semantic HTML là gì?

## 📝 Tóm tắt
Semantic HTML giúp browser và screen reader hiểu đúng ý nghĩa nội dung HTML.

## 💻 Ví dụ thực tế

```html
<header>
<nav>
<main>
<footer>
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Glossary/Semantics

## ❓ Câu hỏi còn lại
- Screen reader đọc semantic HTML thế nào?
- Div soup gây issue gì?

---

# 56. Intersection Observer dùng để làm gì?

## 📝 Tóm tắt
Intersection Observer giúp detect khi element xuất hiện trong viewport mà không cần listen scroll event liên tục.

## 💻 Ví dụ thực tế

```js
const observer = new IntersectionObserver(callback);
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API

## ❓ Câu hỏi còn lại
- Infinite scroll dùng Intersection Observer thế nào?
- Observer có performance tốt hơn scroll event không?

---

# 57. Web Vitals Monitoring là gì?

## 📝 Tóm tắt
Web Vitals Monitoring giúp theo dõi performance thực tế của user production.

## 💻 Ví dụ thực tế

```js
import { getCLS, getLCP } from "web-vitals";
```

## 🔗 Link tham khảo
- https://web.dev/vitals/

## ❓ Câu hỏi còn lại
- Synthetic metrics khác real user metrics thế nào?
- CLS thường bị ảnh hưởng bởi gì?

---

# 58. CSS Specificity là gì?

## 📝 Tóm tắt
CSS specificity xác định rule CSS nào được ưu tiên apply.

## 💻 Ví dụ thực tế

```css
#id {
  color: red;
}

.button {
  color: blue;
}
```

`#id` sẽ ưu tiên hơn.

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity

## ❓ Câu hỏi còn lại
- `!important` ảnh hưởng specificity thế nào?
- CSS-in-JS xử lý specificity ra sao?

---

# 59. Event Delegation là gì?

## 📝 Tóm tắt
Event delegation dùng event bubbling để handle event cho nhiều element bằng một listener cha.

## 💻 Ví dụ thực tế

```js
list.addEventListener("click", (e) => {
  if (e.target.matches("li")) {
    console.log("clicked");
  }
});
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events

## ❓ Câu hỏi còn lại
- Event bubbling khác capturing thế nào?
- React synthetic event hoạt động ra sao?

---

# 60. Synthetic Event trong React là gì?

## 📝 Tóm tắt
Synthetic Event là wrapper của React quanh native browser event để đảm bảo behavior consistent giữa các browser.

## 💻 Ví dụ thực tế

```jsx
<button onClick={handleClick}>
  Click
</button>
```

## 🔗 Link tham khảo
- https://react.dev/reference/react-dom/components/common

## ❓ Câu hỏi còn lại
- React event pooling là gì?
- Synthetic event khác native event ra sao?

</details>

<details>
<summary><strong>📅 2026-05-28 — React Architecture, Next.js Rendering & Frontend Scaling</strong></summary>

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

<details>
<summary><strong>📅 2026-05-27 — Next.js Components, Async UX, Caching & Delivery Workflow</strong></summary>

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
<summary><strong>📅 2026-05-26 — React Hooks, Bundle Optimization, Realtime & State Management</strong></summary>

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
<summary><strong>📅 2026-05-25 — React Effects, Browser Storage, Security & API Patterns</strong></summary>

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
<summary><strong>📅 2026-05-24 — JavaScript Core, React Rendering & Frontend Performance Basics</strong></summary>

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
