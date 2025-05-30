
# ⚖️ JudgeLib

**JudgeLib** is a scalable, Redis-backed Node.js library for secure and efficient online code execution. Designed for educational and competitive programming platforms, JudgeLib provides distributed execution, language support, and isolated process handling out of the box.

---

## 📦 Installation

Install JudgeLib in your Node.js project:

```bash
# Using npm
npm install lib-judge

# Using yarn
yarn add lib-judge
```

---

## 🚀 Getting Started

Execute and evaluate code with just a few lines:

### Example (ES Modules)

```js
import { judge } from 'lib-judge';

const result = await judge({
  codePath: '/path/to/temp/file.py',
  ques_name: 'sum of array',
  input: '5 1 2 3 4 5 ### 3 1 2 3 ### 2 1 2',
  output: '15 ### 6 ### 3',
  timeout: 2,           // timeout per test case in seconds
  sizeout: 64,          // max output size in KB
  language: 'py'        // language code: 'py', 'cpp', 'java'
});

console.log(result);
```

---

## 🌐 Supported Languages

| Language | Version | Extension |
| -------- | ------- | --------- |
| Python   | 3.11    | `.py`     |
| Java     | 17      | `.java`   |
| C++      | GCC 11  | `.cpp`    |

---

## ⚙️ How It Works

1. Each submission is split into multiple test cases.
2. Test cases are pushed into a Redis queue.
3. Distributed workers poll the queue and process tasks.
4. Code is compiled (if needed), executed, and validated securely.
5. Results are aggregated and returned.

---

## 📈 Performance Benchmarks

Currently deployed on [Render](https://render.com) with **3 active workers**.

| Metric            | Estimate                                    |
| ----------------- | ------------------------------------------- |
| Uptime            | \~98–99% (managed by Render)                |
| Avg Response Time | ~800–1500ms (0.8–1.5s) per test case (Render)   |
| Executions/Day    | \~20,000–40,000 test cases across 3 workers |

> 🧠 Scaling Plan:
> JudgeLib is designed to scale horizontally. As usage increases, more workers will be added monthly to maintain low latency and high throughput.

> ⚠️ Notes:
> Performance may vary based on code complexity, queue size, and server load.

---

## 🙌 Contributing

We welcome contributions and feedback!

* 🐞 Found a bug? [Open an issue](https://github.com/lightning-sagar/Lib-judge/issues)
* 🚀 Want to improve the library? Submit a pull request.

---

## 📬 Contact

For support or questions, feel free to reach out:

**Email:** [lightningsagar0@gmail.com](mailto:lightningsagar0@gmail.com)

---

Built with ❤️ to support developers, students, and educators in building better code evaluation platforms.

---

