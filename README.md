# Cartão de perfil pessoal cremope.github.io

Este projeto implementa um contador de visitas simples usando a [CounterAPI.dev](https://counterapi.dev/), ideal para páginas estáticas como cartões de perfil pessoal, portfólios ou projetos no GitHub Pages.

## ✅ Pré-requisitos

- Uma conta gratuita no site [https://counterapi.dev](https://counterapi.dev/)
- Um `workspace` e um `counter` criados no painel da CounterAPI
- HTML estático com suporte a JavaScript

---

## 🚀 Como configurar o contador

### 1. Crie seu workspace e contador

1. Acesse [https://counterapi.dev](https://counterapi.dev/)
2. Faça login com GitHub
3. Crie um novo workspace com um identificador (ex: `meu-site`)
4. Crie um novo contador (ex: `visitas-pagina`)
5. Copie os nomes exatamente como criados (`workspace` e `counter slug`)

---

### 2. Adicione os scripts ao HTML

Inclua este script antes do `</body>` do seu HTML:

```html
<!-- Biblioteca CounterAPI -->
<script src="https://cdn.jsdelivr.net/npm/counterapi@1.1.0/dist/counter.browser.min.js"></script>

<!-- Código para incrementar e mostrar as visitas -->
<script>
  const counter = new Counter({ workspace: 'meu-site' }); // substitua pelo seu

  counter.up('visitas-pagina') // substitua pelo nome do contador
    .then(result => {
      document.getElementById('visit-count').innerText = result.data.up_count;
    })
    .catch(err => {
      console.error('Erro ao contar visitas:', err);
      document.getElementById('visit-count').innerText = 'erro';
    });
</script>
