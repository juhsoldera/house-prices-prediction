# Meus testes:
**Código Inicial:**
<br>mean_squared_log_error: 0.36863123769592315
<br>
<br>**Teste 1:**
<br>A partir do código inicial, alterado o número de neurônios do Hidden Layer 1 de 100 para 1.000:
<br>**De**: hid1 = tfk.layers.Dense(100, activation='relu')(inp)
<br>**Para**: hid1 = tfk.layers.Dense(1000, activation='relu')(inp)
<br>mean_squared_log_error = 0.22658296318960403
<br>
<br>**Teste 2:**
<br>A partir do código inicial, inserido mais um Hidden Layer na rede:
<br>**De**: 
<br>inp = tfk.layers.Input((Xtr.shape[1], ))
<br>hid1 = tfk.layers.Dense(100, activation='relu')(inp)
<br>drop = tfk.layers.Dropout(0.5)(hid1)
<br>hid2 = tfk.layers.Dense(18, activation='relu')(drop)
<br>out = tfk.layers.Dense(1, activation='relu')(hid2)
<br>**Para**:
<br>inp = tfk.layers.Input((Xtr.shape[1], ))
<br>hid1 = tfk.layers.Dense(100, activation='relu')(inp)
<br>hid3 = tfk.layers.Dense(100, activation='relu')(hid1)
<br>drop = tfk.layers.Dropout(0.5)(hid3)
<br>hid2 = tfk.layers.Dense(18, activation='relu')(drop)
<br>out = tfk.layers.Dense(1, activation='relu')(hid2)
<br>0.29149641306532803
<br>
<br>**Teste 3:**
<br>Fazendo um merge das técnicas do Teste1 e do Teste 2:
<br>inp = tfk.layers.Input((Xtr.shape[1], ))
<br>hid1 = tfk.layers.Dense(1000, activation='relu')(inp)
<br>hid3 = tfk.layers.Dense(1000, activation='relu')(hid1)
<br>drop = tfk.layers.Dropout(0.5)(hid3)
<br>hid2 = tfk.layers.Dense(18, activation='relu')(drop)
<br>out = tfk.layers.Dense(1, activation='relu')(hid2)
<br>mean_squared_log_error = 0.25170281710681797
<br>
<br>**Teste 4:**
<br>A partir da solução do Teste 1, alterado o parâmetro do Dropout:
<br>**De**: drop = tfk.layers.Dropout(0.5)(hid1)
<br>**Para**: drop = tfk.layers.Dropout(0.8)(hid1)
<br>mean_squared_log_error = 0.23666346866048116
<br>
<br>
<br>**MELHOR SOLUÇÃO: Teste 1.**
