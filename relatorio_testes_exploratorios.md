# Relatório de Teste Exploratório - James Oliveira

## Propósito da Exploração
Explorar várias funcionalidades do sistema e observar o comportamento da interface, buscando falhas, inconsistências ou pontos de melhoria.

## Detalhes do Sistema / Ambiente
- **Sistema Operacional:** Windows 10 Pro
- **Navegador:** Firefox 91
- **URL do Sistema:** https://the-internet.herokuapp.com

## Data de Início e Término do Teste
- **Início:** 18/04/2025, 20:00
- **Final:** 18/04/2025, 21:20

---

### 1. Checkboxes
**Caminho:** `/checkboxes`

**Testes Realizados:**
- Marcar e desmarcar ambos os checkboxes. ✅ OK
- Observar se o estado persiste ao atualizar a página. ❌ **Falha** – O estado não persiste após a atualização da página (apenas o segundo checkbox permanece marcado).
- Testar acessibilidade (tabulação e uso por teclado). ✅ OK

**Erros:**
- **#123056:** Erro 404 em URLs diferentes da inicial.

**Observações:**
- O comportamento de "resetar" ao atualizar pode ser intencional (por ser uma demo), mas seria uma falha em um sistema real.
- O feedback visual é instantâneo e adequado.

---

### 2. Dropdown
**Caminho:** `/dropdown`

**Testes Realizados:**
- Selecionar “Option 1” e “Option 2”. ✅ OK
- Atualizar a página e verificar se o estado persiste. ❌ **Falha** – O estado não persiste após a atualização da página, voltando ao estado inicial.
- Testar interações por teclado. ✅ OK

**Observações:**
- A falta de persistência do estado após atualização da página pode ser uma falha dependendo do contexto da aplicação.

---

### 3. Inputs
**Caminho:** `/inputs`

**Testes Realizados:**
- Inserir apenas números. ✅ OK
- Inserir letras. ❌ **Não aceito** – As letras não são aceitas no campo de input.
- Inserir caracteres especiais. ❌ **Não aceito** – Caracteres especiais não são aceitos no campo de input.
- Verificar feedback do campo. ❌ **Sem feedback** – Não há feedback visual para entradas inválidas.

**Observações:**
- O sistema não permite caracteres alfabéticos ou especiais, o que pode ser desejado, mas é importante um feedback visual adequado para o usuário.

---

### 4. Add/Remove Elements
**Caminho:** `/add_remove_elements/`

**Testes Realizados:**
- Adicionar vários elementos. ✅ OK
- Remover todos os elementos. ✅ OK
- Verificar limites (se houver). ❓ **Sem limite definido** – Não há limite visível para a adição de elementos.

**Observações:**
- Não há travamento ou limitação ao adicionar muitos elementos, o que pode indicar que o sistema não está implementando um controle de limite.

---

### 5. Broken Images
**Caminho:** `/broken_images`

**Testes Realizados:**
- Verificar carregamento de imagens. ✅ OK
- Identificar imagens quebradas. ✅ **Sim** – Algumas imagens não carregam e exibem o ícone de erro.
- Observar mensagens de erro. ✅ **Sim** – Mensagens de erro são exibidas ao tentar carregar imagens quebradas.

**Observações:**
- O carregamento de imagens é geralmente bem-sucedido, mas imagens quebradas precisam ser tratadas adequadamente com mensagens de erro mais claras ou imagens de fallback.

---

## Conclusões Gerais:
- **Erros de Persistência de Estado:** Algumas funcionalidades como **Checkboxes** e **Dropdown** não mantêm o estado após atualizar a página. Esse comportamento seria inaceitável em um ambiente de produção.
- **Falta de Feedback Visual:** O campo de **Inputs** não fornece feedback adequado para entradas inválidas, o que pode confundir o usuário.
- **Imagens Quebradas:** Algumas imagens não carregam corretamente, mas o sistema exibe mensagens de erro, o que é útil.
- **Controle de Limite Ausente:** A funcionalidade de **Add/Remove Elements** não possui limite claro de adição de elementos, o que pode causar problemas de desempenho em um cenário real.

---

## Estratégia Utilizada:
- Tour de Funcionalidades: Testei cada funcionalidade individualmente, explorando interações do usuário, comportamento do sistema e pontos de falha.

---

## Erros e Questões Detectadas:
- **Erro 404:** Encontrado em URLs diferentes da inicial, o que impede o carregamento correto de alguns recursos.
- **Persistência de Estado:** Algumas funcionalidades não mantêm seu estado após a atualização da página, o que pode ser problemático para o usuário final.
