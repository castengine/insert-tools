# 🚀 Insert Tools

[![PyPI version](https://img.shields.io/pypi/v/insert-tools)](https://pypi.org/project/insert-tools/)
[![Python Versions](https://img.shields.io/pypi/pyversions/insert-tools)](https://pypi.org/project/insert-tools/)
[![Downloads](https://img.shields.io/pypi/dm/insert-tools)](https://pypi.org/project/insert-tools/)
[![GitHub Workflow Status](https://img.shields.io/github/actions/workflow/status/castengine/insert-tools/python-ci.yml?branch=main)](https://github.com/castengine/insert-tools/actions)
[![License](https://img.shields.io/github/license/castengine/insert-tools)](https://github.com/castengine/insert-tools/blob/main/LICENSE_NONCOMMERCIAL.md)
[![Last commit](https://img.shields.io/github/last-commit/castengine/insert-tools)](https://github.com/castengine/insert-tools/commits)
[![Stars](https://img.shields.io/github/stars/castengine/insert-tools?style=social)](https://github.com/castengine/insert-tools)

**Problem:**

Have you faced issues inserting data into databases? Constant schema mismatch errors, incorrect data types, manual checks, and even silent data corruption? If you work with large ETL pipelines and databases, you know how painful it can be.

**Solution:**

Insert Tools is a robust and flexible tool designed for safe and fast data insertion into databases — starting with ClickHouse. It validates schema by column names (not by order), supports automatic type casting, and lets you dry-run your inserts before touching real data. Perfect for ETL pipelines where target table schemas evolve frequently.

## 🔥 Why you should try it:

* ✅ **Data safety:** Validates column names and types before insert.
* ⚙️ **Auto type casting:** Converts mismatched types when enabled.
* 🚧 **Dry-run mode:** Test inserts without touching data.
* 🐳 **Docker-ready:** Comes with ready-to-use Docker integration.
* 🔧 **Configurable:** Fully controllable insert pipeline.
* 🔥 **Time saver:** Automates validation and error prevention.

## 🎯 Key Features:

* 🖥️ Simple CLI and Python API.
* 🛡️ Strict mode to block extra columns.
* 📌 Detailed logging and diagnostics.
* 🔄 Easy CI/CD integration.

## 📦 Quick install:

```bash
pip install insert-tools
```

To install for development:

```bash
pip install -e .[dev]
```

[Link to the project on PyPI](https://pypi.org/project/insert-tools/)

## 🚀 Run & Examples:

### 🐍 Python usage:

```python
python
Копировать
Редактировать
from insert_tools.pipeline import InsertPipeline
from insert_tools.sink.clickhouse import ClickhouseSink

pipeline = InsertPipeline(
select_sql="SELECT * FROM source_table",
sink=ClickhouseSink(
host="localhost",
database="default",
target_table="my_table",
user="default",
password="admin123",
),
allow_type_cast=True,
strict_column_match=True,
)

pipeline.run()
```

### 🖥️ CLI usage:

```bash
python -m insert_tools.cli \
  --config path/to/config.yaml \
  --dry-run \
  --verbose
```

## 🧪 Testing & Integration:

```bash
pytest -v --cov=insert_tools tests/
```

Integration tests are supported via Docker (`docker-compose.yml`).

## 📈 Roadmap:

Planned and upcoming features:

### ✅ Core & Safety
- [x] ClickHouse support (stable)
- [ ] Manual `insert_columns` mapping
- [ ] Logging configuration (file, level, formatting)
- [ ] Dry-run + exit codes
- [ ] Strict schema validator with preview

### 📦 Priority Database Support
- [ ] MySQL — no name-based insert, requires exact column order
- [ ] PostgreSQL — order and column count must match
- [ ] SQLite — insert depends on column order
- [ ] Oracle — insert requires explicit column mapping
- [ ] SQL Server — insert must follow column order

### 🧰 Advanced Features
- [ ] Error handling strategies (`fail`, `warn`, `skip`)
- [ ] Config file validation (optional)
- [ ] Secure secrets handling (.env / vault)
- [ ] Optional CAST rules config

### 📘 Ecosystem
- [ ] Full documentation site (mkdocs)
- [ ] Schema + config reference
- [ ] Auto-generated help from CLI
- [ ] GitHub Discussions / Community page

## 🛠️ Configuration Options

| Parameter             | Description                            | Required |
| --------------------- | -------------------------------------- | -------- |
| `host`                | ClickHouse server hostname             | ✅        |
| `port`                | ClickHouse server port                 | ❌        |
| `user`                | ClickHouse user                        | ❌        |
| `password`            | ClickHouse password                    | ❌        |
| `database`            | Target database                        | ✅        |
| `target_table`        | Target table name                      | ✅        |
| `select_sql`          | SQL query to fetch data                | ✅        |
| `allow_type_cast`     | Allow type casting on mismatch         | ❌        |
| `strict_column_match` | Enable strict mode for column matching | ❌        |

## 🧱 How It Works

1. Fetches target table schema from ClickHouse.
2. Extracts column names and types from `SELECT` query.
3. Applies optional `CAST(...)` if types mismatch.
4. Validates column alignment and inserts data.

## 🤝 Contributing:

Ideas, bug reports, and pull requests are welcome! Join the community and help make Insert Tools better.

## ⚖️ License

This project uses a **dual-license model**:

* 🆓 **Non-commercial license** — free to use for personal, educational, and internal non-commercial purposes. See [LICENSE\_NONCOMMERCIAL.md](./LICENSE_NONCOMMERCIAL.md)
* 💼 **Commercial license** — required for any commercial use. See [LICENSE\_COMMERCIAL.md](./LICENSE_COMMERCIAL.md) or contact [k.n.gorelov@gmail.com](mailto:k.n.gorelov@gmail.com) for licensing terms.

> Insert Tools makes data insertion simple, fast, and safe. Save your time and nerves today!
