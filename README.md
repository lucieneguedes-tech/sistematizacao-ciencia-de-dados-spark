# Sistematização em Ciência de Dados II Pyspark
Projeto prático desenvolvido no ecossistema distribuído Apache (Pyspark) no ambiente Google Colab, com foco na análise preditiva e estratificação de risco de diabetes mellitus a partir de dados populacionais do BRFSS 2015. 

## Estrutura do Pipeline

1.**Configuração e Ingestão:** Inicialização do SparkSession e leitura com inferência de tipos.

2.**Tratamento Engenharia de Atributos:**

   -Remoção de valores nulos e duplicatas completas (redução de 253.680 para 229.474 registros limpos).
   
   -Criação da variável combinada 'Risco Cardiovascular' (Hipertensão + Colesterol).
   
3.**Análise Exploratória (Spark SQL):**

   -Prevalência de diabetes na amostra: 15,29%.
   
   -Associação direta de IMC elevado e comorbidades cardiovasculares com o aumento da prevalência.
   
4.**Modelagem Preditiva Supervisionada:**

   -**Regressão Logística:** AUC-ROC= 0,8059 | Acurácia= 85,04% | F1-Score= 0,8114 (Modelo vencedor).
   
   -**Random Forest:** AUC-ROC= 0,8002 | Acurácia= 85,05% | F1-Score= 0,7956.
   
5.**Modelagem Descritiva / Clusterização (K-Means com k=3:**

   -**Cluster 1 (Baixo Risco):** População jovem/adulta. hábitos preservados, taxa de 4,61%.
   
   -**Cluster 0 (Risco Moderado):** Idosos funcionais com boa autonomia física, taxa de 17,93%.
   
   -**Cluster 2 (Alto Risco):** Indivíduos com obesidade e elevado número de dias com limitações físicas graves, taxa de 29,34%.

    
