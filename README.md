- 👋 Hi, I’m @KmZ153
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
KmZ153/KmZ153 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
import random

def jogar_roleta():
    numeros = list(range(0, 37))
    cor = ['vermelho', 'preto']
    
    numero_sorteado = random.choice(numeros)
    cor_sorteada = random.choice(cor)
    
    return numero_sorteado, cor_sorteada

def analisar_ultimos_resultados(n):
    resultados = []
    for _ in range(n):
        numero, cor = jogar_roleta()
        resultados.append(numero)
    
    return resultados

def calcular_estatisticas(resultados):
    total = len(resultados)
    numeros = {}
    
    for numero in resultados:
        if numero in numeros:
            numeros[numero] += 1
        else:
            numeros[numero] = 1
    
    percentual_numeros = {numero: (ocorrencias / total) * 100 for numero, ocorrencias in numeros.items()}
    
    return percentual_numeros

# Exemplo de uso
num_jogadas = 500
resultados = analisar_ultimos_resultados(num_jogadas)
percentual_numeros = calcular_estatisticas(resultados)

print(f"Análise dos últimos {num_jogadas} números sorteados:")
print("Número\t\tPercentual")
for numero, percentual in percentual_numeros.items():
    print(f"{numero}\t\t{percentual:.2f}%")
