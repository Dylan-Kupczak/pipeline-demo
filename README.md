# pipeline-demo

Pipeline CI qui build une image Docker, la scanne, et ne la publie que si les checks sont verts.

Trois jobs :

- Gitleaks : bloque un secret commité
- Semgrep : analyse le code Python
- Trivy : scanne l'image, une faille HIGH bloque le job

L'image n'est poussée sur ghcr.io qu'après un merge sur master, une fois les trois jobs verts. Une pull request build et scanne, elle ne publie pas pour l'instant.

Image : `ghcr.io/dylan-kupczak/pipeline-demo`
