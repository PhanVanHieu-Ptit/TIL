# TIL
Today I Learned

# 📚 Frontend Learning Journal

<details>
<summary><strong>📅 2026-06-17 — Browser Performance & Rendering Optimization</strong></summary>

---

# 231. Critical Rendering Path là gì?

## 📝 Tóm tắt
Critical Rendering Path là quá trình trình duyệt chuyển đổi HTML, CSS và JavaScript thành giao diện hiển thị trên màn hình.

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
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/Performance/Critical_rendering_path

## ❓ Câu hỏi còn lại
- CSS ảnh hưởng CRP như thế nào?
- Làm sao giảm thời gian render đầu tiên?

---

# 232. Reflow là gì?

## 📝 Tóm tắt
Reflow xảy ra khi trình duyệt phải tính toán lại vị trí và kích thước của các phần tử.

## 💻 Ví dụ thực tế

```js
element.style.width = "300px";
```

## 🔗 Link tham khảo
- https://web.dev/articles/avoid-large-complex-layouts-and-layout-thrashing

## ❓ Câu hỏi còn lại
- Những CSS property nào gây reflow?
- Reflow ảnh hưởng FPS ra sao?

---

# 233. Repaint là gì?

## 📝 Tóm tắt
Repaint xảy ra khi giao diện cần được vẽ lại nhưng không thay đổi layout.

## 💻 Ví dụ thực tế

```css
color: red;
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/Performance

## ❓ Câu hỏi còn lại
- Repaint nhẹ hơn Reflow như thế nào?
- Browser tối ưu repaint ra sao?

---

# 234. Layout Thrashing là gì?

## 📝 Tóm tắt
Layout Thrashing xảy ra khi code liên tục đọc và ghi layout khiến browser phải reflow nhiều lần.

## 💻 Ví dụ thực tế

```js
element.offsetWidth;
element.style.width = "200px";
element.offsetWidth;
```

## 🔗 Link tham khảo
- https://web.dev/articles/avoid-large-complex-layouts-and-layout-thrashing

## ❓ Câu hỏi còn lại
- Làm sao phát hiện Layout Thrashing?
- requestAnimationFrame giúp gì?

---

# 235. Composite Layer là gì?

## 📝 Tóm tắt
Composite Layer là lớp riêng biệt được GPU xử lý để tối ưu animation và rendering.

## 💻 Ví dụ thực tế

```css
transform: translateX(100px);
```

## 🔗 Link tham khảo
- https://developer.chrome.com/docs/devtools/layers

## ❓ Câu hỏi còn lại
- Khi nào browser tạo layer mới?
- Quá nhiều layer có gây vấn đề không?

---

# 236. GPU Acceleration là gì?

## 📝 Tóm tắt
GPU Acceleration tận dụng GPU để xử lý animation và rendering thay vì CPU.

## 💻 Ví dụ thực tế

```css
transform: translate3d(
  0,
  0,
  0
);
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/Performance

## ❓ Câu hỏi còn lại
- Khi nào GPU rendering không hiệu quả?
- GPU Memory được quản lý thế nào?

---

# 237. First Contentful Paint (FCP) là gì?

## 📝 Tóm tắt
FCP đo thời gian từ lúc tải trang đến khi nội dung đầu tiên xuất hiện trên màn hình.

## 💻 Ví dụ thực tế

```txt
Load Page
↓
Logo xuất hiện
```

## 🔗 Link tham khảo
- https://web.dev/fcp/

## ❓ Câu hỏi còn lại
- FCP bao nhiêu là tốt?
- CSS Blocking ảnh hưởng FCP ra sao?

---

# 238. Largest Contentful Paint (LCP) là gì?

## 📝 Tóm tắt
LCP đo thời gian hiển thị phần tử nội dung lớn nhất trong viewport.

## 💻 Ví dụ thực tế

```txt
Hero Banner
Product Image
```

## 🔗 Link tham khảo
- https://web.dev/lcp/

## ❓ Câu hỏi còn lại
- LCP bao nhiêu được đánh giá tốt?
- Image Optimization ảnh hưởng thế nào?

---

# 239. Cumulative Layout Shift (CLS) là gì?

## 📝 Tóm tắt
CLS đo mức độ dịch chuyển bất ngờ của layout trong quá trình tải trang.

## 💻 Ví dụ thực tế

```txt
Button nhảy vị trí
↓
User click nhầm
```

## 🔗 Link tham khảo
- https://web.dev/cls/

## ❓ Câu hỏi còn lại
- Làm sao giảm CLS?
- Quảng cáo ảnh hưởng CLS thế nào?

---

# 240. Interaction to Next Paint (INP) là gì?

## 📝 Tóm tắt
INP đo độ phản hồi tổng thể của giao diện sau các tương tác của người dùng.

## 💻 Ví dụ thực tế

```txt
User Click
↓
UI Update
```

## 🔗 Link tham khảo
- https://web.dev/inp/

## ❓ Câu hỏi còn lại
- INP thay thế metric nào?
- React Concurrent Rendering ảnh hưởng INP ra sao?

</details>

<details>
<summary><strong>📅 2026-06-16 — Advanced State Management & React Architecture</strong></summary>

---

# 221. Flux Architecture là gì?

## 📝 Tóm tắt
Flux là kiến trúc quản lý state theo luồng dữ liệu một chiều giúp ứng dụng dễ dự đoán hơn.

## 💻 Ví dụ thực tế

```txt
Action
↓
Dispatcher
↓
Store
↓
View
```

## 🔗 Link tham khảo
- https://facebook.github.io/flux/

## ❓ Câu hỏi còn lại
- Flux khác Redux ở điểm nào?
- Dispatcher có còn được dùng hiện nay không?

---

# 222. Redux Middleware là gì?

## 📝 Tóm tắt
Middleware cho phép can thiệp vào quá trình dispatch action để xử lý logic bất đồng bộ hoặc logging.

## 💻 Ví dụ thực tế

```ts
store.dispatch(fetchUsers());
```

## 🔗 Link tham khảo
- https://redux.js.org/understanding/history-and-design/middleware

## ❓ Câu hỏi còn lại
- Middleware chạy theo thứ tự nào?
- Middleware khác Reducer ra sao?

---

# 223. Redux Thunk là gì?

## 📝 Tóm tắt
Redux Thunk cho phép dispatch function thay vì chỉ dispatch object.

## 💻 Ví dụ thực tế

```ts
export const fetchUsers =
  () => async (dispatch) => {
    const data = await api.getUsers();
  };
```

## 🔗 Link tham khảo
- https://redux.js.org/usage/writing-logic-thunks

## ❓ Câu hỏi còn lại
- Khi nào nên dùng Thunk?
- Thunk khác Saga thế nào?

---

# 224. Redux Saga là gì?

## 📝 Tóm tắt
Redux Saga sử dụng Generator Function để quản lý side effects phức tạp.

## 💻 Ví dụ thực tế

```ts
yield call(api.fetchUsers);
yield put(success());
```

## 🔗 Link tham khảo
- https://redux-saga.js.org/

## ❓ Câu hỏi còn lại
- Saga phù hợp với dự án nào?
- Saga có khó debug hơn Thunk không?

---

# 225. Zustand là gì?

## 📝 Tóm tắt
Zustand là thư viện quản lý state nhẹ, đơn giản và ít boilerplate hơn Redux.

## 💻 Ví dụ thực tế

```ts
const useStore = create(() => ({
  count: 0,
}));
```

## 🔗 Link tham khảo
- https://zustand-demo.pmnd.rs/

## ❓ Câu hỏi còn lại
- Zustand xử lý persistence thế nào?
- Khi nào Zustand không phù hợp?

---

# 226. Jotai là gì?

## 📝 Tóm tắt
Jotai quản lý state dựa trên atom, cho phép cập nhật dữ liệu theo mức độ rất nhỏ.

## 💻 Ví dụ thực tế

```ts
const countAtom = atom(0);
```

## 🔗 Link tham khảo
- https://jotai.org/

## ❓ Câu hỏi còn lại
- Atom khác Store thế nào?
- Jotai và Recoil khác nhau ra sao?

---

# 227. Recoil là gì?

## 📝 Tóm tắt
Recoil là thư viện state management của Meta dựa trên atom và selector.

## 💻 Ví dụ thực tế

```ts
const userState = atom({
  key: "user",
  default: null,
});
```

## 🔗 Link tham khảo
- https://recoiljs.org/

## ❓ Câu hỏi còn lại
- Recoil có còn được duy trì mạnh không?
- Khi nào nên chọn Recoil?

---

# 228. Selector trong State Management là gì?

## 📝 Tóm tắt
Selector là hàm dùng để tính toán hoặc lấy dữ liệu từ state một cách tối ưu.

## 💻 Ví dụ thực tế

```ts
const userName = useSelector(
  state => state.user.name
);
```

## 🔗 Link tham khảo
- https://redux.js.org/

## ❓ Câu hỏi còn lại
- Memoized Selector hoạt động thế nào?
- Reselect giúp tối ưu gì?

---

# 229. Reselect là gì?

## 📝 Tóm tắt
Reselect là thư viện tạo memoized selector giúp tránh tính toán lại không cần thiết.

## 💻 Ví dụ thực tế

```ts
const selectCompletedTodos =
  createSelector(
    [selectTodos],
    todos =>
      todos.filter(t => t.done)
  );
```

## 🔗 Link tham khảo
- https://github.com/reduxjs/reselect

## ❓ Câu hỏi còn lại
- Memoization có tốn bộ nhớ không?
- Khi nào không cần Reselect?

---

# 230. Event-Driven Architecture trong Frontend là gì?

## 📝 Tóm tắt
Event-Driven Architecture cho phép các module giao tiếp thông qua event thay vì gọi trực tiếp nhau.

## 💻 Ví dụ thực tế

```txt
User Login
↓
Emit Event
↓
Notification Module
Analytics Module
```

## 🔗 Link tham khảo
- https://martinfowler.com/articles/201701-event-driven.html

## ❓ Câu hỏi còn lại
- Khi nào Event-Driven gây khó debug?
- Micro Frontend áp dụng mô hình này thế nào?

</details>

<details>
<summary><strong>📅 2026-06-15 — TypeScript Advanced Types & Type Safety</strong></summary>

---

# 211. Generics trong TypeScript là gì?

## 📝 Tóm tắt
Generics cho phép tạo các hàm, interface hoặc type có thể hoạt động với nhiều kiểu dữ liệu khác nhau mà vẫn đảm bảo type safety.

## 💻 Ví dụ thực tế

```ts
function identity<T>(value: T): T {
  return value;
}
```

## 🔗 Link tham khảo
- https://www.typescriptlang.org/docs/handbook/2/generics.html

## ❓ Câu hỏi còn lại
- Khi nào nên giới hạn Generic bằng extends?
- Generic có ảnh hưởng compile time không?

---

# 212. Utility Types là gì?

## 📝 Tóm tắt
Utility Types là các type được TypeScript cung cấp sẵn để biến đổi kiểu dữ liệu.

## 💻 Ví dụ thực tế

```ts
Partial<User>
Required<User>
Pick<User, "id">
```

## 🔗 Link tham khảo
- https://www.typescriptlang.org/docs/handbook/utility-types.html

## ❓ Câu hỏi còn lại
- Utility Type nào được dùng nhiều nhất?
- Có thể tự tạo Utility Type không?

---

# 213. Mapped Types là gì?

## 📝 Tóm tắt
Mapped Types cho phép tạo type mới bằng cách lặp qua các key của type cũ.

## 💻 Ví dụ thực tế

```ts
type ReadonlyUser = {
  readonly [K in keyof User]: User[K];
};
```

## 🔗 Link tham khảo
- https://www.typescriptlang.org/docs/handbook/2/mapped-types.html

## ❓ Câu hỏi còn lại
- Partial được xây dựng bằng Mapped Type thế nào?
- Khi nào Mapped Type gây khó đọc?

---

# 214. Conditional Types là gì?

## 📝 Tóm tắt
Conditional Types cho phép tạo type dựa trên điều kiện.

## 💻 Ví dụ thực tế

```ts
type IsString<T> =
  T extends string
    ? true
    : false;
```

## 🔗 Link tham khảo
- https://www.typescriptlang.org/docs/handbook/2/conditional-types.html

## ❓ Câu hỏi còn lại
- Infer thường đi cùng Conditional Type thế nào?
- Khi nào Conditional Type quá phức tạp?

---

# 215. Infer Keyword là gì?

## 📝 Tóm tắt
infer cho phép TypeScript suy luận một kiểu dữ liệu bên trong Conditional Type.

## 💻 Ví dụ thực tế

```ts
type Return<T> =
  T extends (...args: any[]) => infer R
    ? R
    : never;
```

## 🔗 Link tham khảo
- https://www.typescriptlang.org/docs/handbook/2/conditional-types.html

## ❓ Câu hỏi còn lại
- ReturnType được xây dựng như thế nào?
- Infer có dùng được nhiều lần không?

---

# 216. keyof là gì?

## 📝 Tóm tắt
keyof trả về tập hợp các key của một object type.

## 💻 Ví dụ thực tế

```ts
type UserKeys = keyof User;
```

## 🔗 Link tham khảo
- https://www.typescriptlang.org/docs/handbook/2/keyof-types.html

## ❓ Câu hỏi còn lại
- keyof kết hợp Generic ra sao?
- keyof có hoạt động với union không?

---

# 217. Discriminated Union là gì?

## 📝 Tóm tắt
Discriminated Union giúp TypeScript tự động thu hẹp kiểu dữ liệu dựa trên một thuộc tính chung.

## 💻 Ví dụ thực tế

```ts
type Shape =
  | { type: "circle" }
  | { type: "square" };
```

## 🔗 Link tham khảo
- https://www.typescriptlang.org/docs/handbook/2/narrowing.html

## ❓ Câu hỏi còn lại
- Vì sao Redux Action thường dùng pattern này?
- Khi nào nên dùng enum thay vì string literal?

---

# 218. Type Narrowing là gì?

## 📝 Tóm tắt
Type Narrowing giúp TypeScript xác định kiểu dữ liệu cụ thể hơn trong từng nhánh code.

## 💻 Ví dụ thực tế

```ts
if (typeof value === "string") {
  value.toUpperCase();
}
```

## 🔗 Link tham khảo
- https://www.typescriptlang.org/docs/handbook/2/narrowing.html

## ❓ Câu hỏi còn lại
- User Defined Type Guard là gì?
- Narrowing hoạt động với Array thế nào?

---

# 219. Type Assertion là gì?

## 📝 Tóm tắt
Type Assertion cho phép lập trình viên chỉ định kiểu dữ liệu mà TypeScript nên tin tưởng.

## 💻 Ví dụ thực tế

```ts
const input =
  document.getElementById(
    "email"
  ) as HTMLInputElement;
```

## 🔗 Link tham khảo
- https://www.typescriptlang.org/docs/handbook/2/everyday-types.html

## ❓ Câu hỏi còn lại
- Khi nào Type Assertion gây bug runtime?
- Nên dùng Assertion hay Type Guard?

---

# 220. unknown và any khác nhau thế nào?

## 📝 Tóm tắt
any bỏ qua kiểm tra kiểu dữ liệu, còn unknown yêu cầu phải kiểm tra trước khi sử dụng.

## 💻 Ví dụ thực tế

```ts
let a: any;
let b: unknown;
```

## 🔗 Link tham khảo
- https://www.typescriptlang.org/docs/handbook/2/functions.html

## ❓ Câu hỏi còn lại
- Có nên cấm any trong dự án?
- unknown giúp tăng type safety thế nào?

</details>

<details>
<summary><strong>📅 2026-06-14 — Modern Frontend Build Systems & Engineering Practices</strong></summary>

---

# 201. Tree Shaking là gì?

## 📝 Tóm tắt
Tree Shaking là kỹ thuật loại bỏ code không được sử dụng khỏi bundle cuối cùng.

## 💻 Ví dụ thực tế

```js
// math.js
export const sum = () => {};
export const multiply = () => {};

// app.js
import { sum } from "./math";
```

## 🔗 Link tham khảo
- https://webpack.js.org/guides/tree-shaking/

## ❓ Câu hỏi còn lại
- Vì sao CommonJS tree shaking kém hơn ESM?
- Dynamic import ảnh hưởng tree shaking thế nào?

---

# 202. Dead Code Elimination (DCE) là gì?

## 📝 Tóm tắt
DCE là quá trình loại bỏ code chắc chắn không được thực thi trong runtime.

## 💻 Ví dụ thực tế

```js
if (false) {
  console.log("never run");
}
```

## 🔗 Link tham khảo
- https://rollupjs.org/

## ❓ Câu hỏi còn lại
- DCE khác Tree Shaking thế nào?
- Minifier tham gia DCE ra sao?

---

# 203. Vite nhanh hơn Webpack ở điểm nào?

## 📝 Tóm tắt
Vite tận dụng ESM và esbuild để giảm thời gian khởi động dev server.

## 💻 Ví dụ thực tế

```txt
Webpack
↓
Bundle trước

Vite
↓
Serve theo module
```

## 🔗 Link tham khảo
- https://vitejs.dev/

## ❓ Câu hỏi còn lại
- Khi nào Webpack vẫn phù hợp hơn?
- Vite build production bằng gì?

---

# 204. Turborepo là gì?

## 📝 Tóm tắt
Turborepo giúp quản lý monorepo và tối ưu build thông qua caching.

## 💻 Ví dụ thực tế

```txt
apps/
packages/
```

## 🔗 Link tham khảo
- https://turbo.build/repo

## ❓ Câu hỏi còn lại
- Turborepo khác Nx thế nào?
- Remote Cache hoạt động ra sao?

---

# 205. Monorepo là gì?

## 📝 Tóm tắt
Monorepo là mô hình lưu nhiều ứng dụng hoặc package trong cùng một repository.

## 💻 Ví dụ thực tế

```txt
apps/
 ├─ web
 ├─ admin

packages/
 ├─ ui
 ├─ utils
```

## 🔗 Link tham khảo
- https://monorepo.tools/

## ❓ Câu hỏi còn lại
- Khi nào nên dùng Monorepo?
- Nhược điểm lớn nhất là gì?

---

# 206. Semantic Versioning (SemVer) là gì?

## 📝 Tóm tắt
SemVer là quy tắc đặt version theo dạng MAJOR.MINOR.PATCH.

## 💻 Ví dụ thực tế

```txt
1.2.5

MAJOR.MINOR.PATCH
```

## 🔗 Link tham khảo
- https://semver.org/

## ❓ Câu hỏi còn lại
- Khi nào tăng Major Version?
- Breaking Change là gì?

---

# 207. Changelog là gì?

## 📝 Tóm tắt
Changelog ghi lại các thay đổi giữa các phiên bản phần mềm.

## 💻 Ví dụ thực tế

```txt
v2.0.0
- Add Dashboard
- Remove Legacy API
```

## 🔗 Link tham khảo
- https://keepachangelog.com/

## ❓ Câu hỏi còn lại
- Changelog nên tạo thủ công hay tự động?
- Conventional Commit hỗ trợ thế nào?

---

# 208. Conventional Commit là gì?

## 📝 Tóm tắt
Conventional Commit là chuẩn đặt tên commit giúp tự động hóa release và changelog.

## 💻 Ví dụ thực tế

```txt
feat: add login page

fix: resolve token bug

docs: update README
```

## 🔗 Link tham khảo
- https://www.conventionalcommits.org/

## ❓ Câu hỏi còn lại
- feat khác fix thế nào?
- Commit message nên chi tiết đến đâu?

---

# 209. Git Hooks là gì?

## 📝 Tóm tắt
Git Hooks cho phép chạy script tự động trước hoặc sau các hành động Git.

## 💻 Ví dụ thực tế

```txt
pre-commit
↓
eslint
↓
commit
```

## 🔗 Link tham khảo
- https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks

## ❓ Câu hỏi còn lại
- Husky hoạt động như thế nào?
- Nên chạy test gì ở pre-commit?

---

# 210. CI/CD Pipeline là gì?

## 📝 Tóm tắt
CI/CD Pipeline tự động hóa quá trình build, test và deploy ứng dụng.

## 💻 Ví dụ thực tế

```txt
Push Code
↓
Lint
↓
Test
↓
Build
↓
Deploy
```

## 🔗 Link tham khảo
- https://docs.github.com/en/actions

## ❓ Câu hỏi còn lại
- Frontend CI/CD tối thiểu cần những bước nào?
- Khi nào nên dùng Preview Deployment?

</details>

<details>
<summary><strong>📅 2026-06-12 — Frontend Testing, Reliability & Code Quality</strong></summary>

---

# 191. Unit Test là gì?

## 📝 Tóm tắt
Unit Test kiểm tra một hàm hoặc module riêng lẻ để đảm bảo hoạt động đúng như mong đợi.

## 💻 Ví dụ thực tế

```ts
expect(sum(1, 2)).toBe(3);
```

## 🔗 Link tham khảo
- https://jestjs.io/docs/getting-started

## ❓ Câu hỏi còn lại
- Unit Test nên mock đến mức nào?
- Khi nào Unit Test trở nên khó bảo trì?

---

# 192. Integration Test là gì?

## 📝 Tóm tắt
Integration Test kiểm tra sự phối hợp giữa nhiều module hoặc component với nhau.

## 💻 Ví dụ thực tế

```txt
User Form
↓
Submit Button
↓
API Call
↓
Success Message
```

## 🔗 Link tham khảo
- https://testing-library.com/docs/react-testing-library/intro/

## ❓ Câu hỏi còn lại
- Integration Test khác E2E thế nào?
- Có nên mock API trong Integration Test không?

---

# 193. End-to-End Test (E2E) là gì?

## 📝 Tóm tắt
E2E Test mô phỏng hành vi thực tế của người dùng từ đầu đến cuối hệ thống.

## 💻 Ví dụ thực tế

```txt
Login
↓
Create Order
↓
Payment
↓
Success
```

## 🔗 Link tham khảo
- https://playwright.dev/

## ❓ Câu hỏi còn lại
- E2E nên cover bao nhiêu luồng?
- Vì sao E2E thường chậm hơn các loại test khác?

---

# 194. Test Pyramid là gì?

## 📝 Tóm tắt
Test Pyramid là chiến lược phân bổ số lượng test theo hình kim tự tháp để tối ưu chi phí bảo trì.

## 💻 Ví dụ thực tế

```txt
      E2E
   Integration
 Unit Tests
```

## 🔗 Link tham khảo
- https://martinfowler.com/articles/practical-test-pyramid.html

## ❓ Câu hỏi còn lại
- Có nên chỉ viết E2E Test không?
- Test Pyramid còn phù hợp hiện nay không?

---

# 195. Mocking là gì?

## 📝 Tóm tắt
Mocking là kỹ thuật thay thế dependency thật bằng dữ liệu hoặc hành vi giả lập để kiểm thử.

## 💻 Ví dụ thực tế

```ts
vi.mock("./api");
```

## 🔗 Link tham khảo
- https://vitest.dev/guide/mocking.html

## ❓ Câu hỏi còn lại
- Mock quá nhiều có rủi ro gì?
- Khi nào nên dùng Mock Service Worker?

---

# 196. Contract Testing là gì?

## 📝 Tóm tắt
Contract Testing giúp đảm bảo frontend và backend tuân thủ cùng một API contract.

## 💻 Ví dụ thực tế

```txt
Frontend
↓
API Contract
↓
Backend
```

## 🔗 Link tham khảo
- https://docs.pact.io/

## ❓ Câu hỏi còn lại
- Contract Test khác Integration Test thế nào?
- Khi nào nên áp dụng Pact?

---

# 197. Feature Flag là gì?

## 📝 Tóm tắt
Feature Flag cho phép bật hoặc tắt tính năng mà không cần deploy lại ứng dụng.

## 💻 Ví dụ thực tế

```ts
if (feature.newDashboard) {
  renderNewUI();
}
```

## 🔗 Link tham khảo
- https://martinfowler.com/articles/feature-toggles.html

## ❓ Câu hỏi còn lại
- Feature Flag nên lưu ở đâu?
- Làm sao tránh Feature Flag tồn đọng?

---

# 198. Canary Release là gì?

## 📝 Tóm tắt
Canary Release triển khai phiên bản mới cho một nhóm nhỏ người dùng trước khi rollout toàn bộ.

## 💻 Ví dụ thực tế

```txt
5% Users
↓
20% Users
↓
100% Users
```

## 🔗 Link tham khảo
- https://martinfowler.com/bliki/CanaryRelease.html

## ❓ Câu hỏi còn lại
- Canary khác Blue-Green Deployment thế nào?
- Những metric nào cần theo dõi khi rollout?

---

# 199. Blue-Green Deployment là gì?

## 📝 Tóm tắt
Blue-Green Deployment duy trì hai môi trường giống nhau để chuyển đổi traffic nhanh chóng khi deploy.

## 💻 Ví dụ thực tế

```txt
Blue (Current)
↓
Switch Traffic
↓
Green (New)
```

## 🔗 Link tham khảo
- https://martinfowler.com/bliki/BlueGreenDeployment.html

## ❓ Câu hỏi còn lại
- Chi phí Blue-Green có cao không?
- Rollback diễn ra như thế nào?

---

# 200. Technical Debt là gì?

## 📝 Tóm tắt
Technical Debt là chi phí phát sinh trong tương lai do các quyết định kỹ thuật ngắn hạn ở hiện tại.

## 💻 Ví dụ thực tế

```txt
Copy-Paste Code
↓
Nhiều Bug
↓
Khó Maintain
```

## 🔗 Link tham khảo
- https://martinfowler.com/bliki/TechnicalDebt.html

## ❓ Câu hỏi còn lại
- Làm sao đo lường Technical Debt?
- Khi nào nên ưu tiên trả nợ kỹ thuật?

</details>

<details>
<summary><strong>📅 2026-06-11 — Advanced Rendering, Caching & Frontend Scalability</strong></summary>

---

# 181. ISR (Incremental Static Regeneration) là gì?

## 📝 Tóm tắt
ISR cho phép cập nhật lại trang Static sau khi deploy mà không cần build lại toàn bộ ứng dụng.

## 💻 Ví dụ thực tế

```tsx
export const revalidate = 60;
```

## 🔗 Link tham khảo
- https://nextjs.org/docs/app/building-your-application/data-fetching/incremental-static-regeneration

## ❓ Câu hỏi còn lại
- ISR khác SSR thế nào?
- Khi nào ISR phù hợp hơn SSG?

---

# 182. Edge Caching là gì?

## 📝 Tóm tắt
Edge Caching lưu nội dung tại các Edge Location gần người dùng để giảm độ trễ.

## 💻 Ví dụ thực tế

```txt
User VN
↓
Singapore Edge
↓
Response
```

## 🔗 Link tham khảo
- https://vercel.com/docs/edge-network/caching

## ❓ Câu hỏi còn lại
- Cache hit ratio là gì?
- Cache miss ảnh hưởng hiệu năng thế nào?

---

# 183. React Suspense for Data Fetching là gì?

## 📝 Tóm tắt
Suspense cho phép React hiển thị fallback UI trong khi dữ liệu đang được tải.

## 💻 Ví dụ thực tế

```tsx
<Suspense fallback={<Loading />}>
  <UserList />
</Suspense>
```

## 🔗 Link tham khảo
- https://react.dev/reference/react/Suspense

## ❓ Câu hỏi còn lại
- Suspense khác loading state truyền thống thế nào?
- Khi nào nên dùng Suspense?

---

# 184. Selective Hydration là gì?

## 📝 Tóm tắt
Selective Hydration cho phép React ưu tiên hydrate những phần UI quan trọng trước.

## 💻 Ví dụ thực tế

```txt
Navbar
↓
Button
↓
Comments Section
```

## 🔗 Link tham khảo
- https://react.dev/reference/react-dom/client/hydrateRoot

## ❓ Câu hỏi còn lại
- Selective Hydration giúp cải thiện TTI thế nào?
- React Scheduler tham gia ra sao?

---

# 185. Partial Rendering là gì?

## 📝 Tóm tắt
Partial Rendering chỉ render hoặc cập nhật phần dữ liệu thay đổi thay vì toàn bộ giao diện.

## 💻 Ví dụ thực tế

```txt
Update Notification
↓
Chỉ render Notification Panel
```

## 🔗 Link tham khảo
- https://nextjs.org/docs/app

## ❓ Câu hỏi còn lại
- Partial Rendering khác React.memo thế nào?
- Next.js App Router hỗ trợ ra sao?

---

# 186. Cache Stampede là gì?

## 📝 Tóm tắt
Cache Stampede xảy ra khi nhiều request cùng lúc làm cache hết hạn và đồng thời truy cập database.

## 💻 Ví dụ thực tế

```txt
Cache Expired
↓
1000 Requests
↓
Database Overload
```

## 🔗 Link tham khảo
- https://en.wikipedia.org/wiki/Cache_stampede

## ❓ Câu hỏi còn lại
- Cache warming là gì?
- Stale-While-Revalidate giúp giảm vấn đề này thế nào?

---

# 187. Event Sourcing là gì?

## 📝 Tóm tắt
Event Sourcing lưu toàn bộ các sự kiện thay đổi trạng thái thay vì chỉ lưu trạng thái cuối cùng.

## 💻 Ví dụ thực tế

```txt
Create User
Update User
Delete User
```

## 🔗 Link tham khảo
- https://martinfowler.com/eaaDev/EventSourcing.html

## ❓ Câu hỏi còn lại
- Frontend có áp dụng Event Sourcing không?
- Event Store hoạt động thế nào?

---

# 188. CQRS là gì?

## 📝 Tóm tắt
CQRS tách riêng luồng đọc (Query) và ghi (Command) để tối ưu hệ thống.

## 💻 Ví dụ thực tế

```txt
Command API
↓
Write Database

Query API
↓
Read Database
```

## 🔗 Link tham khảo
- https://martinfowler.com/bliki/CQRS.html

## ❓ Câu hỏi còn lại
- CQRS thường đi cùng Event Sourcing thế nào?
- Khi nào CQRS là over-engineering?

---

# 189. Feature-Based Architecture là gì?

## 📝 Tóm tắt
Feature-Based Architecture tổ chức source code theo tính năng thay vì theo loại file.

## 💻 Ví dụ thực tế

```txt
features/
 ├─ users/
 ├─ orders/
 ├─ auth/
```

## 🔗 Link tham khảo
- https://feature-sliced.design/

## ❓ Câu hỏi còn lại
- Feature-based khác Layer-based thế nào?
- Dự án nhỏ có nên áp dụng không?

---

# 190. Frontend Scalability là gì?

## 📝 Tóm tắt
Frontend Scalability là khả năng mở rộng codebase, team và hệ thống mà vẫn dễ bảo trì.

## 💻 Ví dụ thực tế

```txt
Design System
Code Splitting
Micro Frontend
Monorepo
```

## 🔗 Link tham khảo
- https://martinfowler.com/articles/micro-frontends.html

## ❓ Câu hỏi còn lại
- Dấu hiệu codebase không scalable là gì?
- Team 20+ FE thường tổ chức source code thế nào?

</details>

<details>
<summary><strong>📅 2026-06-10 — Frontend Design Patterns & Advanced React Hooks</strong></summary>

---

# 171. Custom Hook là gì?

## 📝 Tóm tắt
Custom Hook là cách tái sử dụng logic stateful giữa nhiều component mà không lặp code.

## 💻 Ví dụ thực tế

```tsx
function useWindowSize() {
  // logic
}
```

## 🔗 Link tham khảo
- https://react.dev/learn/reusing-logic-with-custom-hooks

## ❓ Câu hỏi còn lại
- Khi nào nên tạo Custom Hook?
- Custom Hook khác Utility Function thế nào?

---

# 172. Compound Component Pattern là gì?

## 📝 Tóm tắt
Compound Component cho phép nhiều component con phối hợp hoạt động thông qua context chung.

## 💻 Ví dụ thực tế

```tsx
<Tabs>
  <Tabs.List />
  <Tabs.Panel />
</Tabs>
```

## 🔗 Link tham khảo
- https://kentcdodds.com/blog/compound-components-with-react-hooks

## ❓ Câu hỏi còn lại
- Compound Component khác prop drilling thế nào?
- Khi nào pattern này phù hợp?

---

# 173. Headless Component là gì?

## 📝 Tóm tắt
Headless Component chỉ cung cấp logic và state, không áp đặt giao diện.

## 💻 Ví dụ thực tế

```tsx
const {
  selected,
  open
} = useSelect();
```

## 🔗 Link tham khảo
- https://headlessui.com/

## ❓ Câu hỏi còn lại
- Headless UI khác Ant Design thế nào?
- Khi nào nên chọn headless component?

---

# 174. Container-Presenter Pattern là gì?

## 📝 Tóm tắt
Pattern này tách logic xử lý dữ liệu khỏi phần hiển thị UI.

## 💻 Ví dụ thực tế

```txt
UserContainer
↓
UserList
```

## 🔗 Link tham khảo
- https://www.patterns.dev/react/presentational-container-pattern

## ❓ Câu hỏi còn lại
- Custom Hook có thay thế pattern này không?
- Khi nào nên tách Container?

---

# 175. useImperativeHandle là gì?

## 📝 Tóm tắt
useImperativeHandle cho phép component cha gọi trực tiếp method của component con.

## 💻 Ví dụ thực tế

```tsx
useImperativeHandle(ref, () => ({
  open,
  close,
}));
```

## 🔗 Link tham khảo
- https://react.dev/reference/react/useImperativeHandle

## ❓ Câu hỏi còn lại
- Khi nào nên dùng ref thay vì props?
- useImperativeHandle có làm code khó maintain không?

---

# 176. Forward Ref là gì?

## 📝 Tóm tắt
Forward Ref cho phép truyền ref từ component cha xuống DOM hoặc component con.

## 💻 Ví dụ thực tế

```tsx
const Input = forwardRef(
  (props, ref) => {
    return <input ref={ref} />;
  }
);
```

## 🔗 Link tham khảo
- https://react.dev/reference/react/forwardRef

## ❓ Câu hỏi còn lại
- Forward Ref thường dùng trong UI Library thế nào?
- React 19 thay đổi gì với ref?

---

# 177. useLayoutEffect là gì?

## 📝 Tóm tắt
useLayoutEffect chạy đồng bộ sau khi DOM update nhưng trước khi browser paint.

## 💻 Ví dụ thực tế

```tsx
useLayoutEffect(() => {
  measureElement();
}, []);
```

## 🔗 Link tham khảo
- https://react.dev/reference/react/useLayoutEffect

## ❓ Câu hỏi còn lại
- useLayoutEffect khác useEffect thế nào?
- Khi nào useLayoutEffect gây block render?

---

# 178. useInsertionEffect là gì?

## 📝 Tóm tắt
useInsertionEffect được thiết kế cho CSS-in-JS libraries để inject style trước khi layout được tính toán.

## 💻 Ví dụ thực tế

```tsx
useInsertionEffect(() => {
  injectStyles();
});
```

## 🔗 Link tham khảo
- https://react.dev/reference/react/useInsertionEffect

## ❓ Câu hỏi còn lại
- Vì sao hook này hiếm khi dùng?
- Styled Components sử dụng hook này thế nào?

---

# 179. Slot Pattern là gì?

## 📝 Tóm tắt
Slot Pattern cho phép truyền UI tùy chỉnh vào các vị trí xác định trong component.

## 💻 Ví dụ thực tế

```tsx
<Card
  header={<Header />}
  footer={<Footer />}
/>
```

## 🔗 Link tham khảo
- https://www.patterns.dev/react/compound-pattern/

## ❓ Câu hỏi còn lại
- Slot Pattern khác children thế nào?
- Khi nào nên dùng nhiều slot?

---

# 180. Command Pattern trong Frontend là gì?

## 📝 Tóm tắt
Command Pattern đóng gói hành động thành object để dễ quản lý, undo hoặc queue.

## 💻 Ví dụ thực tế

```txt
Add Node
Delete Node
Undo
Redo
```

## 🔗 Link tham khảo
- https://refactoring.guru/design-patterns/command

## ❓ Câu hỏi còn lại
- React Flow áp dụng Command Pattern thế nào?
- Khi nào nên dùng cho editor hoặc workflow builder?

</details>

<details>
<summary><strong>📅 2026-06-09 — Advanced JavaScript Runtime & Browser APIs</strong></summary>

---

# 161. Execution Context là gì?

## 📝 Tóm tắt
Execution Context là môi trường mà JavaScript thực thi code, quản lý scope, biến và hàm.

## 💻 Ví dụ thực tế

```js
function greet() {
  const name = "Hieu";
  console.log(name);
}
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/JavaScript

## ❓ Câu hỏi còn lại
- Global Context và Function Context khác nhau thế nào?
- Execution Context được tạo khi nào?

---

# 162. Call Stack là gì?

## 📝 Tóm tắt
Call Stack là cấu trúc dữ liệu theo cơ chế LIFO dùng để quản lý các hàm đang thực thi.

## 💻 Ví dụ thực tế

```js
function a() {
  b();
}

function b() {
  c();
}

function c() {}
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Glossary/Call_stack

## ❓ Câu hỏi còn lại
- Stack Overflow xảy ra như thế nào?
- Browser giới hạn stack size ra sao?

---

# 163. Memory Leak trong JavaScript là gì?

## 📝 Tóm tắt
Memory Leak xảy ra khi object không còn sử dụng nhưng vẫn bị giữ tham chiếu và không được Garbage Collector dọn dẹp.

## 💻 Ví dụ thực tế

```js
window.cache = largeObject;
```

## 🔗 Link tham khảo
- https://developer.chrome.com/docs/devtools/memory-problems

## ❓ Câu hỏi còn lại
- React thường gặp memory leak ở đâu?
- DevTools phát hiện leak thế nào?

---

# 164. Garbage Collection là gì?

## 📝 Tóm tắt
Garbage Collection là cơ chế tự động giải phóng bộ nhớ của JavaScript.

## 💻 Ví dụ thực tế

```js
let user = {
  name: "Hieu",
};

user = null;
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Memory_management

## ❓ Câu hỏi còn lại
- Mark and Sweep hoạt động ra sao?
- Circular Reference có gây leak không?

---

# 165. Debounce là gì?

## 📝 Tóm tắt
Debounce trì hoãn việc thực thi hàm cho đến khi người dùng ngừng thao tác trong một khoảng thời gian.

## 💻 Ví dụ thực tế

```js
debounce(search, 500);
```

## 🔗 Link tham khảo
- https://lodash.com/docs/#debounce

## ❓ Câu hỏi còn lại
- Debounce khác Throttle thế nào?
- Khi nào debounce gây UX kém?

---

# 166. Throttle là gì?

## 📝 Tóm tắt
Throttle giới hạn số lần hàm được thực thi trong một khoảng thời gian nhất định.

## 💻 Ví dụ thực tế

```js
throttle(handleScroll, 100);
```

## 🔗 Link tham khảo
- https://lodash.com/docs/#throttle

## ❓ Câu hỏi còn lại
- Scroll event nên dùng debounce hay throttle?
- requestAnimationFrame có thay thế throttle được không?

---

# 167. requestAnimationFrame là gì?

## 📝 Tóm tắt
requestAnimationFrame cho phép browser tối ưu việc render animation theo refresh rate của màn hình.

## 💻 Ví dụ thực tế

```js
requestAnimationFrame(update);
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/API/window/requestAnimationFrame

## ❓ Câu hỏi còn lại
- Vì sao animation nên dùng requestAnimationFrame?
- RAF khác setInterval thế nào?

---

# 168. Shadow DOM là gì?

## 📝 Tóm tắt
Shadow DOM tạo một DOM tree độc lập giúp cô lập style và behavior của component.

## 💻 Ví dụ thực tế

```js
element.attachShadow({
  mode: "open",
});
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_shadow_DOM

## ❓ Câu hỏi còn lại
- Shadow DOM ảnh hưởng CSS thế nào?
- Web Components dùng Shadow DOM ra sao?

---

# 169. Custom Elements là gì?

## 📝 Tóm tắt
Custom Elements cho phép tạo HTML tag tùy chỉnh bằng Web Components.

## 💻 Ví dụ thực tế

```js
customElements.define(
  "user-card",
  UserCard
);
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_custom_elements

## ❓ Câu hỏi còn lại
- Custom Elements tích hợp React thế nào?
- Khi nào nên dùng Web Components?

---

# 170. Browser Storage gồm những gì?

## 📝 Tóm tắt
Browser Storage là tập hợp các cơ chế lưu trữ dữ liệu phía client.

## 💻 Ví dụ thực tế

```txt
localStorage
sessionStorage
IndexedDB
Cookies
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API

## ❓ Câu hỏi còn lại
- IndexedDB khác localStorage thế nào?
- Nên lưu Access Token ở đâu?

</details>

<details>
<summary><strong>📅 2026-06-08 — Network, Realtime & Production Frontend Systems</strong></summary>

---

# 151. REST API và GraphQL khác nhau thế nào?

## 📝 Tóm tắt
REST sử dụng nhiều endpoint khác nhau. GraphQL cho phép client chủ động chọn dữ liệu cần lấy từ một endpoint duy nhất.

## 💻 Ví dụ thực tế

```txt
REST
GET /users/1

GraphQL
query {
  user(id:1){
    id
    name
  }
}
```

## 🔗 Link tham khảo
- https://graphql.org/learn/

## ❓ Câu hỏi còn lại
- Khi nào GraphQL phù hợp hơn REST?
- GraphQL có nhược điểm gì?

---

# 152. N+1 Problem là gì?

## 📝 Tóm tắt
N+1 Problem xảy ra khi một request chính kéo theo nhiều request con không cần thiết.

## 💻 Ví dụ thực tế

```txt
Get Users
↓
Get User Posts x100
↓
101 Queries
```

## 🔗 Link tham khảo
- https://graphql.org/learn/performance/

## ❓ Câu hỏi còn lại
- DataLoader giải quyết vấn đề này thế nào?
- REST có gặp N+1 không?

---

# 153. Long Polling là gì?

## 📝 Tóm tắt
Long Polling giữ kết nối mở cho đến khi server có dữ liệu mới để trả về.

## 💻 Ví dụ thực tế

```txt
Client Request
↓
Server chờ dữ liệu
↓
Response khi có event
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest_API

## ❓ Câu hỏi còn lại
- Long Polling khác Polling thế nào?
- Khi nào nên dùng Long Polling?

---

# 154. Server-Sent Events (SSE) là gì?

## 📝 Tóm tắt
SSE cho phép server chủ động gửi dữ liệu một chiều đến client thông qua HTTP.

## 💻 Ví dụ thực tế

```js
const eventSource =
  new EventSource("/events");
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events

## ❓ Câu hỏi còn lại
- SSE khác WebSocket thế nào?
- Khi nào SSE hiệu quả hơn WebSocket?

---

# 155. WebSocket Lifecycle là gì?

## 📝 Tóm tắt
WebSocket trải qua các trạng thái kết nối, mở, trao đổi dữ liệu và đóng kết nối.

## 💻 Ví dụ thực tế

```txt
CONNECTING
↓
OPEN
↓
MESSAGE
↓
CLOSED
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/API/WebSocket

## ❓ Câu hỏi còn lại
- Heartbeat dùng để làm gì?
- Reconnect strategy nên thiết kế thế nào?

---

# 156. MQTT là gì?

## 📝 Tóm tắt
MQTT là giao thức publish/subscribe nhẹ, phù hợp cho IoT và realtime systems.

## 💻 Ví dụ thực tế

```txt
Publisher
↓
Broker
↓
Subscriber
```

## 🔗 Link tham khảo
- https://mqtt.org/

## ❓ Câu hỏi còn lại
- QoS 0,1,2 khác nhau thế nào?
- Khi nào MQTT tốt hơn WebSocket?

---

# 157. Backpressure là gì?

## 📝 Tóm tắt
Backpressure xảy ra khi dữ liệu được gửi nhanh hơn khả năng xử lý của hệ thống nhận.

## 💻 Ví dụ thực tế

```txt
1000 messages/sec
↓
Client xử lý 100/sec
↓
Queue tăng dần
```

## 🔗 Link tham khảo
- https://nodejs.org/en/learn/modules/backpressuring-in-streams

## ❓ Câu hỏi còn lại
- Làm sao phát hiện backpressure?
- Queue overflow xử lý thế nào?

---

# 158. Circuit Breaker Pattern là gì?

## 📝 Tóm tắt
Circuit Breaker giúp ngăn hệ thống liên tục gọi đến service đang lỗi.

## 💻 Ví dụ thực tế

```txt
API lỗi liên tục
↓
Open Circuit
↓
Tạm ngừng request
```

## 🔗 Link tham khảo
- https://martinfowler.com/bliki/CircuitBreaker.html

## ❓ Câu hỏi còn lại
- Frontend có cần circuit breaker không?
- Retry và circuit breaker kết hợp thế nào?

---

# 159. Exponential Backoff là gì?

## 📝 Tóm tắt
Exponential Backoff tăng dần thời gian retry sau mỗi lần thất bại để tránh làm quá tải hệ thống.

## 💻 Ví dụ thực tế

```txt
1s
↓
2s
↓
4s
↓
8s
```

## 🔗 Link tham khảo
- https://cloud.google.com/storage/docs/retry-strategy

## ❓ Câu hỏi còn lại
- Khi nào nên dừng retry?
- Vì sao cần random jitter?

---

# 160. Distributed Tracing là gì?

## 📝 Tóm tắt
Distributed Tracing giúp theo dõi một request đi qua nhiều service trong hệ thống.

## 💻 Ví dụ thực tế

```txt
Frontend
↓
BFF
↓
Auth Service
↓
User Service
```

## 🔗 Link tham khảo
- https://opentelemetry.io/docs/concepts/signals/traces/

## ❓ Câu hỏi còn lại
- Trace ID hoạt động thế nào?
- Frontend có tham gia tracing được không?

</details>

<details>
<summary><strong>📅 2026-06-07 — Modern Web Architecture & Browser Security</strong></summary>

---

# 141. Same-Origin Policy (SOP) là gì?

## 📝 Tóm tắt
Same-Origin Policy là cơ chế bảo mật của trình duyệt ngăn website truy cập tài nguyên từ origin khác.

## 💻 Ví dụ thực tế

```txt
https://app.com
↓
Không được đọc dữ liệu từ
https://admin.com
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy

## ❓ Câu hỏi còn lại
- SOP khác CORS thế nào?
- SOP bảo vệ người dùng ra sao?

---

# 142. CSRF là gì?

## 📝 Tóm tắt
CSRF là kiểu tấn công lợi dụng session của người dùng để gửi request ngoài ý muốn.

## 💻 Ví dụ thực tế

```txt
User đã login
↓
Click link độc hại
↓
Browser gửi request kèm cookie
```

## 🔗 Link tham khảo
- https://owasp.org/www-community/attacks/csrf

## ❓ Câu hỏi còn lại
- SameSite Cookie giúp chống CSRF thế nào?
- JWT có bị CSRF không?

---

# 143. XSS là gì?

## 📝 Tóm tắt
XSS xảy ra khi attacker chèn JavaScript độc hại vào website để thực thi trên trình duyệt người dùng.

## 💻 Ví dụ thực tế

```html
<script>
alert("hacked");
</script>
```

## 🔗 Link tham khảo
- https://owasp.org/www-community/attacks/xss/

## ❓ Câu hỏi còn lại
- React chống XSS bằng cách nào?
- dangerouslySetInnerHTML có rủi ro gì?

---

# 144. Content Security Policy (CSP) là gì?

## 📝 Tóm tắt
CSP là cơ chế cho phép giới hạn nguồn tài nguyên được tải nhằm giảm nguy cơ XSS.

## 💻 Ví dụ thực tế

```http
Content-Security-Policy:
script-src 'self'
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP

## ❓ Câu hỏi còn lại
- CSP ảnh hưởng third-party script thế nào?
- CSP có chặn XSS hoàn toàn không?

---

# 145. Cookie Attributes là gì?

## 📝 Tóm tắt
Cookie có nhiều thuộc tính để tăng bảo mật như HttpOnly, Secure và SameSite.

## 💻 Ví dụ thực tế

```http
Set-Cookie:
token=abc;
HttpOnly;
Secure;
SameSite=Lax
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies

## ❓ Câu hỏi còn lại
- SameSite=None cần điều kiện gì?
- HttpOnly có chống XSS không?

---

# 146. OAuth 2.0 là gì?

## 📝 Tóm tắt
OAuth 2.0 là chuẩn ủy quyền cho phép ứng dụng truy cập tài nguyên thay mặt người dùng.

## 💻 Ví dụ thực tế

```txt
Login with Google
↓
Google Consent Screen
↓
Access Token
```

## 🔗 Link tham khảo
- https://oauth.net/2/

## ❓ Câu hỏi còn lại
- OAuth khác Authentication thế nào?
- PKCE dùng để làm gì?

---

# 147. OpenID Connect (OIDC) là gì?

## 📝 Tóm tắt
OIDC là lớp xác thực xây dựng trên OAuth 2.0 giúp xác định danh tính người dùng.

## 💻 Ví dụ thực tế

```txt
OAuth:
Authorization

OIDC:
Authentication
```

## 🔗 Link tham khảo
- https://openid.net/connect/

## ❓ Câu hỏi còn lại
- ID Token chứa thông tin gì?
- Khi nào cần OIDC?

---

# 148. Access Token vs Refresh Token

## 📝 Tóm tắt
Access Token dùng để truy cập API. Refresh Token dùng để lấy Access Token mới khi hết hạn.

## 💻 Ví dụ thực tế

```txt
Access Token:
15 phút

Refresh Token:
30 ngày
```

## 🔗 Link tham khảo
- https://auth0.com/docs/secure/tokens

## ❓ Câu hỏi còn lại
- Refresh Token nên lưu ở đâu?
- Rotation Token là gì?

---

# 149. API Gateway là gì?

## 📝 Tóm tắt
API Gateway là điểm vào duy nhất cho các backend service trong hệ thống microservices.

## 💻 Ví dụ thực tế

```txt
Frontend
↓
API Gateway
↓
User Service
Order Service
Auth Service
```

## 🔗 Link tham khảo
- https://microservices.io/patterns/apigateway.html

## ❓ Câu hỏi còn lại
- API Gateway khác BFF thế nào?
- Có nên dùng cả Gateway và BFF không?

---

# 150. Rate Limiting là gì?

## 📝 Tóm tắt
Rate Limiting giới hạn số lượng request trong một khoảng thời gian nhằm bảo vệ hệ thống.

## 💻 Ví dụ thực tế

```txt
100 requests/minute
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Glossary/Rate_limit

## ❓ Câu hỏi còn lại
- Token Bucket hoạt động thế nào?
- Frontend nên xử lý HTTP 429 ra sao?

</details>

<details>
<summary><strong>📅 2026-06-06 — React Performance & Large-Scale Frontend Architecture</strong></summary>

---

# 131. Component Composition là gì?

## 📝 Tóm tắt
Component Composition là kỹ thuật xây dựng UI bằng cách kết hợp nhiều component nhỏ thay vì dùng inheritance.

## 💻 Ví dụ thực tế

```tsx
<Card>
  <CardHeader />
  <CardBody />
  <CardFooter />
</Card>
```

## 🔗 Link tham khảo
- https://react.dev/learn/passing-props-to-a-component

## ❓ Câu hỏi còn lại
- Composition tốt hơn inheritance ở điểm nào?
- Khi nào composition trở nên quá phức tạp?

---

# 132. Prop Drilling là gì?

## 📝 Tóm tắt
Prop Drilling xảy ra khi dữ liệu phải truyền qua nhiều cấp component trung gian.

## 💻 Ví dụ thực tế

```txt
App
↓
Layout
↓
Dashboard
↓
UserCard
```

## 🔗 Link tham khảo
- https://react.dev/learn/passing-data-deeply-with-context

## ❓ Câu hỏi còn lại
- Khi nào Context là giải pháp phù hợp?
- Prop drilling có phải lúc nào cũng xấu không?

---

# 133. Controlled Component vs Uncontrolled Component

## 📝 Tóm tắt
Controlled Component được quản lý bởi React State. Uncontrolled Component được quản lý bởi DOM.

## 💻 Ví dụ thực tế

```tsx
<input
  value={name}
  onChange={(e) => setName(e.target.value)}
/>
```

## 🔗 Link tham khảo
- https://react.dev/reference/react-dom/components/input

## ❓ Câu hỏi còn lại
- React Hook Form tối ưu theo hướng nào?
- Khi nào nên dùng uncontrolled form?

---

# 134. React Hook Form tối ưu hiệu năng như thế nào?

## 📝 Tóm tắt
React Hook Form sử dụng uncontrolled input và subscription để giảm re-render.

## 💻 Ví dụ thực tế

```tsx
const { register } = useForm();
```

## 🔗 Link tham khảo
- https://react-hook-form.com/

## ❓ Câu hỏi còn lại
- Vì sao React Hook Form nhanh hơn Formik?
- Controller dùng trong trường hợp nào?

---

# 135. Virtualization là gì?

## 📝 Tóm tắt
Virtualization chỉ render các item đang hiển thị trên màn hình thay vì render toàn bộ danh sách.

## 💻 Ví dụ thực tế

```txt
10,000 rows
↓
Render 20 rows visible
```

## 🔗 Link tham khảo
- https://tanstack.com/virtual

## ❓ Câu hỏi còn lại
- Virtualization ảnh hưởng SEO thế nào?
- Khi nào không nên dùng virtualization?

---

# 136. Windowing là gì?

## 📝 Tóm tắt
Windowing là kỹ thuật chỉ render một phần dữ liệu trong viewport hiện tại.

## 💻 Ví dụ thực tế

```txt
Visible Area
↓
Items 100-120
```

## 🔗 Link tham khảo
- https://web.dev/articles/virtualize-long-lists-react-window

## ❓ Câu hỏi còn lại
- Windowing khác Pagination thế nào?
- react-window và react-virtual khác nhau ra sao?

---

# 137. Bundle Analyzer là gì?

## 📝 Tóm tắt
Bundle Analyzer giúp phân tích bundle để tìm package lớn hoặc code dư thừa.

## 💻 Ví dụ thực tế

```bash
npm run analyze
```

## 🔗 Link tham khảo
- https://github.com/webpack-contrib/webpack-bundle-analyzer

## ❓ Câu hỏi còn lại
- Làm sao giảm bundle size hiệu quả?
- Package nào thường làm bundle tăng mạnh?

---

# 138. Dynamic Import là gì?

## 📝 Tóm tắt
Dynamic Import cho phép tải module khi cần thay vì tải ngay từ đầu.

## 💻 Ví dụ thực tế

```tsx
const AdminPage = lazy(
  () => import("./AdminPage")
);
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/import

## ❓ Câu hỏi còn lại
- Dynamic import khác code splitting thế nào?
- Khi nào dynamic import gây chậm UX?

---

# 139. Monolithic Frontend vs Micro Frontend

## 📝 Tóm tắt
Monolithic Frontend là một ứng dụng frontend duy nhất. Micro Frontend chia thành nhiều ứng dụng nhỏ độc lập.

## 💻 Ví dụ thực tế

```txt
Monolith:
1 React App

Micro Frontend:
Auth App
Admin App
Dashboard App
```

## 🔗 Link tham khảo
- https://micro-frontends.org/

## ❓ Câu hỏi còn lại
- Khi nào nên dùng Micro Frontend?
- Shared state giữa các app xử lý thế nào?

---

# 140. Frontend Observability là gì?

## 📝 Tóm tắt
Frontend Observability giúp theo dõi lỗi, hiệu năng và hành vi người dùng trên môi trường production.

## 💻 Ví dụ thực tế

```txt
Sentry
PostHog
Datadog
LogRocket
```

## 🔗 Link tham khảo
- https://sentry.io/welcome/

## ❓ Câu hỏi còn lại
- Error Monitoring khác Logging thế nào?
- Những metric nào nên theo dõi trong production?

</details>

<details>
<summary><strong>📅 2026-06-05 — Advanced State Management & Data Fetching</strong></summary>

---

# 121. Server State và Client State khác nhau thế nào?

## 📝 Tóm tắt
Client State là dữ liệu chỉ tồn tại trên frontend. Server State là dữ liệu đến từ API và cần đồng bộ với backend.

## 💻 Ví dụ thực tế

```txt
Client State:
Modal Open
Theme
Sidebar Collapse

Server State:
Users
Orders
Products
```

## 🔗 Link tham khảo
- https://tanstack.com/query/latest

## ❓ Câu hỏi còn lại
- Vì sao React Query không thay thế hoàn toàn Redux?
- Khi nào dữ liệu nên là Client State?

---

# 122. Cache Invalidation là gì?

## 📝 Tóm tắt
Cache Invalidation là quá trình đánh dấu dữ liệu cache không còn hợp lệ để fetch lại dữ liệu mới.

## 💻 Ví dụ thực tế

```js
queryClient.invalidateQueries({
  queryKey: ["users"]
});
```

## 🔗 Link tham khảo
- https://tanstack.com/query/latest/docs

## ❓ Câu hỏi còn lại
- Invalidate khác refetch thế nào?
- Khi nào invalidate quá nhiều gây issue?

---

# 123. Request Deduplication là gì?

## 📝 Tóm tắt
Request Deduplication giúp nhiều component dùng chung một request thay vì gọi API trùng lặp.

## 💻 Ví dụ thực tế

```txt
Component A
Component B
↓
1 API Request
```

## 🔗 Link tham khảo
- https://tanstack.com/query/latest

## ❓ Câu hỏi còn lại
- React Query dedupe request ra sao?
- SWR xử lý thế nào?

---

# 124. Polling là gì?

## 📝 Tóm tắt
Polling là kỹ thuật gọi API định kỳ để lấy dữ liệu mới.

## 💻 Ví dụ thực tế

```js
setInterval(fetchData, 5000);
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/API/setInterval

## ❓ Câu hỏi còn lại
- Polling khác WebSocket thế nào?
- Khi nào polling gây tốn tài nguyên?

---

# 125. Infinite Query là gì?

## 📝 Tóm tắt
Infinite Query hỗ trợ tải dữ liệu theo từng trang khi người dùng scroll.

## 💻 Ví dụ thực tế

```txt
Page 1
↓
Page 2
↓
Page 3
```

## 🔗 Link tham khảo
- https://tanstack.com/query/latest/docs/framework/react/guides/infinite-queries

## ❓ Câu hỏi còn lại
- Infinite Query cache page thế nào?
- Khi nào nên reset cache?

---

# 126. Waterfall Fetching là gì?

## 📝 Tóm tắt
Waterfall Fetching xảy ra khi request sau phải chờ request trước hoàn thành.

## 💻 Ví dụ thực tế

```txt
Get User
↓
Get Orders
↓
Get Order Details
```

## 🔗 Link tham khảo
- https://tanstack.com/query/latest

## ❓ Câu hỏi còn lại
- Parallel Query giải quyết vấn đề này ra sao?
- SSR ảnh hưởng waterfall như thế nào?

---

# 127. Optimistic Concurrency là gì?

## 📝 Tóm tắt
Optimistic Concurrency giả định dữ liệu không bị thay đổi đồng thời và xử lý conflict nếu xảy ra.

## 💻 Ví dụ thực tế

```txt
User A edit profile
User B edit profile
↓
Version Check
```

## 🔗 Link tham khảo
- https://martinfowler.com/eaaCatalog/optimisticOfflineLock.html

## ❓ Câu hỏi còn lại
- Frontend xử lý conflict thế nào?
- Version field được dùng ra sao?

---

# 128. Query Key là gì?

## 📝 Tóm tắt
Query Key là định danh duy nhất cho dữ liệu cache trong React Query.

## 💻 Ví dụ thực tế

```js
["users"]

["users", userId]

["orders", page]
```

## 🔗 Link tham khảo
- https://tanstack.com/query/latest

## ❓ Câu hỏi còn lại
- Query key nên thiết kế thế nào?
- Query key quá lớn có ảnh hưởng gì?

---

# 129. Normalized Cache là gì?

## 📝 Tóm tắt
Normalized Cache lưu dữ liệu theo entity thay vì theo response API.

## 💻 Ví dụ thực tế

```txt
users:
  1
  2
  3

posts:
  1
  2
```

## 🔗 Link tham khảo
- https://www.apollographql.com/docs/react/caching/overview

## ❓ Câu hỏi còn lại
- Apollo Cache hoạt động thế nào?
- React Query có normalized cache không?

---

# 130. BFF (Backend For Frontend) là gì?

## 📝 Tóm tắt
BFF là backend được thiết kế riêng cho từng frontend để giảm coupling với backend service.

## 💻 Ví dụ thực tế

```txt
React App
↓
NestJS BFF
↓
Microservices
```

## 🔗 Link tham khảo
- https://samnewman.io/patterns/architectural/bff/

## ❓ Câu hỏi còn lại
- BFF khác API Gateway thế nào?
- Khi nào không nên dùng BFF?

</details>

<details>
<summary><strong>📅 2026-06-04 — Advanced React & Browser Internals</strong></summary>

---

# 111. React Reconciliation Algorithm hoạt động như thế nào?

## 📝 Tóm tắt
Reconciliation là quá trình React so sánh Virtual DOM cũ và mới để xác định phần nào cần update trên DOM thật.

## 💻 Ví dụ thực tế

```txt
Old Tree
↓
New Tree
↓
Diff
↓
Update DOM tối thiểu
```

## 🔗 Link tham khảo
- https://react.dev/learn/render-and-commit

## ❓ Câu hỏi còn lại
- Vì sao React không dùng deep compare?
- Key ảnh hưởng diffing algorithm thế nào?

---

# 112. React.memo hoạt động nội bộ ra sao?

## 📝 Tóm tắt
React.memo sử dụng shallow comparison để quyết định có re-render component hay không.

## 💻 Ví dụ thực tế

```tsx
export default React.memo(UserCard);
```

## 🔗 Link tham khảo
- https://react.dev/reference/react/memo

## ❓ Câu hỏi còn lại
- React.memo có cost gì?
- Khi nào React.memo làm app chậm hơn?

---

# 113. Referential Equality là gì?

## 📝 Tóm tắt
Hai object hoặc array chỉ bằng nhau khi cùng tham chiếu đến một vùng nhớ.

## 💻 Ví dụ thực tế

```js
{} === {} // false

[] === [] // false
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness

## ❓ Câu hỏi còn lại
- Vì sao referential equality quan trọng với React?
- useMemo giúp ổn định reference như thế nào?

---

# 114. Structural Sharing là gì?

## 📝 Tóm tắt
Structural Sharing tái sử dụng phần dữ liệu không thay đổi khi tạo immutable state mới.

## 💻 Ví dụ thực tế

```txt
Old State
↓
Update user.name
↓
Reuse các object khác
```

## 🔗 Link tham khảo
- https://immerjs.github.io/immer/

## ❓ Câu hỏi còn lại
- Immer dùng structural sharing thế nào?
- Redux Toolkit hưởng lợi gì từ kỹ thuật này?

---

# 115. Browser Task Queue là gì?

## 📝 Tóm tắt
Task Queue chứa các macrotask như setTimeout, DOM events và được Event Loop xử lý tuần tự.

## 💻 Ví dụ thực tế

```js
setTimeout(() => {
  console.log("task");
}, 0);
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Event_loop

## ❓ Câu hỏi còn lại
- Task Queue khác Microtask Queue thế nào?
- Browser ưu tiên queue nào trước?

---

# 116. Mutation Observer là gì?

## 📝 Tóm tắt
Mutation Observer cho phép theo dõi thay đổi của DOM tree.

## 💻 Ví dụ thực tế

```js
const observer = new MutationObserver(callback);
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver

## ❓ Câu hỏi còn lại
- Khi nào Mutation Observer hữu ích?
- Có ảnh hưởng performance không?

---

# 117. Resize Observer là gì?

## 📝 Tóm tắt
Resize Observer giúp phát hiện khi kích thước của element thay đổi.

## 💻 Ví dụ thực tế

```js
const observer = new ResizeObserver(callback);
```

## 🔗 Link tham khảo
- https://developer.mozilla.org/en-US/docs/Web/API/ResizeObserver

## ❓ Câu hỏi còn lại
- ResizeObserver khác window resize thế nào?
- Khi nào nên dùng ResizeObserver?

---

# 118. React Key Stability là gì?

## 📝 Tóm tắt
Key phải ổn định giữa các lần render để React reuse component chính xác.

## 💻 Ví dụ thực tế

```tsx
users.map(user => (
  <UserCard key={user.id} />
))
```

## 🔗 Link tham khảo
- https://react.dev/learn/rendering-lists

## ❓ Câu hỏi còn lại
- Vì sao index làm key gây bug?
- Key ảnh hưởng state component thế nào?

---

# 119. Render Props Pattern là gì?

## 📝 Tóm tắt
Render Props là pattern chia sẻ logic bằng cách truyền function làm prop.

## 💻 Ví dụ thực tế

```tsx
<DataProvider
  render={(data) => (
    <UserList data={data} />
  )}
/>
```

## 🔗 Link tham khảo
- https://legacy.reactjs.org/docs/render-props.html

## ❓ Câu hỏi còn lại
- Render Props khác Custom Hook thế nào?
- Vì sao Render Props ít được dùng hơn hiện nay?

---

# 120. Higher Order Component (HOC) là gì?

## 📝 Tóm tắt
HOC là function nhận vào component và trả về component mới với logic được mở rộng.

## 💻 Ví dụ thực tế

```tsx
const EnhancedComponent =
  withAuth(Component);
```

## 🔗 Link tham khảo
- https://legacy.reactjs.org/docs/higher-order-components.html

## ❓ Câu hỏi còn lại
- HOC khác Hook thế nào?
- Khi nào HOC vẫn là lựa chọn tốt?

</details>

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
