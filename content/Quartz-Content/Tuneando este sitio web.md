---
title: "Tuneando este sitio web"
enableToc: True
cssclass: wide-table
author: 
tags: guía
aliases: 
type: 
date: 2023-05-23-Tue 23:47
---

[[Quartz]] es la plantilla que he utilizado para tener este sitio web, puede que le haga falta algunos retoques para personalizarlo al gusto.

Por defecto se ve bien pero hay algunas cosas que prefiero cambiar empezando por..


## Headings

Los _headings_ en inglés son simplemente los títulos que sirven para organizar el contenido, entre más `#`  usemos significará una menor jerarquía dentro de los subtítulos

![[Quartz-Content/quartz-media/Pasted image 20230524133441.png]]


El símbolo de _gato_ prefiero que no sea visible... ¿Cómo cambiamos esto?


### Aquí trato de resolver eso


Una forma es bajar la opacidad del símbolo en el archivo `assets/styles/base.scss`, a un valor cercano a cero.
![[Quartz-Content/quartz-media/Pasted image 20230530231936.png]]

_Sin embargo..._ ese espacio extra de ocultar el "#" puede no verse bien.  Pero ya es algo.


> [!info] Tabla de contenidos
> 
> Otra cosa a tener en cuenta al utilizar headings es que si utilizamos el header 1 (#) este no aparecerá en la ToC porque se espera que ese header solo se utilice para el título del blog, o eso creo

## Imágenes
El autor de Quartz recomienda utilizar Obsidian como editor para las notas, esto hace las cosas prácticas y por mucho. Sin embargo llevo un tiempo usando Obsidian y todas las notas que tengo ahí no quiero publicarlas por el contenido personal, metas, ideas etc etc. _¿Mi solución?_, sincronizar un directorio solamente en mi _vault_ de obsidian hacia el directorio que subirá todo a github, de donde se construye todo el sitio web ¡Genial!

![[Quartz-Content/quartz-media/Pasted image 20230524133420.png]]

Ahora sólo hay que resolver otro detalle dentro de obsidian y es que
- Ya tengo una ubicación por defecto para todos los archivos multimedia dentro de mi _vault_ 
- No quiero que se sincronicen todos los archivos.. sólo los que necesita el blog. 

### Aquí trato de resolver eso 
Hay una solución simple pero a la larga puede llegar a ser impráctica, hay que seleccionar _temporalmente_ el directorio para los archivos multimedia, y cuando ya no sea necesario usarlos ahí o se tenga que usar archivos más sensibles regresar la ubicación por defecto a la anterior.

![[Quartz-Content/quartz-media/Pasted image 20230524121953.png]]

**¿Hay otras opciones?**
Sí, este mismo proceso debería ser posible de activar con un _hotkey_ el cual haga toggle de la carpeta por defecto.

También podrían haber otras opciones más complicadas que involucren hacer scripts los cuales detecten que cuando hayan imágenes se pongan estas imágenes en el directorio deseado y se actualice el hipervínculo, honestamente es más probable que termine haciendo un desastre y no sea práctico a parte de lleavar demasiado tiempo innecesariamente, tampoco se pierde mucho tiempo haciendo unos cuantos clicks.

## Idioma

Por defecto están en inglés, no es algo que me moleste pero puede quitar algo de carácter que todo esté en _spanglish_.
El idioma se edita en el archivo `config.toml`
![[Quartz-Content/quartz-media/Pasted image 20230531180439.png]]


## Colores

Puede que no sea necesario, los colores que traen son _esenciales_, no molestan, son agradables pero tampoco llaman mucho la atención lo cual puede ser una ventaja, dependiendo.

Lo que si considero muy útil con respecto a los colores es el color de los [[Quartz-Content/Tuneando este sitio web#Headings|Headings]], es algo que utilizo de manera frecuente para captar la jerarquía más rápido.

### Añadiendo colores
Hay que editar el archivo `custom.scss` en `/assets/styes`


> [!NOTE]- Distribución de colores, de acuerdo a la jerarquía de los headers (#)
> 
> ![[Quartz-Content/quartz-media/Pasted image 20230531153301.png]]
>  
> `# nivel 1`
> 
> `## nivel 2`
> 
> `### nivel 3`
> 
> `#### nivel 4`
> 
> `##### nivel 5`
> 
> `###### nivel 6`
> 

![[Quartz-Content/quartz-media/Pasted image 20230531000907.png]]

Una vez añadidos los colores tenemos que configurarlos en `base.scss`, para más detalles me guié un poco de este  [fork](https://github.com/pietraferreira/quartz/blob/hugo/assets/styles/base.scss) de quartz.
### Aquí trato de personalizar algunos colores

[Styling](https://quartz.jzhao.xyz/notes/config/#styling)
Para cambiar los colores hay que hacer un archivo `custom.scss`

![[Quartz-Content/quartz-media/Pasted image 20230524233321.png]]

Podemos escoger un esquema de colores o _inspirarse_ de otros blogs con colores que nos agraden y cambiarlos después.

## Zotero y referencias cruzadas.
Zotero es una herramienta increíble para algo específico, recopilar referencias y utilizar esta base para generar conocimiento. 

Generalmente si me encuentro con un artículo interesante, o un vídeo de youtube que encuentro útil para después uso su extensión del navegador, solo con eso se guarda la info más importante en zotero. Después si quiero ahondar más en el tema utilizo obsidian donde directamente puedo importar las notas de zotero y añadir contenido adicional, también se puede utilizar zotero para escribir _papers_ o reportes ya que gestiona toda tu bibliografía y referencias.

El punto es, ¿Cómo citar una referencia que sea funcional para el blog, pero que siga siendo útil en mi uso cotidiano de obsidian?

### Entendiendo mejor el plugin zotero-integration (obsidian)


## Callouts
Para que los _callouts_ se renderizen bien, es necesario agregar un espacio después del título

> [!quote] ~Shakespare
>
> ...Aprenderás...

![[Quartz-Content/quartz-media/Pasted image 20230524132959.png]]

> [!example]- Todos los tipos de callouts disponibles hasta ahora
> 
> > [!EXAMPLE] Examples
> >
> > Aliases: example
> 
> > [!note] Notes
> >
> > Aliases: note
> 
> > [!abstract] Summaries 
> >
> > Aliases: abstract, summary, tldr
> 
> > [!info] Info 
> >
> > Aliases: info, todo
> 
> > [!tip] Hint 
> >
> > Aliases: tip, hint, important
> 
> > [!success] Success 
> >
> > Aliases: success, check, done
> 
> > [!question] Question 
> >
> > Aliases: question, help, faq
> 
> > [!warning] Warning 
> >
> > Aliases: warning, caution, attention
> 
> > [!failure] Failure 
> >
> > Aliases: failure, fail, missing
> 
> > [!danger] Error
> >
> > Aliases: danger, error
> 
> > [!bug] Bug
> >
> > Aliases: bug
> 
> > [!quote] Quote
> >
> > Aliases: quote, cite
> 




## Añadiendo info extra a la página de inicio

Un buen inicio es añadir las _notas recientes_, esto se activa colocando el valor `true` dentro de `data/config.yaml` en quartz

![[Quartz-Content/quartz-media/Pasted image 20230524134416.png]]

De todas maneras quiero estadísticas!

Algo que muestre el número de notas totales en el jardín digital, de ser posible un índice estilo wikipedia ordenado en orden alfabético con todos los temas, eso añadido con _graph view_ debería ser suficiente por el momento.

Después de indagar un poco la [pág. de Jacky](https://jzhao.xyz/) tiene a su costado izquierdo info adicional de notas... esto se puede habilitar en..


### Tags
![[Quartz-Content/quartz-media/Pasted image 20230530223100.png]]

Podemos agregar los tags que queramos en el header de YAML en nuestra nota de obsidian, de preferencia en el formato mostrado en la captura y no con comas.

Otra cosa a tener en cuenta es que si queremos tener información útil cuando presionemos un tag, debemos crear los archivos acerca de estos en `/content/tags/<nombre_del_tag>/_index.md`
![[Quartz-Content/quartz-media/Pasted image 20230530223359.png]]

### Agregando tags en la página de inicio

A diferencia de obsidian en donde se pueden usar los tags en cualquier parte del documento, en Quartz tenemos que definirlos en el header de YAML de cada nota.

La opción que se suele tomar es utilizar MoC's o mapas de contenidos, los cuáles son simples notas con hipervínculos hacía diferentes temas organizados por diferentes categorías.

En el blog _Data Glossary_ está la opción de mostrar todos los tags con el ícono que aparece a un lado del modo oscuro.

![[Quartz-Content/quartz-media/Pasted image 20230531145452.png]]

Si queremos agregar esto, hemos de modificar dos archivos en `/layouts/partials`:
- `header.html`
- `tags.html`

El archivo `tags.html` es necesario crearlo en caso de que no exista, de referecia se puede usar el material de layouts en [Data Glossary](https://github.com/airbytehq/glossary/tree/hugo/layouts/partials)


## Inspiración 
Quartz tiene más de 1500 forks en github, no todos son activos pero los que son pueden servir de inspiración, aquí una lista


- [Morioh](https://pietraferreira.github.io/quartz/) [git](https://github.com/pietraferreira/quartz)
	- Interesante esquema de colores
	- Uso útil de graph view
	- Buena organización
 -  [vrakonor](https://vrak.konor.fr/) 
	 - Los colores no me agradan pero parece una buena forma de poner la presentación.
	 - Comentarios con github en los posts.. interesante.
- [brain](https://brain.aalexmmaldonado.com/)
	- Grandes cambios en la apariencia
	- Resuelve el detalle con los [[Quartz-Content/Tuneando este sitio web#Headings|Headings]]
	- Organización simple y útil.
	- Está basado en [hugo-book](https://github.com/alex-shpak/hugo-book)
	 - [x] Encontrar la parte que corresponda a los headings e implementarla ✅ 2023-05-30
 - [Data Glossary](https://glossary.airbyte.com/)
	 - Fantástico uso de colores
	 - Configuración atractiva de graphview
	 - Espacio de escritura más ancho
	 - Organizado en la pag frontal.
	 - Backlinks a la derecha
	 - Moradito