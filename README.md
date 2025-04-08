# gradle-performance-suite
Performance profiling suite for Gradle builds using Gradle Profiler
# Gradle Performance Profiling Suite

A lightweight suite for benchmarking Gradle build performance, especially around Configuration Cache and configuration time. This suite is part of my application for the **Google Summer of Code (GSoC) 2025** project focused on **Improving Configuration Cache** in Gradle.

##  Structure

- `sample-java/`: A basic Java project to test Gradle performance.
- `scenarios/`: Contains `.profiler` files used by [Gradle Profiler](https://github.com/gradle/gradle-profiler).
- `results/`: Output directory for benchmark results.

##  How to Run

1. Install [Gradle Profiler](https://github.com/gradle/gradle-profiler).
2. Run the profiler:

```bash
gradle-profiler \
  --scenario-file scenarios/config-cache-test.profiler \
  --project-dir sample-java \
  --output-dir results
Analyze the CSV output in results/.

📈 What It Measures
Configuration Time

Build Execution Time

Configuration Cache Reuse

🧹 Clean Builds (Cold)
To simulate cold builds, delete .gradle/ and build/ directories before running:
rm -rf sample-java/.gradle sample-java/build

📜 GSoC 2025 Project
This suite is developed as part of my Google Summer of Code (GSoC) 2025 application. The project focuses on improving Configuration Cache in Gradle, with an emphasis on reducing lock contention and enhancing cache reuse. The suite helps measure and optimize Gradle's configuration performance, a crucial part of my GSoC proposal.

