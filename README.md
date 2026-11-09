# Ireland Legal Research MCP Server (`ie-legal-mcp`)

**[Gaeilge](#lang-ga) | [English Documentation](#english-documentation)**

---

<a id="lang-ga"></a>
## Freastalaí MCP Dlí agus Cásdlí na hÉireann (`ie-legal-mcp`) — Gaeilge

### Maidir leis an Stór seo

Soláthraíonn an stór seo freastalaí Model Context Protocol (MCP) a nascann d'fheidhmchlár IS (Claude Desktop, Cursor, Windsurf, VS Code / Copilot, Cline nó Antigravity) go díreach le Leabhar Reachtanna na hÉireann (`irishstatutebook.ie`), Tithe an Oireachtais, agus breithiúnais Chúirteanna na hÉireann (`courts.ie` — An Chúirt Dúiche, An Chúirt Chuarda, An Ard-Chúirt, An Chúirt Achomhairc agus An Chúirt Uachtarach).

### Suiteáil Thapa (Roghnú do Chliant IS)

1. **Íoslódáil:** Cliceáil ar **`<> Code` -> `Download ZIP`** thuas ar dheis agus bain an fillteán amach ar do ríomhaire.
2. **Rith an tSuiteáil:** Déan клиc dúbailte ar **`Click_Here_To_Install_Windows.bat`** (Windows) nó **`Click_Here_To_Install_Mac.command`** (macOS).
3. **Roghnaigh Feidhmchlár IS:** Roghnaigh na feidhmchláir IS a úsáideann tú, cliceáil ar Suiteáil agus atosú d'fheidhmchlár IS.

**Nóta Slándála:** Oibríonn an uirlis seo i mód inléite amháin (read-only) agus ní dhéanann sé teagmháil le haon chomhaid phearsanta ar do ríomhaire.

### Ordlathas na gCúirteanna agus Foinsí Oifigiúla

| Céim Bhreithiúnach | Cúirteanna Clúdaithe |
|:---|:---|
| **Céad Chéim (An Chúirt Dúiche, An Chúirt Chuarda & An Ard-Chúirt)** | District Court of Ireland, Circuit Court of Ireland & High Court of Ireland (IEHC) |
| **Achomharc (An Chúirt Achomhairc — IECA)** | Court of Appeal of Ireland (IECA — Civil & Criminal) |
| **An Chúirt Uachtarach (IESC)** | Supreme Court of Ireland / Cúirt Uachtarach na hÉireann (IESC) |

- **electronic Irish Statute Book (irishstatutebook.ie) & Oireachtas Open Data API:** [https://www.irishstatutebook.ie](https://www.irishstatutebook.ie) (`irishstatutebook.ie`, `oireachtas.ie`)
- **Courts Service of Ireland Judgments Registry (courts.ie/judgments — IEHC, IECA, IESC):** [https://www.courts.ie/judgments](https://www.courts.ie/judgments) (`courts.ie`, `bailii.org`)

---

<a id="english-documentation"></a>
## English Documentation

Model Context Protocol (MCP) server providing live, read-only access to **Ireland (IE)** legislation, official gazettes, multi-tier judicial decisions (First Instance, Regional/Cantonal/Appellate, and Supreme/Constitutional courts, including HTML and PDF full-text extraction), and statutory citation verification across all major AI clients (**ChatGPT Desktop, OpenAI Codex CLI, Claude Desktop, Claude Code CLI, Cursor, Windsurf, VS Code / GitHub Copilot / Cline / Roo Code, Google Antigravity / Gemini CLI, Perplexity, and Continue.dev**).

---

### Interactive Desktop Setup (Select Your AI Assistant)

This package includes a graphical installer for legal practitioners and non-technical users that lets you select which AI application(s) you use:

1. **Download:** Click **`<> Code`** at the top right of this repository, select **`Download ZIP`**, and extract the folder to your computer.
2. **Run the Setup Utility:**
   - **Windows:** Double-click `Click_Here_To_Install_Windows.bat`
   - **macOS:** Double-click `Click_Here_To_Install_Mac.command`
3. **Select Your AI Client(s) & Connect:** Check the box(es) for the AI assistant(s) installed on your computer (**ChatGPT Desktop & OpenAI Codex CLI**, **Claude Desktop & Claude Code CLI**, **Cursor**, **Windsurf**, **VS Code / GitHub Copilot / Cline / Roo Code**, **Google Antigravity / Gemini CLI**, or **Perplexity / Continue.dev**), click **Install to Selected AI Clients**, and restart your selected AI application.

**System Integrity Note:** The setup utility operates strictly in read-only mode with respect to your personal files and documents. It installs an isolated Python runtime inside the extracted folder and registers the server entry only in the AI client configuration files you select.

---

### Multi-Tier Judicial Hierarchy & Live Indexed National Archives

This server performs live queries across the full judicial hierarchy and official legal archives of **Ireland**, extracting full text from both HTML pages and official court/gazette PDF judgments:

| Judicial Tier | Covered Courts & Tribunals |
|:---|:---|
| **Tier 1 — First Instance** | District Court of Ireland, Circuit Court of Ireland & High Court of Ireland (IEHC) |
| **Tier 2 — Regional / Cantonal / Appellate** | Court of Appeal of Ireland (IECA — Civil & Criminal) |
| **Tier 3 — Supreme & Constitutional** | Supreme Court of Ireland / Cúirt Uachtarach na hÉireann (IESC) |

#### Official Portals & Live Indexed Domains

- **National Legislation & Official Gazette:** electronic Irish Statute Book (irishstatutebook.ie) & Oireachtas Open Data API — [https://www.irishstatutebook.ie](https://www.irishstatutebook.ie)
  - *Indexed Legislation Domains:* `irishstatutebook.ie`, `oireachtas.ie`
- **Court Decisions & Jurisprudence Archives:** Courts Service of Ireland Judgments Registry (courts.ie/judgments — IEHC, IECA, IESC) — [https://www.courts.ie/judgments](https://www.courts.ie/judgments)
  - *Indexed Judicial & Open Case Law Domains:* `courts.ie`, `bailii.org`

---

### Available MCP Tools

| Tool | Description |
|:---|:---|
| `search_legislation` | Searches enacted statutes, codes, decrees, and official gazette publications in Ireland. |
| `search_case_law` | Searches national jurisprudence and open judicial archives for Ireland. |
| `search_tiered_court_decisions` | Filters case law specifically by judicial instance (`first_instance`, `appellate_regional`, `supreme_constitutional`) or specific regional/cantonal/district court. |
| `list_court_hierarchy` | Returns the complete 3-tier court structure and supported regional court filters for Ireland. |
| `get_legal_document_markdown` | Retrieves full statutory or judicial texts (both HTML and official `.pdf` court judgments) and converts them into clean Markdown. |
| `verify_citation` | Validates statutory and case law citations against official registries. |

---

<details>
<summary><b>Manual Configuration for Developers (Optional)</b></summary>

```json
{
  "mcpServers": {
    "ie-legal-mcp": {
      "command": "uvx",
      "args": [
        "--from",
        "https://github.com/jurisatlas/ie-legal-mcp/archive/refs/heads/main.zip",
        "ie-legal-mcp"
      ]
    }
  }
}
```
</details>
