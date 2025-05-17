# Contributing to Insert Tools

🎉 Thanks for taking the time to contribute to **insert-tools**!

We welcome contributions of all kinds — new features, bug fixes, documentation, tests, or feedback. Here's how to get started.

---

## 🛠️ Setting up the project locally

1. **Fork the repository** on GitHub
2. Clone your fork:

   ```bash
   git clone https://github.com/your-username/insert-tools.git
   cd insert-tools
   ```
3. **Install dependencies**:

   ```bash
   pip install -r requirements.txt
   ```
4. **Try the CLI**:

   ```bash
   python clickhouse_insert/cli.py --help
   ```

---

## 📁 Project structure

* `clickhouse_insert/` – main CLI logic and insert functionality
* `tests/` – unit tests
* `examples/` – example configs or use cases
* `README.md` – overview and usage instructions

---

## 🧪 Running tests

We use `pytest` for testing:

```bash
pytest tests/
```

Make sure your feature or fix includes a test case if applicable.

---

## 💬 Making changes

1. Create a new branch:

   ```bash
   git checkout -b your-feature-name
   ```

2. Make your changes

3. Commit your work:

   ```bash
   git commit -m "feat: short description of your change"
   ```

   Example prefixes:

   * `feat:` – new feature
   * `fix:` – bug fix
   * `test:` – test related changes
   * `docs:` – documentation only

4. Push and open a pull request:

   ```bash
   git push origin your-feature-name
   ```

---

## ✨ Suggesting features or reporting issues

We love ideas! Feel free to [open an issue](https://github.com/castengine/insert-tools/issues) for:

* Feature requests
* Bugs
* Usability suggestions

---

## ✅ Code of Conduct

This project follows a [Code of Conduct](./CODE_OF_CONDUCT.md). By participating, you agree to uphold these standards.

---

## 📫 Contact

For questions or discussions, open a GitHub issue or reach out via Discussions tab.

Happy coding! 🚀
