# Predicao-de-doacoes-Campanha-USP-do-Agasalho

Projeto feito para a disciplina de Inteligência Artificial SCC 0530 ministrada pela professora doutora Solange Oliveira Rezende.

Esse trabalho buscava aplicar em algum problema, as técnicas de aprendizado de máquina vistas na disciplina.

Como a grande maioria dos membros do grupo participava do grupo de extensão da Campanha USP do Agasalho, escolhemos um problema relacionado à Campanha, predição de doações.

![Símbolo da Campanha](https://github.com/user-attachments/assets/c3cf4321-0243-4853-aae3-062aa318715d)

O grupo possui mais de 100 caixas de doações espalhadas pela região de São Carlos, e ter ao menos uma luz de quais caixas iriam necessitar ser recolhidas em breve seria de grande ajuda para a logística do grupo.

Diante desse desafio, exploramos os dados de arrecadações passadas da Campanha para elaborar um dataset contendo as séries temporais das arrecadação dos últimos 18 meses, e trabalhar com esses dados para realizar predições.

Foi uma experiência enriquecedora, na qual descobrimos não só a importância dos dados, mas também das dificuldades em adquiri-los e processá-los para que eeles tenham uma boa qualidade.

O código desenvolvido pode ser encontrado no colab presente neste git, mas uma explicação mais detalhada também pode ser encontrada abaixo.

##Modelagem

Primeiramente, obtemos os dados minerando mais de 200 planilhas contendo o histórico das lotações das caixas. Aqui uma das maiores dificuldades, além do trabalho manual, foi lidar com as diferentes anotações dos dados. ![Foto de uma das planilhas](https://github.com/user-attachments/assets/7cbf4683-84ee-4727-9790-3bc843c0629f)


Com os dados de cada caixa organizado em um dicionário, geramos séries temporais para as doações recebidas em uma caixa pelo tempo e fizemos um pequeno tratamento, descartando caixas que tiveram apenas um ou menos doações recebidas.
![Exemplo de uma série temporal](https://github.com/user-attachments/assets/b8a5bfa3-24a0-47d5-a363-77ea28915d06)


Em seguida, obfuscamos o último mês de arrecadação das caixas, nosso target seria prever se houve ou não mais arrecadação nesse último mês

Com as séries em mãos, utilizamos o catch 22 para extrair características das séries e obttermos dados tabulares para utilizar os algoritmos que vimos na disciplinas. Aplicamos esses algoritmos (KNN , árvore de decisão e random forest) e analisamos os resultados observando a acurácia, precisão e sensibilidade.

Pelo que observamos, o KNN obteve um desempenho inferior aos outros, mas conseguia identificar a maioria das caixas que não iam encher (especifidade bem alta, mas sensibilidade nem tanto), acreditamos que devido à certo desbalanceamento dos nossos dados (40% a 60%).

Já a árvore de decisão e random Forest tiveram desempenhos semelhantes, com accurácia acima de 0,8 e sensibilidade um poucco menor do que a especificidade.

Agradecimento à professora pelo conhecimento e oportunidade.

 # Membros do grupo

Angela Patricia Mestas Muñante
Artur de Vlieger Lima  		
Bruna Pereira Serrano da Mata
Gabriel Henrique dos Santos
Ítalo de Matos Saldanha			
Lucas Pereira Franco de Almeida	
Pedro Henrique Cruz da Silva
