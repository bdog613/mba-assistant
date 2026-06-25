# PDF Export (human-looking, RUNI format)

Every exported deliverable must look like a human wrote it in Word, not like AI output. This is the format a one-year MBA program (RUNI) expects, and it removes the loudest visual AI tells. Use it for the final PDF unless the assignment specifies a different format.

## The rules
- Font: David, 12pt. (David Libre is the open-source David and renders identically in a PDF. Load it from Google Fonts if David isn't installed locally.)
- Line spacing: 1.5.
- Alignment: justified (both edges).
- Headings: the SAME font and 12pt size as the body. Set them apart with bold and/or underline only. Never a bigger or different heading font.
- No horizontal rules. No bold-bullet lead-ins ("**Term:** ..."). Straight quotes only. No em dashes.
- Code snippets stay in a monospace block; keep lines short enough to fit the page width (a too-wide line clips at the right margin in print).

## The pipeline (markdown to styled HTML to PDF)
Put the finished markdown inside the styled HTML template below (in the `<script type="text/markdown" id="src">` block). The page renders it client-side with marked.js and renders any ```mermaid``` block as a diagram. Then print to PDF with headless Chrome.

### HTML template (head + the David CSS)
```html
<!doctype html>
<html lang="en"><head><meta charset="utf-8">
<link href="https://fonts.googleapis.com/css2?family=David+Libre:wght@400;500;700&display=block" rel="stylesheet">
<style>
  @page { size: A4; margin: 2.5cm; }
  body { font-family: 'David','David Libre','Times New Roman',serif; font-size: 12pt; line-height: 1.5; text-align: justify; color:#000; margin:0; }
  h1,h2,h3,h4 { font-family: inherit; font-size: 12pt; font-weight: bold; line-height: 1.5; text-align: left; margin: 1.1em 0 .35em; }
  h1 { text-align: center; text-decoration: underline; margin: 0 0 .2em; }
  h2 { text-decoration: underline; }
  h3 { text-decoration: none; }
  p { margin: 0 0 .55em; }
  ul,ol { margin:.3em 0 .7em; padding-left:1.6em; } li { margin:.12em 0; }
  table { border-collapse: collapse; width:100%; margin:.7em 0; }
  th,td { border:1px solid #000; padding:4px 8px; text-align:left; vertical-align:top; line-height:1.3; } th{font-weight:bold;}
  code { font-family:'Courier New',monospace; font-size:11pt; }
  pre { font-family:'Courier New',monospace; font-size:10.5pt; line-height:1.35; border:1px solid #999; padding:8px 10px; white-space:pre; text-align:left; }
  .mermaid { text-align:center; margin:1em 0; }
  hr { display:none; }
  a { color:#000; text-decoration:none; }
  @media print { h1,h2,h3,h4{page-break-after:avoid;} table,pre,.mermaid{page-break-inside:avoid;} }
</style></head><body>
<div id="content">Rendering...</div>
<script type="text/markdown" id="src">
PUT THE FINISHED MARKDOWN HERE
</script>
<script src="https://cdn.jsdelivr.net/npm/marked/marked.min.js"></script>
<script>
  document.getElementById('content').innerHTML = marked.parse(document.getElementById('src').textContent);
  document.querySelectorAll('pre code.language-mermaid').forEach(c=>{const d=document.createElement('div');d.className='mermaid';d.textContent=c.textContent;c.closest('pre').replaceWith(d);});
</script>
<script type="module">
  import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@10/dist/mermaid.esm.min.mjs';
  mermaid.initialize({startOnLoad:false, theme:'neutral'}); mermaid.run({querySelector:'.mermaid'});
</script>
</body></html>
```

### Print command (headless Chrome)
```
"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" \
  --headless=new --disable-gpu --no-pdf-header-footer \
  --virtual-time-budget=30000 --run-all-compositor-stages-before-draw \
  --user-data-dir=/tmp/chrome-pdf \
  --print-to-pdf="OUT.pdf" "file:///ABSOLUTE/PATH/TO.html"
```
The `--virtual-time-budget` gives the web font and the diagram time to load before printing.

## Checklist before submitting
- [ ] David 12pt, 1.5 spacing, justified.
- [ ] Headings same size as the body, bold/underline only.
- [ ] No horizontal rules, no em dashes, straight quotes.
- [ ] No bold-bullet lead-ins.
- [ ] No code block clipped at the right edge (shorten long lines if so).
- [ ] Final file scanned against references/ai-slop.md sections 15-16.
