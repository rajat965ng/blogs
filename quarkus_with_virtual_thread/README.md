# Boosting Performance with Quarkus: A Tale of Virtual Threads

In the world of today's internet programs, speed is very important. The way you build your app can make a big difference in how it grows. In this blog post, we will look at a web service app made with Golang. We'll check how fast it works before and after adding virtual threads. Then, I will compare Quarkus to regular web frameworks to see which one is better for us.

## Exploring the Golang Web Service

Before we get into comparing how well they perform, let's learn about the Golang web service and its setup first. The Golang service is a simple "Hello World" app. It uses Fiber, a quick and small web tool for Golang to make things work better. The service is measured using the Bombardier HTTP testing tool, both before and after starting virtual threads.

### Benchmarking Results

#### Before Using Virtual Threads

```bash
bombardier -n 100000 -p i,p,r http://localhost:8080/hello

Statistics        Avg      Stdev        Max
  Reqs/sec      1321.67    2695.53   45642.22
  Latency      110.07ms     3.41ms   153.67ms
  Throughput:   215.01KB/s
```

#### After Using Virtual Threads

```bash
bombardier -n 100000 -p i,p,r http://localhost:8080/hello

Statistics        Avg      Stdev        Max
  Reqs/sec      1217.24    2278.28   30562.03
  Latency      109.65ms     4.48ms   229.89ms
  Throughput:   243.53KB/s
```

### Key Performance Indicators

#### Reqs/sec

- **Before:** 1321.67 requests per second
- **After:** 1217.24 requests per second

#### Latency

- **Before:** Average latency of 110.07ms
- **After:** Average latency of 109.65ms

#### Throughput

- **Before:** 215.01KB/s
- **After:** 243.53KB/s

## Comparing PlatformThreads and VirtualThreads

Quarkus, a Java stack made for Kubernetes, adds the idea of virtual threads. This helps to improve how many things can happen at once without wasting resources. In the code shown, `RunOnVirtualThread` is used to run the `hello` method on a virtual thread.

### Benefits of Virtual Threads

1. **Improved Concurrency:**
    - **PlatformThreads:** Traditional threads can be resource-intensive, leading to scalability challenges. Virtual threads are lightweight and offer efficient concurrency, making it easier to handle a large number of connections.

2. **Reduced Latency:**
    - **PlatformThreads:** Using virtual threads helps reduce switching costs and brings down waiting times compared to old-style threads.

3. **Enhanced Throughput:**
    - **PlatformThreads:** Virtual threads efficiently utilize available resources, leading to improved throughput as seen in the benchmark results.

## Quarkus: A Superior Framework

The Quarkus framework, leveraged in this example, showcases its superiority over traditional frameworks in multiple aspects:

- **Resource Efficiency:Quarkus, which has a native compile and works with GraalVM. It uses less memory and starts up quickly than other Java frameworks.

- **Developer Productivity:Quarkus uses new ways to make software and helps live coding. This means developers can see changes right away without having to restart the app.

- **Cloud-Native Capabilities:Quarkus is made for cloud-based plans, making it great for small parts and programs that use containers.

- **Extension Ecosystem:Quarkus has a big set of extensions that make it easy to add different libraries and services to your app.


## Conclusion

When trying to make a web app work well, picking the right framework and concurrency model is very important. The Golang service, at first using regular threads, showed a lot of changes for speed and time wait after swapping to virtual threads with Quarkus.

The use of online threads makes things work better and also matches today's methods for good use of resources. Quarkus, which pays attention to making things easy for developers and works well with the cloud, is a top choice for building fast and flexible web apps. Look at the given Golang code and think about how good Quarkus can be for your next project. Happy coding!