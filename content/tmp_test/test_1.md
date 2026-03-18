
故有 $$\nabla_\theta J(\theta) = E_{\tau\sim p_\theta(\tau)}[\nabla_\theta \log p_\theta(\tau)r(\tau)] = E_{\tau\sim p_\theta(\tau)}[(\sum_{t=1}^T\nabla_\theta\log\pi_\theta(a_t|s_t))(\sum_{t=1}^Tr(s_t,a_t))]$$

通常情况下，environment 的分布 $p_\theta(\tau)$对我们来说是未知的，要进行采样 N 次 sampling 去拟合

测试修改
![[test_1-1773860570015.png]]


