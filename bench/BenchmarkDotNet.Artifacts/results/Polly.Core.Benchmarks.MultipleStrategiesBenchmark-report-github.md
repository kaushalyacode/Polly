``` ini

BenchmarkDotNet=v0.13.5, OS=Windows 11 (10.0.22621.1848/22H2/2022Update/SunValley2), VM=Hyper-V
Intel Xeon Platinum 8370C CPU 2.80GHz, 1 CPU, 16 logical and 8 physical cores
.NET SDK=7.0.304
  [Host] : .NET 7.0.7 (7.0.723.27404), X64 RyuJIT AVX2

Job=MediumRun  Toolchain=InProcessEmitToolchain  IterationCount=15  
LaunchCount=2  WarmupCount=10  

```
|                               Method |     Mean |     Error |    StdDev | Ratio |   Gen0 | Allocated | Alloc Ratio |
|------------------------------------- |---------:|----------:|----------:|------:|-------:|----------:|------------:|
|           ExecuteStrategyPipeline_V7 | 2.269 μs | 0.0136 μs | 0.0204 μs |  1.00 | 0.1106 |    2824 B |        1.00 |
|           ExecuteStrategyPipeline_V8 | 1.861 μs | 0.0111 μs | 0.0155 μs |  0.82 |      - |      40 B |        0.01 |
| ExecuteStrategyPipeline_Telemetry_V8 | 2.402 μs | 0.0104 μs | 0.0156 μs |  1.06 |      - |      40 B |        0.01 |