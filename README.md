# 🤖 Automação de Cadastro de Produtos em ERP
 
Robô em Python que automatiza o cadastro de produtos em um sistema ERP, preenchendo formulários automaticamente a partir de uma planilha Excel — usando **reconhecimento de imagem na tela**, não integração via API/HTML.
 
## 📌 Sobre o projeto
 
Sistemas ERP corporativos (como SAP e TOTVS) costumam ter cadastros de produtos manuais e repetitivos, campo por campo. Este projeto simula esse cenário usando o **Fakturama**, um ERP open-source de faturamento — importante deixar claro que é uma ferramenta de escala bem menor que SAP/TOTVS, usada aqui como ambiente de teste acessível para reproduzir o mesmo *padrão* de automação que se aplicaria a sistemas maiores.
 
A técnica usada (reconhecimento visual via `pyautogui.locateOnScreen`) é especialmente útil em sistemas legados ou desktop que não oferecem API — o robô "enxerga" a tela como um humano enxergaria, localizando botões e campos por imagem.
 
## ⚙️ O que o robô faz
 
1. Abre o ERP automaticamente (`subprocess`)
2. Localiza elementos na tela por reconhecimento de imagem (`pyautogui.locateOnScreen`)
3. Lê a base de produtos de uma planilha Excel (`pandas`)
4. Para cada produto, preenche automaticamente todos os campos do formulário: ID, nome, categoria, GTIN, fornecedor, descrição, preço, custo e estoque
5. Localiza e seleciona a imagem correspondente ao produto
6. Salva o cadastro e repete o processo até o fim da planilha
## 🛠️ Tecnologias utilizadas
 
- **Python**
- **PyAutoGUI** — automação de mouse/teclado e reconhecimento de imagem
- **Pyperclip** — manipulação da área de transferência para preenchimento de texto
- **Pandas** — leitura e manipulação da base de produtos (Excel)
- **Subprocess** — abertura automática do ERP
## 📂 Estrutura do repositório
 
```
├── main.ipynb              # Notebook com o script principal
├── Imagens Produtos/        # Fotos dos produtos usadas no cadastro
├── fakturama.png            # Imagens de referência para reconhecimento visual
├── new.png
├── new_product.png
├── number_item.png
├── salvar.png
├── selecionar_imagem.png
└── LICENSE
```
 
## ▶️ Como executar
 
1. Tenha o [Fakturama](https://fakturama.info/) instalado
2. Instale as dependências:
```bash
   pip install pyautogui pyperclip pandas
```
3. Ajuste o caminho do executável do ERP e da planilha `Produtos.xlsx` conforme seu ambiente
4. Execute o notebook `main.ipynb`
> ⚠️ Por usar reconhecimento de imagem, a resolução de tela e o layout do ERP precisam ser os mesmos usados nas imagens de referência do repositório.
>
> ## 👤 Autor
**Vinicius Cavalcanti Vilela Lins**  
[LinkedIn](https://linkedin.com/in/vinicius-cavalcanti-si) |
[GitHub](https://github.com/ViniciusCavalcanti-03) | 
[E-mail](https://mail.google.com/mail/?view=cm&fs=1&to=viniciuscavalcanti.dev@gmail.com)
