# BlackAndScholes
```python
class blackAndScholes:
    def __init__(self, S, K, r, sigma, T):
        self.S = S
        self.K = K
        self.r = r
        self.sigma = sigma
        self.T = T
    def call(self):
        d1 = (np.log(self.S / self.K) + (self.r + self.sigma ** 2 / 2) * self.T) / (self.sigma * np.sqrt(self.T))
        d2 = d1 - self.sigma * np.sqrt(self.T)
        call = self.S * norm.cdf(d1) - self.K * np.exp(-self.r * self.T) * norm.cdf(d2)
        return call
    def put(self):
        d1 = (np.log(self.S / self.K) + (self.r + self.sigma ** 2 / 2) * self.T) / (self.sigma * np.sqrt(self.T))
        d2 = d1 - self.sigma * np.sqrt(self.T)
        put = self.K * np.exp(-self.r * self.T) * norm.cdf(-d2) - self.S * norm.cdf(-d1)
        return put
    def delta(self):
        d1 = (np.log(self.S / self.K) + (self.r + self.sigma ** 2 / 2) * self.T) / (self.sigma * np.sqrt(self.T))
        delta = norm.cdf(d1)
        return delta
    def gamma(self):
        d1 = (np.log(self.S / self.K) + (self.r + self.sigma ** 2 / 2) * self.T) / (self.sigma * np.sqrt(self.T))
        gamma = norm.pdf(d1) / (self.S * self.sigma * np.sqrt(self.T))
        return gamma
    def vega(self):
        d1 = (np.log(self.S / self.K) + (self.r + self.sigma ** 2 / 2) * self.T) / (self.sigma * np.sqrt(self.T))
        vega = self.S * norm.pdf(d1) * np.sqrt(self.T)
        return vega
    def theta(self):
        d1 = (np.log(self.S / self.K) + (self.r + self.sigma ** 2 / 2) * self.T) / (self.sigma * np.sqrt(self.T))
        d2 = d1 - self.sigma * np.sqrt(self.T)
        theta = -self.S * norm.pdf(d1) * self.sigma / (2 * np.sqrt(self.T)) - self.r * self.K * np.exp(-self.r * self.T) * norm.cdf(d2)
        return theta
    def rho(self):
        d1 = (np.log(self.S / self.K) + (self.r + self.sigma ** 2 / 2) * self.T) / (self.sigma * np.sqrt(self.T))
        rho = self.K * self.T * np.exp(-self.r * self.T) * norm.cdf(d1)
        return rho

#TEST
if __name__ == '__main__':
    import numpy as np
    from scipy.stats import norm
    import seaborn as sns
    sns.set()
    S = 100
    K = 100
    r = 0.05
    sigma = 0.2
    T = 1
    call = blackAndScholes(S, K, r, sigma, T)
    print(call.call())
    print(call.put())
    print(call.delta())
    print(call.gamma())
    print(call.vega())
    print(call.theta())
    print(call.rho())
    print(call.vega())
    S = 100
    K = 100
    r = 0.05
    sigma = 0.2
    T = 1
    call = blackAndScholes(S, K, r, sigma, T)
    print(call.call())
    print(call.put())
    print(call.delta())
    print(call.gamma())
    print(call.vega())
    print(call.theta())
    print(call.rho())
    print(call.vega())
    S = 100
    K = 100
    r = 0.05
    sigma = 0.2
    T = 1
    call = blackAndScholes(S, K, r, sigma, T)
    print(call.call())
    print(call.put())
    print(call.delta())
    print(call.gamma())
    print(call.vega())
    print(call.theta())
    print(call.rho())
    print(call.vega())
```
