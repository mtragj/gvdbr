# Archived images

Images in this folder are **not referenced by any page, post, layout, include or
stylesheet**. They are kept here rather than deleted so past photos stay
available for reuse, while making it obvious that nothing on the site links to
them.

To bring one back into use, move it up to `images/` and reference it from a
post's `image:` frontmatter (see the image sizing conventions in `CLAUDE.md`).

To re-check which images are unused:

```bash
for f in $(git ls-files images/ | grep -v '/archived/'); do
  b=$(basename "$f")
  grep -rqF "$b" --exclude-dir=_site --exclude-dir=.git --exclude-dir=images . \
    || echo "unreferenced: $f"
done
```

Note that `sarlacc_n_desert.jpg` was archived under the corrected spelling; it
was previously `sarlaac_n_desert.jpg`.
