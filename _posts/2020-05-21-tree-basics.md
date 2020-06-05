---
layout: post
title:  "🌳 Árboles 🌳"
subtitle : "Estructuras de datos: Árboles"
tags: [Data Structures]
author: Tania R. Zúñiga
comments : true
---

Un árbol es una estructura de datos no lineal que colecciona elementos llamados nodos. Este se caracteriza por imponer una estructura jerárquica en un conjunto de datos.

<br>

<h3>Terminología</h3>

Uno de los nodos del árbol es llamado **raíz** (*root*), se caracteriza por no tener ascendencia (no tiene padre).  El descendiente de un nodo es llamado **hijo** (*child*). La conexión entre dos nodos es llamada "**relación de paternidad**" o *edge*.

<br>

>**Ojo 👀**
>
>Un nodo puede tener ***n*** hijos, ***n*** es un número entero positivo. No nos estamos limitando a Arboles Binarios, por ahora.

<br>

Los nodos que pertenecen al mismo padre son **hermanos** (*siblings*). Por ejemplo, en la **Imagen 1** de abajo vemos como los nodos G, H I son hermanos. Por otro lado, el nodo F no tiene hermanos.

<br>

Una **hoja** (*leaf*) es un nodo que no tiene hijos. En nuestro ejemplo, los nodos F, K, D y J son hojas.

<br>

La **altura** (*height*) de un nodo es el numero total de *edges* desde un nodo en particular hasta la hoja más lejana. La altura de un árbol, es la altura de su raíz. Por ejemplo, la altura del *Árbol azul* es tres.

<br>

Por otro lado, la **profundidad** (*depth*) de un nodo es el número total de *edges* desde la raíz hasta un nodo particular. Por ejemplo, la profundidad del nodo J es dos.

<br>

En un árbol, la raíz siempre está en el Nivel 0 y los hijos de la raíz están en el Nivel 1 y los hijos de los nodos que están en el Nivel 1 estarán en el Nivel 2 y así sucesivamente. Del lado derecho del *Árbol azul* se denota el nivel correspondiente.

<br>

![arbol azul]({{ site.baseurl }}/assets/img/DataStructures/tree/blue_tree.svg) **Imagen 1**: *Árbol azul*, indicando partes del árbol.

<br>

<h2>Recorrido de árboles</h2>

Hay diversas formas de recorrer todos los nodos de un árbol. Explicaré en pseudocódigo los cuatro recorridos más comunes. Para ello vamos a tomar en cuenta que los nodos de nuestro árbol tienen los siguientes métodos:

<h6>INodo (Interfaz Nodo)</h6>

- **Padre()**: Devuelve el nodo que es padre. Si el iNodo es la raíz, la cual no tiene padre, se devuelve un valor indeterminado.

- **hijoIzquierdo()**: Devuelve el nodo hijo que está más a la izquierda. Si el INodo es una hoja, devuelve un valor indeterminado por no tener hijos.

- **hermanoDerecho()**: Devuelve el nodo hermano que está inmediatamente a la derecha. Por ejemplo, en el *Árbol azul*, el hermano derecho de G es H. Si el INodo no tiene hermano derecho, es decir, es el hijo más a la derecha de su padre, devuelve un valor indeterminado.

- **obtenerValor()**: Devuelve la información almacenada en el INodo.


<script src='https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.5/MathJax.js?config=TeX-AMS_CHTML'>
</script>
<script type="text/x-mathjax-config">
    MathJax.Hub.Config({
        tex2jax: {
            inlineMath: [['$','$'], ['\\(','\\)']],
            displayMath: [['$$','$$'], ['\[','\]']],
            processEscapes: true,
            processEnvironments: true,
        }
    });
</script>

<br>

<h3>Preorden</h3>

<pre id="preorden" style="display:hidden;">
\begin{algorithm}
\caption{Preorden}
\begin{algorithmic}
\FUNCTION{Preorden}{INodo $n$}
    \IF{ $n$ es valido } 
        \STATE \CALL{Listar}{ $n.obtenerValor( )$ }
        \STATE \CALL{Preorden}{ $n.hijoIzquierdo( )$ }
        \STATE \CALL{Preorden}{ $n.hermanoDerecho( )$ }
    \ENDIF
\ENDFUNCTION
\end{algorithmic}
\end{algorithm}
</pre>

<br>

Si recorremos el *Árbol azul* en Preorden obtendremos: \[A, B, F, C, G, K, H, I, D, E, J\]

<br>

<h3>Inorden</h3>

<pre id="inorden" style="display:hidden;">
\begin{algorithm}
\caption{Inorden}
    \begin{algorithmic}
    \FUNCTION{Inorden}{INodo $n$}
        \IF{ $n.hijoIzquierdo( )$ no es valido } 
            \STATE \CALL{Listar}{$n.obtenerValor( )$ }
        \ELSE
            \STATE \CALL{Inorden}{$n.hijoIzquierdo( )$}
            \STATE \CALL{Listar}{$n.obtenerValor( )$ }
            \STATE $h = n.hermanoDerecho( ) $
            \WHILE{ $h$ sea valido }
                \STATE \CALL{Inorden}{$h$}
                \STATE $h = n.hermanoDerecho( ) $
            \ENDWHILE
        \ENDIF
    \ENDFUNCTION
    \end{algorithmic}
    \end{algorithm}
</pre>

<br>

Si recorremos el *Árbol azul* en Inorden obtendremos: \[F, B, A, K, G, C, H, I, D, J, E\]

<br>

<h3>Postorden</h3>

<pre id="postorden" style="display:hidden;">
\begin{algorithm}
\caption{Inorden}
    \begin{algorithmic}
    \FUNCTION{Postorden}{INodo $n$}
        \IF{ $n$ es valido } 
            \STATE \CALL{Postorden}{$n.hijoIzquierdo( )$}
            \STATE \CALL{Listar}{$n.obtenerValor( )$ }
            \STATE \CALL{Postorden}{$n.hermanoDerecho( )$}
        \ENDIF
    \ENDFUNCTION
    \end{algorithmic}
    \end{algorithm}
</pre>

<br>

Si recorremos el *Árbol azul* en Postorden obtendremos: \[F, B, K, G, H, I, C, D, J, E, A\]

<br>

<h3>Por nivel</h3>

<pre id="nivel" style="display:hidden;">
\begin{algorithm}
\caption{Level Order}
    \begin{algorithmic}
    \FUNCTION{Nivel}{INodo $n$}
        \STATE Queue $q$
        \STATE $q.enqueue(n)$
        \WHILE{ $q$ tenga elementos }
            \STATE $root = q.dequeue( ) $
            \STATE \CALL{Listar}{$root.obtenerValor( )$ }
            \STATE $hijo = root.hijoIzquierdo( ) $
            \WHILE{ $hijo$ sea valido }
                \STATE $q.enqueue(hijo)$
                \STATE  $hijo = hijo.hijoIzquierdo( ) $
            \ENDWHILE
        \ENDWHILE
    \ENDFUNCTION
    \end{algorithmic}
    \end{algorithm}
</pre>

<br>

Si recorremos el *Árbol azul* por Nivel obtendremos: \[A, B, C, D, E, F, G, H, I, J, K\]


<script>
    pseudocode.renderElement(document.getElementById("preorden") );
    pseudocode.renderElement(document.getElementById("inorden"), {indentSize: '3em'});
    pseudocode.renderElement(document.getElementById("postorden") );
    pseudocode.renderElement(document.getElementById("nivel"), {indentSize: '3em'});
</script>


<h6>¿Por qué usas spanglish?</h6>

Para estar familiarizados con los términos tanto en inglés, como en español.

```root == raíz ```

```si... entonces == if... then```








