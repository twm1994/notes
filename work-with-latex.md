### hyperref, use latex command
`\texorpdfstring{}{}`

when using the elsarticle template with \corref{}
`\hypersetup{pdfauthor=author}`

### overful/underful \hbox
```latex
\usepackage{microtype}

% use in table environment
% \arraybackslash returns to normal controls (too lazy to put explaination here)
\raggedright\arraybackslash 
```

### minimum margins
`\usepackage{fullpage}`

### multiline formula, align by `=`, use the `align` environment
