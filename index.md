Welcome to the Mathwiki! Choose an article on the left side to start learning.
## Recently modified pages
```dataview
TABLE WITHOUT ID
	link(file.path, file.folder + "/" + file.name) AS "Page",
	dateformat(file.mtime, "yyyy-MM-dd, HH:mm") AS "Last Modified"
FROM ""
WHERE file.mtime >= date(today) - dur(30 days)
AND file.name != this.file.name
	AND !contains(file.path, "z_attachments")
	AND !contains(file.path, "z_templates")
SORT file.mtime DESC
LIMIT 10
```

## To do list
 - [ ] Finish proofs in [[Integration on Manifolds]]
 - [ ] Define [[Lie Derivatives]] for arbitrary tensor fields
 - [ ] Prove the embeddding theorem in [[Smooth Function]]
 - [ ] Add Riemann Surfaces article (in algebraic geometry)
 - [x] Add and prove Yoneda lemma
 - [x] Define bundles, especially vector bundles
 - [ ] Add nicer index page
 - [x] Add folder notes to fields to introduce the reader
 - [ ] Define pullback on tensor fields
 - [ ] Add gauge theories
 - [ ] Do proof in [[Adjoint]].