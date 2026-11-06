# 📏 Performance Benchmark

[![ClawHub Skill](https://img.shields.io/badge/ClawHub-Skill-blue)](https://clawhub.ai/djc00p/performance-benchmark) [![Agent Skill](https://img.shields.io/badge/Agent-Skill-blue)](#) [![Web Vitals](https://img.shields.io/badge/Web-Vitals-4285F4.svg)](https://web.dev/vitals) [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**Performance Benchmark** measures the performance impact of code changes and establishes baselines for your project.

Most performance regressions are invisible in review — the code looks fine, the test suite passes, and the page just got slower. A benchmark baseline turns that into a number you can diff. This skill gives you the measurement discipline and the target thresholds to compare against.

---

## ⚠️ Safety Warning

**Load tests should not be run against production systems without explicit authorization from your team.** Test against staging or local environments only.

---

## 🚀 Quick Start

**Bring your own benchmark tool** — k6 for load testing, autocannon for API benchmarks, hyperfine for build speed.

1. **Run baseline** — `benchmark baseline` captures current metrics
2. **Make changes** to your code
3. **Run comparison** — `benchmark compare` measures impact against the baseline
4. **Review the report** — tracks deltas for Web Vitals, bundle size, build time, and API latency

---

## 📊 Key Concepts

* **Page Performance** — Core Web Vitals (LCP, CLS, INP, TTFB) and resource sizes
* **API Performance** — p50/p95/p99 latency under load
* **Build Performance** — cold build, hot reload (HMR), test suite, type-check, lint times
* **Before/After** — compare metrics against the stored baseline to detect regressions

---

## 🎯 Page Performance Metrics

Measured on a real browser:

| Metric | Target |
|--------|--------|
| **LCP** (Largest Contentful Paint) | < 2.5s |
| **CLS** (Cumulative Layout Shift) | < 0.1 |
| **INP** (Interaction to Next Paint) | < 200ms |
| **TTFB** (Time to First Byte) | < 800ms |
| Total page weight | < 1MB |
| JS bundle | < 200KB gzipped |
| Network requests count | — |

---

## ⚡ API Performance

```text
Hit each endpoint 100 times:
- p50, p95, p99 latency
- Response size, status codes
- Load test: 10 concurrent requests
- Compare against SLA targets
```

The median hides the tail. **p95 and p99 are where your users actually live** — a p50 of 40ms with a p99 of 4 seconds is a service that feels broken for one in every hundred requests.

---

## 🏗️ Build Performance

Measures the development feedback loop — the thing engineers feel most:

```text
- Cold build time
- Hot reload time (HMR)
- Test suite duration
- TypeScript check time
```

A slow feedback loop doesn't just cost time; it changes how people work. When a check takes 90 seconds, people batch their changes instead of iterating.

---

## 🔁 Regression Detection

The point of a baseline is the diff. A benchmark report surfaces:

* Which metric moved
* By how much (absolute and percentage)
* Whether it crossed a target threshold
* Which change correlates with the shift

Store baselines alongside the code so they're diffable across branches and reviews.

---

## 📚 References

* `references/metrics.md` — metric definitions, targets, and how to interpret each
* `references/tooling.md` — k6, autocannon, hyperfine, and browser-based measurement setup
* `references/reporting.md` — baseline storage format and report templates

---

**Published by [@djc00p](https://github.com/djc00p)**
