---
created: 2024-07-22T17:29
updated: 2024-07-22T18:55
---
# Obsidian OSINT Templates & Plugins

The following page contains templates to create structured and interlinked pages for an open source intelligence ([OSINT](https://en.wikipedia.org/wiki/Open-source_intelligence)) investigation in [Obsidian](https://obsidian.md/).

# Sample [Obsidian Graph](https://help.obsidian.md/Plugins/Graph+view)

One of the main features of Obsidian is its graphical capabilities. The graph below shows an investigation in-the-making using the templates of this repository.

<img src="https://github.com/resistec/obsidian-osint-templates/blob/main/graph.png" style="width:400px;"/>

The Graph is a powerful tool because it lets us escape hierarchical file organization. Hierarchy always limits the flow of ideas. By connecting our notes in a principled manner, we can mitigate ontological biases. The graph focuses knowledge from category onto relations, thereby overcoming some of the limitations of linear note-taking.
# Contents

## Entities

The current [ontology](https://en.wikipedia.org/wiki/Ontology_(information_science)) contains entities of the following types:

| Entity                | Type                                         | Parent / Child / Both                    | Standard Name                                                                                                    | Example                                                                 |
| --------------------- | -------------------------------------------- | ---------------------------------------- | ---------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| Account               | Possession (Actant if owner is unattributed) | Child                                    | [username]_[platform]                                                                                            | potus_Facebook, username_Instagram                                      |
| Asset                 | Possession                                   | Child                                    | [Parent]_[Asset]                                                                                                 | house_JohnAdams, office_JoeBiden, car, phone                            |
| Crypto Wallet         | Possession                                   | Both                                     | [Parent]_[CryptoWallet]-[num]                                                                                    |                                                                         |
| Domain                | Possession                                   | Both                                     | web address without protocol or port specification                                                               | www[.]example[.]com                                                     |
| Event                 | Context                                      | Parent                                   | [yyyy.mm.dd.hh.mm.ss]-[location]-[event]                                                                         | 1979-Iran-IslamicRevolution, 1956.10-Budapest-Revolution, 1956-Suez-War |
| Host IP Address       | Possession                                   | Both                                     | a legit IPv4 or IPv6 address or address range                                                                    | 8[.]8[.]8[.]8, 192.168.0.0/18                                           |
| Indicator             | Possession                                   | Child to TTP or Event, Parent to Event   | [STIX v2.1+](https://docs.oasis-open.org/cti/stix/v2.1/cs01/stix-v2.1-cs01.html#_muftrcpnf89v)conventions        | file is_part_of Poison_Ivy malware                                      |
| Intellectual Property | Possession                                   | Child                                    | [article/book/etc. title]                                                                                        | Obsidian OSINT Templates                                                |
| Organization          | Actant                                       | Both                                     | an unambiguous name; Org-[alphanum] if unknown                                                                   | CIA, Nestle, UNICEF, Org-1                                              |
| Person                | Actant                                       | Both                                     | an unambiguous name; [FirstSecondLast]-[IDno] if multiple; [Organization]_[Role] or Person-[alphanum] if unknown | Joe Biden, CEO_EvilCorp, Person-1, TimWolf-22                           |
| Phone Number          | Possession                                   | Both                                     | +[country-code]-[dialer]-000-0000                                                                                | +44-60-000-1234                                                         |
| TTP                   | Possession                                   | Both (Child restricted to Weapon System) | performance statement: verb + object                                                                             | identify assets, weaponize software                                     |
| Weapon System         | Possession                                   | Both (Parent restricted to TTP)          | name or standard identifier                                                                                      | AK-47, Predator Drone                                                   |


## Properties

Each entity has at least one of the following properties:

| Property  | Definition                                                                                                                                                   | Link / Shadow Entity | Illegitimate Relations                |
| --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------- | ------------------------------------- |
| Location  | An attribute that definitely and unambiguously locates an entity in physical space. Cannot be in logical space, e.g. a specific folder on a digital machine. | Y                    | Online Account, Domain, Crypto Wallet |
| Date-Time | An attribute that definitely and unambiguously locates an entity in a common reference framework of time across the investigation.                           | N                    | None                                  |
| Tag       | Each entity has a unique tag with no ontological function but to help with Obsidian formatting.                                                              | N                    | None                                  |
| Aliases   | Common names used to refer to the entity that are not in its title.                                                                                          | N                    | None                                  |

Notice that the **Location** property can be linked to entities, meaning, you may see location tags as “shadow” entities in the Obsidian Graph. Despite this, they are NOT treated as entities in the present ontology.

In contrast, **Date**-**Time** cannot be linked as a shadow entity. Instead, Date-Time may be part of the name of an Event. If you decide to create a linked page for a Date-Time property (which may be legitimate when you decide to investigate the given time-based clue later), make sure to transform the property to an Event later.

**Tags** always mirror a single given entity name. They serve to color the Graph. If and when an entity page has mutliple tags, only one tag should be colored on the Graph. Properties should not have tags, except for Location.

## Additional Metadata

Additional metadata on each page includes the creation and last edited date-times of the page.

# Installation

1. Save the files of this repository. 
2. Open an Obsidian Vault with the files in it.
3. Click the Settings icon > Community Plugins > Browse > Install & Enable Templater by SilentVoid
4. Click Options 
	1. Set "Template folder location" to "/Templates"
	2. Choose "Trigger Templater on new file creation"
5. Install and configure optional plugins
# How to Use

Start an investigation in a clean [Obsidian Vault](https://help.obsidian.md/Getting+started/Create+a+vault).

Use any template that you need for a given entity. For present purposes, let's say we start off the investigation with a website.

1. The first entity thus will be a domain. Open a new note and use the Domain template.
2. Fill in the information in the Domain template wherever you can.
3. Create links by appending phrases with double squared brackets `[[…]]` to new pages. Legitimate links lead to one of the ten entities defined above, or to external resources referenced with `(…)[…]`.
4. Open the new pages you created as children of the domain and take notes in their respective templates.

For instance, if we found that the website belongs to a certain Company A, we create a link as in `[[Company A]]` and copy the **Organization** template to that page.

We repeat this process as many times as needed.

# Learn Obsidian for OSINT

For those who are new to Obsidian, the following resources may be helpful to consult:

- https://www.youtube.com/live/sKF37Ng4gaI?si=tDe-1eS4IFhxRws6
- https://youtu.be/eLqQo38wC2Q?si=2VmPX95tHUd5nre4
- https://medium.com/@farallon/uncommon-osint-obsidian-semantic-meaning-and-nlp-3339e1e51d70
- https://www.linkedin.com/pulse/unlocking-power-osint-my-workflow-effective-scott-altiparmak-3bs4e
- https://publication.osintambition.org/unlock-the-power-of-obsidian-for-osint-and-blockchain-intelligence-analysis-a69e526e2638

# Other Obsidian Templates

- https://github.com/WebBreacher/obsidian-osint-templates
- https://github.com/malleVF/Threat-Research-with-Obsidian-for-SOC-Analysts

# Best Practices

- Use the templates to pivot from one clue to another, all the while keeping track of still missing information.
- Create tasks across notes to remember where to follow up later on.
- **In the Graph View, exclude paths other than the current investigation.**
- You can create a folder structure for your investigations and organize the files in them. My system looks like this:
    
    ```markdown
    .
    |__ Investigations
    		|__Case-1
    		|__Case-2
    				|__General Recon
    						|__Organizations
    						|__People
    						|__Digital Accounts
    						|__Assets
    						|__Intellectual Property
    				|__Locations
    				|__Technical Recon
    				    |__Domains
    				    |__Hosts
    				    |__Phones
    				    |__Emails
    ```
    
- **Use the Replace functionality to bulk rename a list of targets** you copied from an aggregator site. For example, a domain may have many sub-domains, each of which you want to link and visualize in your Graph after having copied or imported them from a tool.
- **There are two approaches to being consistent in your workflow:**
    1. **either follow through all the leaves of a branch in the graph;**
    2. **or record all pivot points in the graph as you go through sources and tools and return to empty leaves later.**
    
    The first method is more likely to be exhaustive, may show clearer links, can help better pivotting. At the same time, this method takes considerably more time and may easily lead to unproductive black holes.
    
    The second method is more intuitive and relies more on the capabilities of sources and tools. It may easily mislead you if you trust the wrong information, fail to avoid tunnel vision or recognize pivots due to an overreliance on existing sources and tools.
    
    **You keep track of empty or incomplete notes with [obsidian-incomplete-files](https://github.com/HananoshikaYomaru/obsidian-incomplete-files), or even prioritize specific strings or blocks with [obsidian-prio-plugin](https://github.com/Tekknoman/obsidian-prio-plugin).**
    

# Recommended Plugins

### Essential

1. [Templater](https://github.com/SilentVoid13/Templater) makes it possible to create and use templates in your workspace. Make sure to set the template path to the folder where this repo is located on your machine.
2. [Auto Template Trigger](https://github.com/numeroflip/obsidian-auto-template-trigger) adds a tiny twist to the game, enabling you to escape the command palette and import a template to a new note or directory automatically.
3. [Update Time on Edit](https://github.com/beaussan/update-time-on-edit-obsidian) displays creation and last edit date-times on your notes; essential for keeping track of your investigation.
4. [Omnisearch](https://github.com/scambier/obsidian-omnisearch) enables you to search for strings across your vault.
5. [Pandoc](https://github.com/OliverBalfour/obsidian-pandoc)
6. [Quite Outline](https://github.com/guopenghui/obsidian-quiet-outline) adds a searchable table of contents for each page. Useful for quick navigation. Alternatively, you can use [Create Note List](https://github.com/andrewheekin/obsidian-create-note-list) which does the same but with bullet points.
7. [Hierarchical-outgoing-links](https://github.com/jasonmotylinski/hierarchical-outgoing-links) will display all outgoing internal links in your current page categorized by the links’ tags. Given that the template structure of this repo follow a similar logic, this could help you easily find links (leaves in a branch) to specific types of entities.

### Optional

1. [Advanced Tables](https://github.com/tgrosinger/advanced-tables-obsidian): create and edit markdown tables easily. 
2. [Relative Line Numbers](https://github.com/nadavspi/obsidian-relative-line-numbers): adds relative line numbers that helps with navigating a multiline page. 
3. [Tag-wrangler](https://github.com/pjeby/tag-wrangler): easier renaming, searching and management of tags.
4. [Obsidian-db](https://github.com/RafaelGB/obsidian-db-folder): Obsidian Plugin to Allow Notion like database based on folders
5. [Text Generator](https://github.com/nhaouari/obsidian-textgenerator-plugin)
6. [Editing Toolbar](https://github.com/PKM-er/obsidian-editing-toolbar): display editing options in a toolbar.
7. [Code Block](https://github.com/paddan/code-block-plugin): add advanced code blocks to a page.
8. [Linter](https://github.com/platers/obsidian-linter) enables you to assign formatting rules to actions, making your workflow more productive and efficient.
9. [Safe Filename Linter](https://github.com/sneaky-foxes/obsidian-safe-filename-linter) if you want to create or import filenames that are invalid in vernacular Obsidian.
10. [Cryptsidian](https://github.com/triumphantomato/cryptsidian) encrypts your vault locally; can be used for secure file transfer or cloud sync.
11. [Obsidian Hash](https://github.com/zigahertz/obsidian-hash) provides a hash to each page, so that you can check the integrity of files or share data with trust and confidence.
12. [Garble Text](https://github.com/kurakart/garble-text) makes all text and media files in your Obsidian workspace inreadable. Useful for sharing screenshots with team members or clients when you want to point only to selected information.
13. [GPG Inline Encrypt](https://github.com/lajg-dev/obsidian-plugin-gpg-inline-encrypt) encrypts pages or selected strings (!) in your obsidian note. You can use it to share intelligence based on more inclusive **need**-**to**-**share** principles.
14. Use [Obsidian-Git](https://publish.obsidian.md/git-doc/Installation) with [obsidian-version-history-diff](https://github.com/kometenstaub/obsidian-version-history-diff) to see a detailed version history of your investigation. This is essential if you prepare a report for dissemination at legal or forensic authorities. **Privacy considerations** should be made before deploying these tools! 
15. The previous tools can be combined with [Activity History](https://github.com/Darakah/obsidian-activity-history) to provide Github activity-like visualization for your history.
16. For completed tasks, you can create a time-based tree-like archive with [Task Archiver](https://github.com/ivan-lednev/obsidian-task-archiver).
17. [Link Archive](https://github.com/tomzorz/obsidian-link-archive) submits every internet-facing URL in the current page to WaybackMachine, automatically archiving your links. **Be considerate, mission INFOSEC or ethical considerations regarding amplification may be contrary to this practice.**
18. [Incomplete Files](https://github.com/HananoshikaYomaru/obsidian-incomplete-files) is a great plugin to automatically mark pages that are empty or incomplete.
19. With [Adjacency Matrix Maker](https://github.com/SkepticMystic/adjacency-matrix-maker) you can see the relations between your notes in a matrix format. This may be helpful when looking for pivot points in the Graph yields no results due to its visual complexity. The Matrix view could be implemented into cryptocurrency and blockchain investigations, where addresses and hashes obfuscate a lot on the Graph.
20. Once you ended your investigation, you may try to aim for a last pivot with [Graph Analysis](https://github.com/SkepticMystic/graph-analysis). Analyzing your notes, this plugin uses various algorithms to identify or predict relations between entities. Relations you may have not noticed yourself.
21. If you take notes in multiple languages or work on a multilingual investigation, a great tool to auto-translate note-titles is [Obsidian Multilingual](https://github.com/leolazou/obsidian-multilingual).
22. [CSV Table](https://github.com/coddingtonbear/obsidian-csv-table) will help you import csv datasets to Obsidian. [JSON Table](https://github.com/dario-baumberger/obsidian-json-table) does the same for JSON files. Useful when you download or copy table formatted data en masse.
23. [Obsidian Mermaid](https://github.com/dartungar/obsidian-mermaid) is a plugin that makes it easier to create Mermaid flow-charts without memorizing all the code.
24. [Leaflet](https://github.com/javalent/obsidian-leaflet) is a cool plugin if you want to save geolocation data in your notes and visualize them on interactive maps. Could be especially useful to recognize spatial relations (Location tags!) between targets.
25. [Bulk Rename](https://github.com/OlegLustenko/obsidian-bulk-rename) is a simple tool to bulk rename your page titles with regex patterns and update all links accordingly.
26. [Obsidian Cron](https://github.com/cdloh/obsidian-cron) enables you to attach Obsidian commands to cron jobs, i.e. schedule commands to execute automatically in specific intervals.
27. Run your own python scripts from Obsidian with [Python Scripter](https://github.com/nickrallison/obsidian-python-scripter). Could be useful to feed the results of certain collection tools, like Sherlock or Maigret, right into your notes.
28. You could use [Regex Pipeline](https://github.com/No3371/obsidian-regex-pipeline?tab=readme-ov-file) to auto-format text from bulk input with regex parameters, e.g. when importing online accounts from multiple username enumeration tools that use different output formatting.
29. [Smart2Brain](https://github.com/your-papa/obsidian-Smart2Brain) is an AI chatbot that can be run locally to query your Obsidian notes; although not tested, it could be useful for various analytic tasks when pivotting.
30. [No Dupe Leaves](https://github.com/scambier/obsidian-no-dupe-leaves) is useful to avoid duplicate open tabs, but has some functionality caveats.
31. [Tag Summary](https://github.com/macrojd/tag-summary) can collect in one space all lines where a tag (#likethis) is present across your notes. Useful for creating summaries by specific types of entities on top of your notes, in your final report or just for a general orientation of properties across your entities.
32. [Hunchly](https://github.com/shadowoption/Hunchly-obsidian-plugin) ‐ import the results of the Hunchly web capture tool into Obsidian.
33. If you do persistent monitoring using RSS feeds, you can use the following plugin to follow and copy RSS feeds to your Obsidian vault: [RSS](https://github.com/joethei/obsidian-rss). Addig AI-enabled auto-tagging or linking could enable you to auto-create dynamic graphs that display relations between global news and events.
34. When creating Event type entities in your investigation's vault, the ability to see and edit a list of chronological events (each a separate page) is a great enhancer of productivity. With the [Daily Notes Editor](https://github.com/Quorafind/Obsidian-Daily-Notes-Editor) tool you can do just that!
35. The [Keyword Highlighter](https://github.com/marcel-goldammer/obsidian-keyword-highlighter) tool highlights keywords across your vault, marking important phrases, like the target's name, an ID or hash, with clear visibility.

# Obsidian Basics

> See more at https://github.com/ieshreya/Obsidian-Cheat-Sheet

### Shortcuts

- `Ctrl + P` open command palette
- `Ctrl + G` open graph view
- `Ctrl + N` create new note
- `Ctrl + O` see recent files & open file
- `Ctrl + Shift + F` search in all files
- `Alt + E` insert template

### Formatting

- Internal Links:  `[[note name]]` to create internal links to other notes.
- External Links: Use `[Text](URL)` to create external links.
- Bullet Points: Use `-`, `*`, or `1`.
- Headings: Use `#` (e.g., # Heading 1, ## Heading 2).
- Code Blocks: Wrap text in triple backticks `(```)`.
- Embeds: Use `![[note name]]` to embed another note in your current note.
- Callout: `>` to create text in callout.
    
    ```
    > [!title]
    > Here's a callout block.
    > It supports **Markdown**, [[Internal link|Wikilinks]], and [[Embed files|embeds]]!
    > ![[Engelbart.jpg]]
    ```
    
- Divider: `---` to create horizontal divider line.
- Tables:
    
    ```
    First name | Last name
    -- | --
    Max | Planck
    Marie | Curie
    ```
    

### Graph View Transformations

[Graph view - Obsidian Help](https://help.obsidian.md/Plugins/Graph+view)

**Filters:**

- Search filters: set `path:Investigations` if your files are in the Investigations directory.
- Unselect: tags, attachments, existing files only.
- Select: orphans.

**Groups:** set different colors for each

- tag:#domain
- tag:#IP
- tag:#company
- tag:#team
- tag:#person
- tag:#account
- tag:#email
- tag:#phone
- tag:#TTP
- tag:#weapon
- tag:#intel_prop

**Display:** 

- **Arrows** toggles whether to show the direction of each link.
- **Text fade threshold** controls the text transparency for the name of each note.
- **Node size** controls the size of the circle representing each note.
- **Link thickness** controls the line width for each link.
- **Animate** starts a [time-lapse animation](https://help.obsidian.md/Plugins/Graph+view#Start%20a%20time-lapse%20animation).

**Forces:**

- **Center force** controls how compact the graph is. A higher value creates a more circular graph.
- **Repel force** controls how much a node pushes other nodes away from it.
- **Link force** controls the pull on each link. If the link was a rubber band, the link force controls how tight or loose the band is.
- **Link distance** controls the length of the lines between each note.

# License

These templates are free to use and distribute. Please credit the creator if distributed.