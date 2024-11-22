# Curso de Composer: Gerenciador de Dependências para PHP

Este README documenta os principais conceitos e comandos aprendidos durante o curso de **Composer**, abordando desde a configuração inicial até o uso avançado do gerenciador de dependências para PHP.

## O que é o Composer?

O **Composer** é um gerenciador de dependências para projetos PHP. Ele permite:
- Gerenciar bibliotecas e pacotes de forma centralizada.
- Automatizar a instalação e atualização de dependências.
- Manter controle das versões instaladas.

## 📂 Estrutura de Arquivos Gerenciados pelo Composer
- **`composer.json`**: Contém meta-informações sobre as dependências do projeto.
- **`composer.lock`**: Registra as versões exatas das dependências instaladas.
- **`/vendor`**: Pasta onde as dependências e seus arquivos são armazenados.
- **`vendor/autoload.php`**: Arquivo para carregamento automático das dependências.

## 🛠️ Comandos Essenciais

### Inicialização
- **`composer init`**: Cria o arquivo `composer.json`.
- **`composer require <vendor>/<pacote>`**: Adiciona dependências ao projeto e atualiza automaticamente o `composer.json`.
- **`composer install`**: Instala as dependências listadas no `composer.lock` (ou `composer.json`, caso o `.lock` não exista).
- **`composer update`**: Atualiza todas as dependências para suas versões mais recentes, respeitando as restrições de versão do `composer.json`.

### Repositórios
- **Packagist**: Repositório oficial de pacotes do Composer ([packagist.org](https://packagist.org/)).
- Repositórios personalizados: É possível configurar fontes alternativas, como GitHub ou arquivos `.zip`.

### Dependências e Modos de Instalação
- **Dependências globais**: Gerenciadas com o comando `global`.
- **Dependências transitivas**: Automaticamente incluídas com base nas dependências principais.
- **Modo de desenvolvimento (`--dev`)**: Dependências para desenvolvimento que não serão usadas em produção. Exemplo: `composer require --dev phpunit`.

## 🚀 PSR-4 e Autoload
O Composer suporta o padrão **PSR-4**, que define a estrutura de namespaces para carregamento automático de classes.

- **Configuração no `composer.json`**:
  ```json
  "autoload": {
    "psr-4": {
      "Vendor\\Namespace\\": "src/"
    }
  }
