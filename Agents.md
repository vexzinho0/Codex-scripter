# AGENTS.md

## Projeto
Scripts e exploits para Roblox, escritos em Lua/Luau.

## Stack
- Linguagem: Lua / Luau
- Ambiente: Roblox (executor de exploits)
- Sem gerenciador de pacotes formal (scripts soltos ou módulos `.lua`/`.luau`)

## Estrutura
- `scripts/` — scripts principais
- `modules/` — módulos reutilizáveis
- `ui/` — interfaces (ex: Rayfield, Kavo, Orion)
- `utils/` — funções auxiliares

## Convenções
- Usar Luau com tipagem quando possível (`--!strict` ou `--!nonstrict`)
- Nomes de variáveis e funções em `camelCase`
- Constantes em `UPPER_SNAKE_CASE`
- Comentários em português
- Preferir `task.wait()` em vez de `wait()`
- Preferir `task.spawn()` em vez de `spawn()`
- Preferir `task.delay()` em vez de `delay()`
- Usar `pcall` para operações que podem falhar
- Evitar `while true do end` sem `task.wait()`

## Regras Críticas (NUNCA)
- Nunca usar `loadstring` sem necessidade explícita
- Nunca hardcodar webhooks, tokens ou chaves de API
- Nunca remover proteções de outros scripts sem pedido explícito
- Nunca usar loops infinitos sem yield
- Nunca assumir que uma função do executor existe sem checar (`if typeof(f) == "function"`)

## Compatibilidade
- Checar funções do executor antes de usar (`getgenv`, `hookfunction`, `getrawmetatable`, etc.)
- Preferir APIs universais quando possível
- Declarar suporte apenas ao executor alvo, se houver

## Fluxo de Trabalho
1. Ler o script inteiro antes de modificar
2. Manter compatibilidade com a UI existente
3. Testar lógica em ambiente seguro antes de entregar
4. Reportar mudanças de comportamento não solicitadas
