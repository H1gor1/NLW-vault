
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


