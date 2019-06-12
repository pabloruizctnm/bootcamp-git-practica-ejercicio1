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

**- El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?**

`git merge master`

No causó conflictos porque se absorbe la rama master en la rama styled. La rama master está al menos un commit por detrás, y además "en linea". Es decir, no se ha trabajado en la rama master desde que se dejó para hacer cambios en la rama styled.

**- El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?**

En este caso hemos hecho:
 
 `git merge htmlify` desde styles
 
 Y por supuesto que causa conflictos. Hemos modificado varias de las líneas de un mismo documento desde dos ramas diferentes al mismo tiempo.
 
 **- El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?**
 
 En este caso hemos hecho:
  
  `git merge styles` desde master
  
 En esta ocasión no causa conflictos porque master estaba actualizada a la rama styles; y habíamos conservado los cambios de la rama styles cuando la mergeamos con htmlify.
  
 
**- ¿Qué comando o comandos utilizaste en el paso 25?**
 
  `git log --graph --decorate --pretty=oneline`
  
  Con 'graph' se muestra el gráfico.<br>
  Con 'decorate' se muestran los punteros.<br>
  Con 'pretty=oneline' se muestran los commit en una línea
  
**- El merge del paso 26, ¿Podría ser fast forward?¿Por qué?**

Sí que podría ser fast forward ya que la rama master no había cambiado durante el trabajo en la rama title. Es decir, el merge puede generar un commit "en linea" de la rama master sin ningún problema.  
  