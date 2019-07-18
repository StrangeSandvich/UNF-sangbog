# Files for the creation of the CSC 2019 songbook
Den er rimelig hacky, men hvis du vil adaptere denne til at lave en sangbog skal du:

Lave en fork og hente repo ned. 
Vælge sange ved at ændre hvilke sange der bliver inputtet i unf-sangbog.tex
Slet de eksisterence /newpage hack kommandoer
Hvis du vil tilføje din egen sang så lav en kopi af template i songs mappen og adapter
Sørg for at "Fulbert og Beatrice" er nummer 12 (Vi sørger for at den er på side 10 senere)
Sørg for at "I morgen er verden vor" er nummer 42 og at DAT62 er nummer 43

Ændr forside, footer, header og side 2 til at reflektere den nye bog

Compiler sangbogen ved brug af "pdflatex unf-sangbog.tex". 
Hvis du ikke har pdflatex så skal du på Linux bruge apt til at få texlive-latex-extra og texlive-science
Hvis du har Windows/Mac/Distro uden apt så find selv ud af det.

Kør derefter "./mksbtdx unf-sangbog" for at generere indholdsfortegnelse og index. Hvis filen ikke vil køre så giv den tilladelse. Hvis dit styresystem ikke kan finde ud af at køre den så find selv ud af det. Og kør pdflatex igen for at indsætte den nye indholdsfortegnelse og index. Hvis den brokker sig så tryk bare enter, vi fikser det om lidt. Hvis den nye indholdsfortegnelse flytter sidenumre skal du køre mksbtdx igen.

Tjek sidetallene omkring "Fulbert og Beatrice". Hvis sidetallet ikke er 10 skal "\fancyhead[CE,CO]{\CHeadFont\thepage}" linjen flyttes en sang længere ned. 

Find alle de sider hvor at en sang starter først på den side. Tjek indholdsfortegnelsen og du vil nok finde at sidetallet for sangen er forkert. Fix dette ved at gå ind og lave \newpage før alle sange med forkert sidetal. Kør mksbtdx igen for at opdatere indholdsfortegnelsen og pdflatex igen. Tjek at sidetallene passer for alt undtagen side 10. 

Gå ind i unf-sangbog.toc og fix alle titler hvor der bliver brugt \TeX. Ændr sidetallet for Fulbert og Beatrice og alle sange som starter på samme side som den til 10
Gå ind i unf-sangbog.tdx og fjern "\begin{theindex}" og "\end{theindex}". Fix også alle titler hvor der bliver brught \TeX
Kør mksbtdx og pdflatex igen, tjek at der ikke er to index titler, at sange med \TeX i titlen er vist i index og indholdsfortegnelse. Tjek at Fulbert og Beatrice m.m. står til side 10. 
Tilføj sektionerne ind i indholdsfortegnelsen i tocx. Hvis de gør at indholdsfortegnelsen fylder ud på endnu en side er der en masse sidetal der igen skal fixes. 

Gå ind i unf-sangbog.ptc og fix sidetal for Fulbert og Beatrice m.m.
Noter at .ptc nulstiller sidetal efter at pdflatex er kørt

Kør pdflatex igen og bogen skulle nu være komplet.

For at printe brugte vi "hæfte" funktionen i adobe acrobat. 