**- ¿Qué comando utilizaste en el paso 11? ¿Por qué?**

`git reset --hard HEAD~1`

Use reset porque es lo que se usa para deshacer commits. <br>
Use --hard para indicar que no quería conservar los cambios en el working copy. <br>
Use HEAD~1 para irme 1 commit anterior. Podría haber usado la referencia del commit por ejemplo.

**- ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?**

`git reflog`

Gracias a este comando, puedo ver un histórico de todos las actualizaciones que he ido haciendo en git en orden cronológico. Me queda algo como lo siguiente: <br>

4b6cb3c (HEAD -> styled, master) HEAD@{0}: checkout: moving from results to styled<br>
d99426a (results) HEAD@{1}: commit: Añado la carpeta .idea. Si no me equivoco, la genera el editor de texto PhpStorm. No es importante en este caso<br>
a8a310e HEAD@{2}: commit: Añado la respuesta a la pregunta 1 - paso 11<br>
4b6cb3c (HEAD -> styled, master) HEAD@{3}: checkout: moving from master to results<br>
4b6cb3c (HEAD -> styled, master) HEAD@{4}: checkout: moving from styled to master<br>
4b6cb3c (HEAD -> styled, master) HEAD@{5}: reset: moving to HEAD~1<br>
c7bf460 HEAD@{6}: commit: Añado estilo al fichero git-nuestro.md<br>
4b6cb3c (HEAD -> styled, master) HEAD@{7}: checkout: moving from master to styled<br>
4b6cb3c (HEAD -> styled, master) HEAD@{8}: commit (initial): Añado git-nuestro.md<br>

De tal forma, busco el commit que me interesa y vuelvo a hacer un reset, como en la pregunta 11.

`git reset --hard c7bf460`

En este caso uso de nuevo --hard para desechar mi working copy y recuperar el antiguo.<br>
Uso el identificador del commit c7bf460, que es donde había añadido el estilo al fichero git-nuestro.md.


