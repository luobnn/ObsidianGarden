强化学习的目标是求得 $\theta^*=\arg\max_\theta J(\theta)=\arg\max_\theta E_{\tau\sim p_\theta(\tau)}[\sum_tr(s_t, a_t)]$

完成此优化目标，需要求解 $J(\theta)$的梯度： $$\nabla_\theta J(\theta) = \int \nabla_\theta p_\theta(\tau)r(\tau)dx = \int p_\theta(\tau)\nabla_\theta \log p_\theta(\tau)r(\tau)d\tau = E_{\tau\sim p_\theta(\tau)}[\nabla_\theta \log p_\theta(\tau)r(\tau)]$$

而有 $\nabla_\theta \log p_\theta(\tau)=\nabla_\theta[\log p(s_1)+\sum_{t=1}^T[\log\pi_\theta(a_t|s_t)+\log p(s_{t+1}|s_t,a_t)]]$

首项和求和式中后面的那项是和 $\theta$无关的，故有 $\nabla_\theta \log p_\theta(\tau)=\sum_{t=1}^T\nabla_\theta\log\pi_\theta(a_t|s_t)$

故有 $$\nabla_\theta J(\theta) = E_{\tau\sim p_\theta(\tau)}[\nabla_\theta \log p_\theta(\tau)r(\tau)] = E_{\tau\sim p_\theta(\tau)}[(\sum_{t=1}^T\nabla_\theta\log\pi_\theta(a_t|s_t))(\sum_{t=1}^Tr(s_t,a_t))]$$

通常情况下，environment 的分布 $p_\theta(\tau)$对我们来说是未知的，要进行采样 N 次 sampling 去拟合
