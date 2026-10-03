# reading-feed

Personal RSS feed of curated reading lists (the "how it gets made" digest and blog hunts). Subscribe in any RSS reader with:

    https://echo4eva.github.io/reading-feed/feed.xml

Served by GitHub Pages from the `main` branch root. Static: just `feed.xml` plus this file.

## Adding items

Insert a new `<item>` directly after `<lastBuildDate>` (newest first) in `feed.xml`, and update `<lastBuildDate>`:

```xml
<item>
  <title>[recommended] Article title</title>   <!-- drop the prefix if not recommended -->
  <link>https://original-article-url</link>
  <guid isPermaLink="true">https://original-article-url</guid>   <!-- unique, never reused -->
  <pubDate>Sat, 03 Oct 2026 15:00:00 -0700</pubDate>   <!-- RFC-822, date added -->
  <category>how-it-gets-made</category>   <!-- the list/batch name -->
  <description>Author - one-line note.</description>
</item>
```

Rules: escape `&`, `<`, `>` as `&amp;`, `&lt;`, `&gt;`; never change an existing guid; keep the file well-formed (check with `python3 -c "import xml.etree.ElementTree as E;E.parse('feed.xml')"`).
