## `bio.json` Schema

Your `bio.json` file defines what appears on your OPN profile. Below is a breakdown of its structure and how to use each part.

### Top-Level Fields

| Field         | Type   | Required | Description                                |
| ------------- | ------ | -------- | ------------------------------------------ |
| `name`        | string | ✅       | Your full name (or display name).          |
| `description` | string | ✅       | A short tagline or summary of who you are. |
| `sections`    | array  | ❌       | Optional content blocks for your profile.  |
| `style`       | object | ❌       | Customize font and theme (light/dark).     |

---

### Sections

The `sections` field is an array of content blocks. Each block must be one of the following `type`s:

#### 1. **List Section**

Displays a list of items, such as work experience, projects, publications, etc.

```json
{
  "title": "Projects",
  "type": "list",
  "items": [
    {
      "title": "Project One",
      "description": "An open-source project.",
      "url": "https://github.com/yourname/one",
      "date": "2025"
    }
  ]
}
```

| Field                 | Type   | Required | Description                      |
| --------------------- | ------ | -------- | -------------------------------- |
| `title`               | string | ✅       | Section title (e.g. "Projects"). |
| `type`                | string | ✅       | Must be `"list"`.                |
| `items`               | array  | ✅       | List of entries in the section.  |
| `items[].title`       | string | ✅       | Title of the entry.              |
| `items[].description` | string | ❌       | Short description.               |
| `items[].url`         | string | ❌       | Optional link.                   |
| `items[].date`        | string | ❌       | Optional date (e.g. year).       |

---

#### 2. **Text Section**

Displays a block of plain textn.

```json
{
  "title": "About Me",
  "type": "text",
  "content": "I'm a developer who loves building open tools for the web."
}
```

| Field     | Type   | Required | Description       |
| --------- | ------ | -------- | ----------------- |
| `title`   | string | ✅       | Section title.    |
| `type`    | string | ✅       | Must be `"text"`. |
| `content` | string | ✅       | The text content. |

---

#### 3. **Links Section**

Displays a group of external links, like social media or portfolios.

```json
{
  "title": "Connect",
  "type": "links",
  "links": [
    {
      "title": "GitHub",
      "url": "https://github.com/yourname"
    }
  ]
}
```

| Field           | Type   | Required | Description          |
| --------------- | ------ | -------- | -------------------- |
| `title`         | string | ✅       | Section title.       |
| `type`          | string | ✅       | Must be `"links"`.   |
| `links`         | array  | ✅       | List of links.       |
| `links[].title` | string | ✅       | Label for the link.  |
| `links[].url`   | string | ✅       | The URL of the link. |

---

### Style (Optional)

Customize your profile’s appearance.

```json
"style": {
  "font": "serif",
  "theme": "dark"
}
```

| Field   | Type   | Options                   | Description           |
| ------- | ------ | ------------------------- | --------------------- |
| `font`  | string | `"serif"`, `"sans-serif"` | Choose a font style.  |
| `theme` | string | `"light"`, `"dark"`       | Choose a color theme. |
