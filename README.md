# AutoTable — Claude Code Plugin

AI coding assistant skill for [AutoTable](https://github.com/dromara/auto-table), a JDBC-based automatic database table structure maintenance framework for Java.

## What's Inside

A comprehensive skill covering:

- **29 annotations** — `@AutoTable`, `@AutoColumn`, `@PrimaryKey`, `@Index`, `@TableIndex`, MySQL-specific (`@MysqlEngine`, `@MysqlFullTextIndex`, etc.), Doris-specific (`@DorisTable`, `@DorisColumn`, etc.)
- **9 database dialects** — MySQL, PostgreSQL, Oracle, SQLite, H2, Doris, DM (达梦), KingBase (人大金仓), MariaDB
- **10 lifecycle callbacks + 4 interceptors** — full execution control
- **SPI extension points** — custom strategies, type converters, ORM adapters
- **SQL audit** — record all DDL changes, Flyway integration
- **Data initialization** — SQL files, Java methods, dialect-specific paths
- **Multi-datasource** — manage multiple databases with one codebase

## Installation

### From Community Marketplace (after approval)

```bash
/plugin marketplace add anthropics/claude-plugins-community
/plugin install autotable@claude-community
```

### Manual Install

```bash
# Copy skill to your personal skills directory
git clone https://github.com/dromara/auto-table-claude-plugin.git
cp -r auto-table-claude-plugin/skills/autotable-usage ~/.claude/skills/
```

### Test Locally

```bash
claude --plugin-dir ./autotable-claude-plugin
```

## Usage

Once installed, the skill activates automatically when you ask about:

- AutoTable annotations and configuration
- How to define entity classes for auto table creation
- Multi-database adaptation with `@AutoColumns` and `dialect`
- Spring Boot / Solon configuration properties
- Lifecycle callbacks and interceptors
- MySQL / Doris / PostgreSQL specific features
- Type mapping and custom type converters
- Multi-datasource setup
- Production deployment best practices

## Project Structure

```
skills/
└── autotable-usage/
    ├── SKILL.md                              # Main entry + routing table
    └── references/
        ├── quick-start.md                    # Installation, enable, first entity
        ├── annotation-reference.md           # All 29 annotations with full attributes
        ├── configuration.md                  # All config properties
        ├── lifecycle.md                      # Execution flow + 14 hooks
        ├── database-specific.md              # 9 database dialect specifics
        ├── type-mapping.md                   # Java → DB type mapping
        ├── multi-datasource.md               # Multi-datasource setup
        ├── best-practices.md                 # Production deployment + pitfalls
        └── architecture.md                   # Internal architecture + SPI
```

## License

Apache-2.0
