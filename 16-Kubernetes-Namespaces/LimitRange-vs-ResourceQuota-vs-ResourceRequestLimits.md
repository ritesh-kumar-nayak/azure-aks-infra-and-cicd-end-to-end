| Aspect                   | **Requests & Limits (Pod / Container)** | **LimitRange (Namespace)**    | **ResourceQuota (Namespace)** |
| ------------------------ | --------------------------------------- | ----------------------------- | ----------------------------- |
| Scope                    | Single container / pod                  | Policy per namespace          | Total namespace budget        |
| Defined by               | App team                                | Platform / cluster admin      | Platform / cluster admin      |
| Purpose                  | Declare workload needs                  | Enforce per-object boundaries | Enforce total consumption     |
| Controls totals          | ❌ No                                    | ❌ No                          | ✅ Yes                         |
| Controls min/max         | ❌ No                                    | ✅ Yes                         | ❌ No                          |
| Injects defaults         | ❌ No                                    | ✅ Yes                         | ❌ No                          |
| Rejects pod creation     | ❌ No                                    | ✅ Yes                         | ✅ Yes                         |
| Affects scheduling       | ✅ Directly                              | Indirectly                    | Indirectly                    |
| Prevents noisy neighbors | ❌ Limited                               | ⚠️ Partial                    | ✅ Strong                      |
| Common misuse            | Missing limits                          | Wrong scope                   | Used without LimitRange       |
