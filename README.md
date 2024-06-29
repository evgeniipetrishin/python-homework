# python-homework 
Задача
"""
Задача 44: В ячейке ниже представлен код генерирующий DataFrame, которая состоит всего из 1 столбца. Ваша задача перевести его в one hot вид. Сможете ли вы это сделать без get_dummies?

Решение

import random
lst = ['robot'] * 10
lst += ['human'] * 10
random.shuffle(lst)
data = pd.DataFrame({'whoAmI':lst})
data.head()
""" 
lst = ['robot'] * 10
lst += ['human'] * 10
random.shuffle(lst)
data = pd.DataFrame({'whoAmI': lst})

one_hot_encoded = pd.get_dummies(data['whoAmI'])
data = pd.concat([data, one_hot_encoded], axis=1)
data = data.drop('whoAmI', axis=1)

data.head() 
