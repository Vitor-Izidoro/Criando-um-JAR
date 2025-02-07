## 🚀 Como Criar um JAR Personalizado no Eclipse

Se você precisa modificar o MOA ou criar um novo classificador, pode gerar um **JAR customizado** com suas próprias classes.  

---

### 📌 **1️⃣ Configurar o Projeto no Eclipse**
Se ainda não tiver um projeto do MOA no Eclipse, siga estes passos:

1. **Importe o código-fonte do MOA**  
   - Baixe o MOA do [GitHub](https://github.com/Waikato/moa).  
   - Recomendo seguir o seguinte tutorial: [instalação-do-MOA](https://github.com/Vitor-Izidoro/JAR-s-no-MOA-um-tutorial-basico).

2. **Adicione ou Modifique Classes**  
   - Exemplo: Se quiser adicionar `InstanceSelectedClassifier3`, crie um arquivo `.java` dentro do pacote `moa.classifiers.drift`.
   - Se precisar de bibliotecas externas, adicione os JARs ao **Build Path**:
     - **Clique com o botão direito no projeto > Build Path > Configure Build Path > Libraries > Add External JARs**.

---

### ⚙ **2️⃣ Gerar o JAR Personalizado**
Após fazer suas modificações, gere um JAR seguindo estes passos:

1. **Clique com o botão direito no projeto** > **Export...**  
2. Escolha **Java > Runnable JAR file** (para um JAR executável) ou **JAR file** (para uma biblioteca).  
3. No campo **Launch Configuration**, escolha a classe principal do MOA (`moa.DoTask`).  
4. Defina um nome para o arquivo (exemplo: `moaCustom.jar`) e escolha onde salvá-lo.  
5. Clique em **Finish**.  

---

### 🏗 **3️⃣ Testar o Novo JAR no CMD**
Depois de criar seu JAR, teste se ele funciona corretamente:

```bash
java -cp "moaCustom.jar" moa.DoTask "EvaluatePrequential -l (meta.OzaBag -l (drift.InstanceSelectedClassifier3)) -s (ArffFileStream -f dataset.arff) -e BasicClassificationPerformanceEvaluator -f 10000 -q 5000"
