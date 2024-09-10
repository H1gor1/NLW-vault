
NPX = comando do node para iniciar um script de alguma biblioteca instalado, no nosso caso "npx tsc --init";

Framework utilizado: fastify

Promisse: no js indica algo que pode demorar um pouco para executar

BiomeJS: "concorrente" do ESLint

Drizzle: ORM que será utilizada, usando migrations


---
Criaçao de tabela com drizzle:

após todas as configurações do drizzle partimos para a criação de uma tabela no banco de dados:

```
import { pgTable, text, integer, timestamp } from 'drizzle-orm/pg-core'

export const goals = pgTable('goals', {
  id: text('id').primaryKey(),
  title: text('title').notNull(),
  desiredWeeklyFrequency: integer('desired_weekly_frequency').notNull(),
  createdAt: timestamp('created_at', { withTimezone: true })
    .notNull()
    .defaultNow(),
})
```

serão necessárias 4 rotas:

1 para cadastrar meta
1 para marcar como concluida
1 para retornar os dados da semana
1 para retornar as metas da semana
