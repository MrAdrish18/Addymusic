# 🌍 Localization System

This system handles multi-language support for the bot using YAML files and Go's `embed` package.

## 📂 Project Structure
* `Addy/locales/*.yml`: Language translation files.
* `Addy/locales/loader.go`: Core logic for loading and fetching strings.
* `Addy/modules/helpers.go`: Contains `F()` and `FWithLang()` for easy access.

## 🛠️ How to Add a New Language
1. **Create File:** Create `Addy/locales/{code}.yml` (e.g., `es.yml`).
2. **Define Name:** Set the display name: `name: "🇪🇸 Español"`.
3. **Translate:** Copy keys from `en.yml` and translate. 
   * Use `{key}` for variables (e.g., `Hello {user}`).
   * Use `|` for multi-line strings.
4. **Deploy:** Files are automatically embedded; no code changes are required.

## 📝 Usage for Developers
Use these helpers instead of calling the loader directly:
* `F(chatID, key, args...)`: Automatically detects chat language.
* `FWithLang(lang, key, args...)`: Force a specific language.

---

## 👥 Language Contributors

| Language | Code | Contributor |
| :--- | :--- | :--- |
| 🇺🇸 English | `en` | [@AddyUpdate](https://github.com) |
| 🇮🇳 Hindi | `hi` | [@AddyUpdate](https://github.com) |
| 🇸🇦 Arabic | `ar` | [@AddyUpdate](https://github.com) |
| 🇹🇷 Turkish | `tr` | [@AddyUpdate]
*All YAML files in `Addy/locales/` are automatically embedded into the binary during compilation.*