# hg38 switch

hg19 to hg38 switch: reasons, pitfalls, ...

**Pro hg38**

* manche Konsortialzentren sind bereits umgestiegen (T�bingen, wer noch?) 
* Datenbanken/Tools die nur noch hg38 unterst�tzen:
	* Ensembl gene/transcript defininitions newer then 2014
	* MANE Transkripte
	* gnomAD 3.x

**Contra hg38**

* CanRisk PRS Definition nur f�r hg19 (lift-over ist aber m�glich)
* HerediVar hg19-basiert
* Schnittstellen zu anderen Tools k�nnnen ein Problem sein, z.B. zu Tools f�r Primerdesign und 


**Beispielvorgehen in T�bingen**

1) Zun�chst wurde zuerst die Analysepipeline umgestellt:

* Referenzgenom umgestellt
* Alle Datenbanken/Tools umgestellt
* Alle Koordinaten/VCFs die in der Pipeline benutzt werden umgestellt (PAR, Centromere, Telomere, SRY, ...)

2) Nach der Umstellung der Pipeline wurden alle Proben basierend auf hg38 neu gerechnet.

3) Dann wurde versucht alle von Hand kurierten Daten (Klassifikationen, Kommentare, ...) der hg19-Proben per Lift-over auf die Varianten in hg38 zu transferieren:

* kleine Varianten (SNVs und InDels) konnten zu ca. 98% �bertragen werden.
* Readtiefe-basierte CNVs konnten zu ??% �bertragen werden (hier gibt es oft Probleme mit abweichenden Calls aufgrund von Rauschen in den Tiefendaten).
* SVs konnten zu ??% �bertragen werden.
