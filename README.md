# Twemoji-Converted
Twemoji but the filenames are converted from codepoints to be human readable and easily searchable.

## Script source code (Python)
```py
import os
import fitz
from svglib.svglib import svg2rlg
from reportlab.graphics import renderPDF

input_dir = 'name_converted\\1689431952'
output_dir = 'png'

for filename in os.listdir(input_dir):
    if filename.endswith('.svg'):
        input_path = os.path.join(input_dir, filename)
        output_path = os.path.join(output_dir, filename.replace('.svg', '.png'))
        
        drawing = svg2rlg(input_path)
        pdf = renderPDF.drawToString(drawing)

        doc = fitz.Document(stream=pdf)
        pix = doc.load_page(0).get_pixmap(alpha=True, dpi=1024)
        pix.save(output_path)
```
