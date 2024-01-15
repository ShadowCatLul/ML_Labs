# LR1
## Выбранные функции оптимизации:
### Изома
#### f(x, y) = -cos(x) cos(y) e(-((x-pi)^2 + (y-pi)^2))
    class Easom():
      @staticmethod
      def calc(x1, x2):
          return -(np.cos(x1)*np.cos(x2))*np.exp(-((x1-math.pi)**2+(x2-math.pi)**2))
  
      @staticmethod
      def dx(x, y):
          return math.e**((-x**2)-y**2-2*math.pi**2)*(np.cos(y)*math.e**(2*math.pi*x+2*math.pi*y)*np.sin(x)+(2*math.e**(2*math.pi*y)*np.cos(y)*x+(math.e**(2*math.pi*y)*np.sin(y)+(2*y-2*math.pi)*math.e**(2*math.pi*y)*np.cos(y))-2*math.pi*math.e**(2*math.pi*y)*np.cos(y))*math.e**(2*math.pi*x)*np.cos(x))
      @staticmethod
      def dy(x, y):
          return math.e**((-x**2)-y**2-2*math.pi**2)*((np.cos(y)*math.e**(2*math.pi*x+2*math.pi*y)*np.sin(x)+(2*math.e**(2*math.pi*y)*np.cos(y)*x-2*math.pi*math.e**(2*math.pi*y)*np.cos(y))*math.e**(2*math.pi*x)*np.cos(x))+(math.e**(2*math.pi*y)*np.sin(y)+(2*y-2*math.pi)*math.e**(2*math.pi*y)*np.cos(y))*math.e**(2*math.pi*x)*np.cos(x))
      
      @staticmethod
      def glob_min():
          return np.array([math.pi,math.pi,-1])
  
      @staticmethod
      def boundaries():
          #domain =  np.array([[-100, 100], [-100, 100]])
          domain =  np.array([[-0, 5], [-0, 5]])
          return(domain)

### Бута
#### f(x, y) = (x + 2y - 7)^2 + (2x + y -5)^2
  
    class Booth():
      @staticmethod
      def calc(x, y):
          return (x + 2*y -7)**2 + (2*x + y - 5)**2
  
      @staticmethod
      def dx(x, y):
          return 6*x;
      
      @staticmethod
      def dy(x, y):
          return 6*y;
      
      @staticmethod
      def glob_min():
          return np.array([1,3,0])
          
      @staticmethod
      def boundaries():
          domain =  np.array([[-10, 10], [-10, 10]])
          return domain



## Градиенты
### Классический
#### Для Изома
![image](https://github.com/ShadowCatLul/ML_Labs/assets/64269779/4671d340-ff8d-4e95-8ff2-5cebd6950fe5)

##### Функцию оптимизации Изома считаю бесполезным считать далее, т.к. при любом из градиентных методов функция останется в локальном минимуме - f(x, y) = 0
#### Для Бута
![image](https://github.com/ShadowCatLul/ML_Labs/assets/64269779/ef460e55-7b25-4386-b28a-5ba5dd79cb52)

### Моментный
![image](https://github.com/ShadowCatLul/ML_Labs/assets/64269779/7def71f0-51b8-4af2-8e2a-6bcc7d2059c8)

### Адаптивный
![image](https://github.com/ShadowCatLul/ML_Labs/assets/64269779/2edb48b1-d063-4d04-b435-16aa1516a631)

#LR2
| Функция | Метод | МАЕ |
| ----- | ----------- |---------- |
| Изома | DE          | 0.000007  |
| Изома | SADE        | 0.0000054 |
| Изома | Bee_colony  |  0.000006 |
| Бута  | DE          | 0.0000006 |
| Бута  | SADE        | 0.0000005 |
| Бута  | Bee_colony  | 0.00000055|

