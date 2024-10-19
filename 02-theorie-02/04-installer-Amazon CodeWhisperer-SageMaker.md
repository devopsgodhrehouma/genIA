#### Étapes et commandes nécessaires pour installer **Amazon CodeWhisperer** dans notre environnement SageMaker Studio :

1. Activez l'environnement **studio** :
   ```bash
   conda activate studio
   ```

2. Installez l'extension **CodeWhisperer** pour JupyterLab :
   ```bash
   pip install amazon-codewhisperer-jupyterlab-ext
   ```

3. Activez l'extension dans Jupyter :
   ```bash
   jupyter server extension enable amazon_codewhisperer_jupyterlab_ext
   ```

4. Redémarrez le serveur Jupyter pour appliquer les modifications :
   ```bash
   restart-jupyter-server
   ```

Ces étapes devraient installer et activer **Amazon CodeWhisperer** dans votre environnement SageMaker Studio.
