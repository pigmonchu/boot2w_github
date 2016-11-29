#Soluciones
##Ejercicio 1

- **¿Qué comando utilizaste en el paso 11? ¿Por qué?**

	`git reset --hard HEAD~1`

	Con este comando deshago el commit y me deja los ficheros tal y como estaban cuando se realizó el commit previo al que he deshecho.
- **¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?**

	~~~
git reflog
git reset --hard 0643641
~~~
	He preferido retomar literalmente el commit deshecho en 11 que volver a modificar el fichero y rehacer el commit. Me parece un poco matar moscas a cañonazos, pero era lo más rápido.
	- **El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?**
	No causó conflicto. Dió el mensaje *Already up-to-date*. No hay nada que fusionar, *styled* va por delante de master, así que la incluye.
- **El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?**
	Sí, causó el siguiente conflicto
	
	~~~
	Auto-merging git-nuestro.md
CONFLICT (content): Merge conflict in git-nuestro.md
Automatic merge failed; fix conflicts and then commit the result.
	~~~
	
	Porque tanto *styled* como *htmlify* parten de *master* y modifican en los mismos puntos del fichero. Git no puede saber cual de las modificaciones prevalece y avisa al usuario para que lo resuelva. 

	> Al resolver el conflicto queda un `<br />` ya que esta linea sólo cambia en htmlify -- No se si es lo que se quiere pero lo dejo

- **El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?**

	No. Hizo un fast forward, ya que una vez resueltos los conflictos volvemos a la situación anterior: *styled* simplemente va por delante de master, así que lo que hace git es adelantar el puntero de master.
	
- **¿Qué comando o comandos utilizaste en el paso 25?**
	
	`git log --graph`

- **El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?**

	Si, ya que no hay commits que puedan perderse.

- **¿Qué comando o comandos utilizaste en el paso 27?**	
	`git reset HEAD~1`	- **¿Qué comando o comandos utilizaste en el paso 28?** 

	`git chechout git-nuestro.md`
	
- **¿Qué comando o comandos utilizaste en el paso 29?**

	`git branch -D title`

- **¿Qué comando o comandos utilizaste en el paso 30?** 

	Tengo el siguiente alias 
	`alias.graph=log --graph --oneline --decorate`
	
	
	`git reflog` ➤ busco el commit en que se hace el merge de title en master (9da7935)
	
	`git reset --hard 9da7935` ➤ Estoy donde quiero pero me falta la rama title. Su commit está, pero no el puntero.
	
	`git graph` ➤ busco el commit de la rama title, para crear allí el puntero de la rama title (4515015)
	
	`git checkout 4515015 -b title` ➤ "creo" la rama title en el commit 4515015
	
	`git checkout master` ➤ vuelvo a donde estaba
	
	`git graph` ➤ compruebo que está todo como debe

	
- **¿Qué comando o comandos usaste en el paso 32?**	`git reset --hard HEAD~3`	- **¿Qué comando o comandos usaste en el punto 33?**

	~~~
	git reflog
	git reset --hard 9da7935
	~~