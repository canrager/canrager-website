# Add Citation to Blog Post

Use this skill when the user asks to add a citation to a blog post from a URL.

## Steps

1. **Fetch the URL** to extract relevant data (title, author, year, key statistics)

2. **Add entry to bibliography file** at `assets/bibliography/2018-12-22-distill.bib`:
   ```bibtex
   @misc{unique_key,
     title={Title of the source},
     author={Author or Organization},
     year={2025},
     url={https://example.com/source}
   }
   ```
   - Use a descriptive key like `statista2025whatsapp` or `guardian2024privacy`
   - Use `@misc` for web sources, `@article` for journal articles

3. **Insert the citation** in the blog post using the Distill `<d-cite>` tag:
   ```html
   Some claim with data<d-cite key="unique_key"></d-cite>
   ```
   - The citation appears inline as a hoverable number
   - Multiple keys can be comma-separated: `<d-cite key="key1,key2"></d-cite>`

4. **Update any incorrect data** in the text based on what you found from the source

## Example

Before:
```
Whatsapp has 86% market share in Germany (Statista 2025)
```

After adding to `.bib`:
```bibtex
@misc{statista2025whatsapp,
  title={Leading actively used social media platforms in Germany Q2 2025},
  author={Statista},
  year={2025},
  url={https://www.statista.com/statistics/867539/top-active-social-media-platforms-in-germany/}
}
```

After updating text:
```
Whatsapp has 85% market share in Germany<d-cite key="statista2025whatsapp"></d-cite>
```

## Notes

- The bibliography is automatically rendered in an appendix if the post has one
- Distill uses numerical inline citations for readability
- Always verify the data from the source matches what's claimed in the text
