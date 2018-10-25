---


---

<h1 id="variables">Variables</h1>
<h2 id="floats"><em>Floats</em></h2>
<blockquote>
<p>Les floats sont écrits avec un point. Attention, les floats et les entiers ne peuvent pas être utilisés ensemble dans un calcul.</p>
</blockquote>
<p>Les floats ont leur propres opérateurs :</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token number">3</span> <span class="token operator">+</span> <span class="token number">1</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
<span class="token number">3.0</span> <span class="token operator">+.</span> <span class="token number">1.5</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<h2 id="booleans"><em>Booleans</em></h2>
<blockquote>
<p>Les opérateurs <code>&lt;</code>,<code>&gt;</code>,<code>=</code>, etc., sont aussi des fonctions infix.<br>
La négation d’un booléen se fait avec <code>not</code>. Le <em>ET</em> et le <em>OU</em> se font avec <code>&amp;&amp;</code> et <code>||</code>.</p>
</blockquote>
<p>Le <code>if</code> est une expression et peut être utilisée n’importe où tant que les types sont compatibles :</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token number">100</span> <span class="token operator">+</span> <span class="token punctuation">(</span><span class="token keyword">if</span> a <span class="token operator">&gt;</span> b <span class="token keyword">then</span> <span class="token number">5</span> <span class="token keyword">else</span> <span class="token operator">-</span><span class="token number">5</span><span class="token punctuation">)</span> <span class="token operator">*</span> <span class="token number">10</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<h2 id="strings-chars"><em>Strings, chars</em></h2>
<blockquote>
<p>Les strings sont écrits entre guillemets (<code>"mot"</code>) et les caractères entre apostrophes (<code>'a'</code>).</p>
</blockquote>
<p>On peut accéder aux caractères d’un string :</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> s <span class="token operator">=</span> <span class="token string">"Toto"</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
s<span class="token punctuation">.</span><span class="token punctuation">[</span><span class="token number">0</span><span class="token punctuation">]</span><span class="token punctuation">;</span><span class="token punctuation">;</span> <span class="token comment">(* char = 'T' *)</span>
</code></pre>
<p>Pour concaténer des chaines, on utilise l’opérateur <code>^</code>.</p>
<h2 id="unit"><em>Unit</em></h2>
<blockquote>
<p><code>unit</code> correspond au type <code>void</code> en C ou en Java. C’est le type des fonctions qui ne renvoient rien.</p>
</blockquote>
<h2 id="tuples"><em>Tuples</em></h2>
<blockquote>
<p>Un tuple est une collection “d’objets” ordonnée.</p>
</blockquote>
<p>Elle peut contenir plusieurs types d’éléments en même temps.</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token punctuation">(</span><span class="token number">2</span><span class="token punctuation">,</span> <span class="token number">4</span><span class="token punctuation">)</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
<span class="token punctuation">(</span><span class="token boolean">false</span><span class="token punctuation">,</span> <span class="token string">"toto"</span><span class="token punctuation">,</span> <span class="token operator">-</span><span class="token number">10</span><span class="token punctuation">)</span><span class="token punctuation">;</span><span class="token punctuation">;</span> <span class="token comment">(* bool * string * int *)</span>
<span class="token punctuation">(</span>add<span class="token punctuation">,</span> abs<span class="token punctuation">)</span><span class="token punctuation">;</span><span class="token punctuation">;</span> <span class="token comment">(* Tuple de fonctions *)</span>
</code></pre>
<p>Le type d’un tuple sera <code>element1 * ... * elementN</code>.<br>
On ne peut pas (par exemple) additionner directement des tuples (ce qui est logique car l’opérateur attend deux entiers et non pas des tuples d’entiers).</p>
<h2 id="lists"><em>Lists</em></h2>
<blockquote>
<p>Une liste est définie entre crochets, et ses éléments sont séparés par des points-virgules “;”.</p>
</blockquote>
<ul>
<li>
<p>Contrairement aux tuples, tous les éléments d’une liste doivent avoir le même type.</p>
</li>
<li>
<p><code>[]</code> est la liste vide.</p>
</li>
</ul>
<p><em>Attention de ne pas écrire une liste avec des virgules simples, ce qui reviendrait à définir un tuple !</em></p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> list <span class="token operator">=</span> <span class="token punctuation">[</span><span class="token number">1</span><span class="token punctuation">,</span><span class="token number">2</span><span class="token punctuation">]</span><span class="token punctuation">;</span><span class="token punctuation">;</span> <span class="token comment">(* (int * int) list = [(1,2)] *)</span>
</code></pre>
<p>On peut ajouter des éléments à une liste à l’aide de <code>::</code>.</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> l2 <span class="token operator">=</span> <span class="token number">7</span> <span class="token punctuation">:</span><span class="token punctuation">:</span> <span class="token number">6</span> <span class="token punctuation">:</span><span class="token punctuation">:</span> l1<span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<p>Attention, l’opérateur (::) ajoute un élément <em>(à gauche)</em> à une liste <em>(à droite)</em>. On ne peut donc pas écrire <code>l1 :: l1</code>.</p>
<p>On peut avoir des listes de listes : <code>[l1]</code>.  L’exemple suivant fonctionnera :</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> l1 <span class="token operator">=</span> <span class="token punctuation">[</span><span class="token number">2</span><span class="token punctuation">;</span><span class="token number">4</span><span class="token punctuation">]</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
<span class="token punctuation">[</span><span class="token number">6</span><span class="token punctuation">;</span><span class="token number">8</span><span class="token punctuation">]</span> <span class="token punctuation">:</span><span class="token punctuation">:</span> <span class="token punctuation">[</span>l1<span class="token punctuation">]</span><span class="token punctuation">;</span><span class="token punctuation">;</span> <span class="token comment">(* int list list = [[6; 8]; [2; 4]] *)</span>
</code></pre>
<h2 id="option"><em>Option</em></h2>
<p><em>(Voir les fonctions polymorphiques)</em></p>
<blockquote>
<p>Le type <code>'a option</code> est utilisé pour représenté une value qui a été initialisée (<code>Some x</code>) ou non initialisée (<code>None</code>).</p>
</blockquote>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> a <span class="token operator">=</span> None<span class="token punctuation">;</span><span class="token punctuation">;</span>
<span class="token keyword">let</span> b <span class="token operator">=</span> Some <span class="token number">10</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
<span class="token keyword">let</span> c <span class="token operator">=</span> Some <span class="token boolean">true</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<h2 id="types-paramétrés"><em>Types paramétrés</em></h2>
<blockquote>
<p>Un <strong>type paramétré</strong> est quelque chose qui a un type d’argument.</p>
</blockquote>
<p>C’est le cas par exemple des listes (exemple <code>int list</code>).</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> <span class="token type variable">'a</span> test <span class="token operator">=</span>
	<span class="token punctuation">{</span> fonc<span class="token punctuation">:</span> <span class="token punctuation">(</span><span class="token type variable">'a</span> <span class="token operator">-&gt;</span> int<span class="token punctuation">)</span> <span class="token punctuation">;</span>
	  arg<span class="token punctuation">:</span> <span class="token type variable">'a</span> <span class="token punctuation">;</span>
	  expect<span class="token punctuation">:</span> int <span class="token punctuation">}</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<h2 id="opérateurs"><em>Opérateurs</em></h2>
<blockquote>
<p><strong>+</strong> est un <strong>infix operator</strong> : il est placé juste après son premier argument.</p>
</blockquote>
<pre class=" language-ocaml"><code class="prism  language-ocaml">arg1 <span class="token operator">+</span> arg2
</code></pre>
<p>Un <strong>infix operator</strong> peut aussi être utilisé comme ceci :</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token punctuation">(</span><span class="token operator">+</span><span class="token punctuation">)</span> <span class="token number">5</span> <span class="token number">3</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<h1 id="fonctions">Fonctions</h1>
<h2 id="définition-dune-fonction"><em>Définition d’une fonction</em></h2>
<p>Une fonction se définit comme une variable :</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> f arg <span class="token operator">=</span> <span class="token punctuation">.</span><span class="token punctuation">.</span><span class="token punctuation">.</span> <span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<p>Il y a plusieurs façons de définir une fonction :</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> f <span class="token punctuation">(</span> <span class="token punctuation">(</span>x<span class="token punctuation">:</span>int<span class="token punctuation">)</span><span class="token punctuation">,</span> <span class="token punctuation">(</span>y<span class="token punctuation">:</span>int<span class="token punctuation">)</span> <span class="token punctuation">)</span> <span class="token operator">=</span>
	<span class="token keyword">if</span> y <span class="token operator">=</span> <span class="token number">0</span> <span class="token keyword">then</span> <span class="token number">0</span> <span class="token keyword">else</span> x <span class="token operator">/</span> y<span class="token punctuation">;</span>

<span class="token keyword">let</span> f <span class="token punctuation">(</span> <span class="token punctuation">(</span>x<span class="token punctuation">,</span>y<span class="token punctuation">)</span> <span class="token punctuation">:</span> int<span class="token operator">*</span>int <span class="token punctuation">)</span> <span class="token operator">=</span>
	<span class="token keyword">if</span> y <span class="token operator">=</span> <span class="token number">0</span> <span class="token keyword">then</span> <span class="token number">0</span> <span class="token keyword">else</span> x <span class="token operator">/</span> y<span class="token punctuation">;</span>

<span class="token keyword">let</span> f <span class="token operator">=</span> <span class="token keyword">function</span> <span class="token punctuation">(</span><span class="token punctuation">(</span>x<span class="token punctuation">,</span>y<span class="token punctuation">)</span> <span class="token punctuation">:</span> int<span class="token operator">*</span>int<span class="token punctuation">)</span> <span class="token operator">-&gt;</span>
	<span class="token keyword">if</span> y <span class="token operator">=</span> <span class="token number">0</span> <span class="token keyword">then</span> <span class="token number">0</span> <span class="token keyword">else</span> x <span class="token operator">/</span> y<span class="token punctuation">;</span>
</code></pre>
<p>On n’est pas obligé d’indiquer le type des arguments :</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> f <span class="token punctuation">(</span>x<span class="token punctuation">,</span>y<span class="token punctuation">)</span> <span class="token operator">=</span>
	<span class="token keyword">if</span> y <span class="token operator">=</span> <span class="token number">0</span> <span class="token keyword">then</span> <span class="token number">0</span> <span class="token keyword">else</span> x <span class="token operator">/</span> y<span class="token punctuation">;</span>

<span class="token keyword">let</span> f <span class="token operator">=</span> <span class="token keyword">function</span> <span class="token punctuation">(</span>x<span class="token punctuation">,</span>y<span class="token punctuation">)</span> <span class="token operator">-&gt;</span>
	<span class="token keyword">if</span> y <span class="token operator">=</span> <span class="token number">0</span> <span class="token keyword">then</span> <span class="token number">0</span> <span class="token keyword">else</span> x <span class="token operator">/</span> y<span class="token punctuation">;</span>
</code></pre>
<p><em><strong>Attention</strong>, dans la commande <strong><code>abs -10</code></strong>, <code>abs</code> considère le <code>-</code> comme l’argument de <code>abs</code>, de type <code>int -&gt; int</code>. Il y a donc une erreur car on attendait un <code>int</code>.</em></p>
<p><strong>Cas des fonctions sans argument</strong><br>
On peut définir et appeler une fonction sans argument de la façon suivante :</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> f <span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">=</span> <span class="token number">5</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
<span class="token keyword">let</span> f <span class="token operator">=</span> <span class="token punctuation">(</span><span class="token keyword">fun</span> <span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">-&gt;</span> <span class="token number">10</span><span class="token punctuation">)</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<p>Ne pas oublier les parenthèses lors de l’appel de la fonction :</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml">f <span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">;</span><span class="token punctuation">;</span> <span class="token comment">(* 10 *)</span>
</code></pre>
<h2 id="curryfication"><em>Curryfication</em></h2>
<p>Les fonctions précédentes étaient des fonctions <strong>uncurried</strong> (non curryfiées) car on ne pouvait pas séparer ses arguments.</p>
<p>Une fonction peut être définie “partiellement”. Prenons la fonction <code>add</code> qui ajoute deux nombres :</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> add x y <span class="token operator">=</span> x <span class="token operator">+</span> y<span class="token punctuation">;</span>
</code></pre>
<p>Cette fonction peut être appelée “en partie”. On parle alors de <strong>curryfication</strong>.</p>
<blockquote>
<p>La curryfication est la transformation d’une fonction à plusieurs arguments en une fonction à un argument qui retourne une fonction sur le reste des arguments.</p>
</blockquote>
<blockquote>
<p>Une fonction curryfiée prend un premier paramètre et retourne une autre fonction.</p>
</blockquote>
<pre class=" language-ocaml"><code class="prism  language-ocaml">add <span class="token number">100</span><span class="token punctuation">;</span>
</code></pre>
<p>Cet exemple va retourner une fonction de type <code>int -&gt; int</code>, car elle n’attend plus qu’un seul argument.</p>
<p>La curryfication permet l’application partielle : si on appelle la fonction curryfiée avec un argument, on récupère une fonction qui ajoute 100 à son argument.</p>
<blockquote>
<p>La fonction ainsi obtenue est appelée <strong>closure</strong>. C’est une fonction dont certains arguments ont déjà une valeur.</p>
</blockquote>
<p>Pour écrire la version non curryfiée d’une fonction, il suffit de “rassembler” les paramètres de cette fonction dans un tuple.</p>
<p><em>Note : le compilateur OCaml est optimisé pour les fonctions curryfiées.</em></p>
<h2 id="différence-entre--fun--et--function-"><em>Différence entre -fun- et -function-</em></h2>
<p><code>fun</code> et <code>function</code> permettent de définir des fonctions “de la même façon” :</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> incr <span class="token operator">=</span> <span class="token keyword">fun</span> x <span class="token operator">-&gt;</span> x <span class="token operator">+</span> <span class="token number">1</span> <span class="token punctuation">;</span><span class="token punctuation">;</span>
<span class="token keyword">let</span> incr <span class="token operator">=</span> <span class="token keyword">function</span> x <span class="token operator">-&gt;</span> x <span class="token operator">+</span> <span class="token number">1</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<ul>
<li>Avec <code>fun</code>, on peut définir une fonction (qui peut être curryfiée) :</li>
</ul>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> add <span class="token operator">=</span> <span class="token keyword">fun</span> x y <span class="token operator">-&gt;</span> x <span class="token operator">+</span> y<span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<ul>
<li>Avec <code>function</code>, on peut définir une fonction qui n’attend qu’un seul argument, mais celui-ci pourra être matché selon certains patterns.</li>
</ul>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> f <span class="token operator">=</span> <span class="token keyword">function</span>
	<span class="token operator">|</span> <span class="token punctuation">[</span><span class="token punctuation">]</span> <span class="token operator">-&gt;</span> <span class="token number">0</span>
	<span class="token operator">|</span> <span class="token punctuation">[</span>a<span class="token punctuation">]</span> <span class="token operator">-&gt;</span> <span class="token number">1</span>
</code></pre>
<p><em>(Le paramètre analysé dans le pattern matching n’est pas explicitement écrit.)</em></p>
<h2 id="lambdas"><em>Lambdas</em></h2>
<blockquote>
<p>Une <strong>lambda-fonction</strong>, ou <strong>fonction anonyme</strong>, est une fonction sans nom qui peut être utilisée directement.</p>
</blockquote>
<p>On peut par exemple la mettre dans une liste, dans un tuple…</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> lambda<span class="token punctuation">_</span>list <span class="token operator">=</span> <span class="token punctuation">[</span> <span class="token punctuation">(</span><span class="token keyword">fun</span> x <span class="token operator">-&gt;</span> x <span class="token operator">*</span> <span class="token number">2</span><span class="token punctuation">)</span> <span class="token punctuation">;</span> <span class="token punctuation">(</span><span class="token keyword">fun</span> x <span class="token operator">-&gt;</span> x <span class="token operator">*</span> <span class="token number">3</span><span class="token punctuation">)</span> <span class="token punctuation">]</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<p>On parle de <strong>lambda-calcul</strong>. Ainsi, l’écriture <code>λx.(x + 4)</code> correspond au code suivant :</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token punctuation">(</span><span class="token keyword">fun</span> x <span class="token operator">-&gt;</span> x <span class="token operator">+</span> <span class="token number">4</span><span class="token punctuation">)</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<h2 id="polymorphisme"><em>Polymorphisme</em></h2>
<blockquote>
<p>Un type polymorphique est un type qui n’est pas explicitement indiqué.</p>
</blockquote>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> mk<span class="token punctuation">_</span>list a b <span class="token operator">=</span> <span class="token punctuation">[</span> a <span class="token punctuation">;</span> b <span class="token punctuation">]</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<p>Dans cet exemple, rien n’indique si <code>a</code> et <code>b</code> sont des entiers, des strings, ou autre chose.<br>
Ils ont alors le type <code>alpha</code>, noté <code>'a</code> dans Ocaml (puis <code>'b</code>, <code>'c</code>, etc.).</p>
<h2 id="fonctions-récursives"><em>Fonctions récursives</em></h2>
<blockquote>
<p>Le type <code>list</code> est un type récursif.</p>
</blockquote>
<p>Une liste peut être :</p>
<ul>
<li>Vide (<code>[]</code>), aussi utilisée pour marquer la fin d’une liste ;</li>
<li>Ou contenir un élément et le reste de la liste : <code>x :: rest</code>.</li>
</ul>
<p>Une liste doit souvent être parcourue pour effectuer des opérations dessus. On pourrait le faire à l’aide d’un <code>while</code>, mais en programmation fonctionnelle, on préfère utiliser des <strong>fonctions récursives</strong>.</p>
<blockquote>
<p>Une boucle <code>while</code> peut toujours être remplacée par une fonction récursive.</p>
</blockquote>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> <span class="token keyword">rec</span> length <span class="token operator">=</span> <span class="token keyword">function</span>
	<span class="token operator">|</span> <span class="token punctuation">[</span><span class="token punctuation">]</span> <span class="token operator">-&gt;</span> <span class="token number">0</span>
	<span class="token operator">|</span> x <span class="token punctuation">:</span><span class="token punctuation">:</span> rest <span class="token operator">-&gt;</span> <span class="token number">1</span> <span class="token operator">+</span> length rest<span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<p>Cet exemple permet de calculer la longueur d’une liste à l’aide d’une fonction récursive. Le mot-clé <code>rec</code> doit être utilisé pour définir une fonction récursive.</p>
<p><em>Note : si on a un message d’erreur disant que la fonction récursive n’est pas connue (<code>Unbound value</code>), c’est que <code>rec</code> a certainement été oublié.</em></p>
<p>Une autre façon de définir une fonction récursive est d’utiliser un <strong>accumulateur</strong> :</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> <span class="token keyword">rec</span> length<span class="token punctuation">_</span>bis acu <span class="token operator">=</span> <span class="token keyword">function</span>
	<span class="token operator">|</span> <span class="token punctuation">[</span><span class="token punctuation">]</span> <span class="token operator">-&gt;</span> acu
	<span class="token operator">|</span> x <span class="token punctuation">:</span><span class="token punctuation">:</span> rest <span class="token operator">-&gt;</span> length<span class="token punctuation">_</span>bis <span class="token punctuation">(</span>acu <span class="token operator">+</span> <span class="token number">1</span><span class="token punctuation">)</span> rest<span class="token punctuation">;</span><span class="token punctuation">;</span>

<span class="token keyword">let</span> n <span class="token operator">=</span> length<span class="token punctuation">_</span>bis <span class="token number">0</span> <span class="token punctuation">[</span><span class="token number">1</span><span class="token punctuation">;</span><span class="token number">2</span><span class="token punctuation">;</span><span class="token number">3</span><span class="token punctuation">;</span><span class="token number">4</span><span class="token punctuation">;</span><span class="token number">5</span><span class="token punctuation">]</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<p>Utiliser un accumulateur permet de transformer la fonction en fonction <strong>tail-recursive</strong> ; c’est-à-dire qu’on ne doit pas remonter à chaque appel de la fonction (pour effectuer le <code>+1</code> dans ce cas).<br>
Cela permet de traiter de très longues listes, alors qu’une version sans accumulateur ne le permettrait pas.</p>
<h2 id="cacher-les-fonctions-avec-accumulateur"><em>“Cacher” les fonctions avec accumulateur</em></h2>
<p>Pour définir une fonction tail-recursive, il faut utiliser un accumulateur. Cependant, utiliser un accumulateur modifie le type de la fonction (car il rajoute un argument).<br>
Afin de conserver le type original et de “simplifier” la fonction, on cache cette fonction avec accumulateur :</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> func l <span class="token operator">=</span>
	<span class="token keyword">let</span> <span class="token keyword">rec</span> loop acu l <span class="token operator">=</span>
		<span class="token comment">(* Corps de la fonction tail-recursive *)</span>
	<span class="token keyword">in</span>
		loop <span class="token number">0</span> l<span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<p>Exemple pour le cas de la fonction <code>length</code> :</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token comment">(* Fonction qui n'est pas tail-recursive *)</span>
<span class="token keyword">let</span> <span class="token keyword">rec</span> length l <span class="token operator">=</span>
	<span class="token keyword">match</span> l <span class="token keyword">with</span>
		<span class="token operator">|</span> <span class="token punctuation">[</span><span class="token punctuation">]</span> <span class="token operator">-&gt;</span> <span class="token number">0</span>
		<span class="token operator">|</span> x<span class="token punctuation">:</span><span class="token punctuation">:</span>rest <span class="token operator">-&gt;</span> <span class="token number">1</span> <span class="token operator">+</span> length rest<span class="token punctuation">;</span><span class="token punctuation">;</span>

<span class="token comment">(* Fonction tail-recursive, de type	int -&gt; 'a list -&gt; int *)</span>
<span class="token keyword">let</span> <span class="token keyword">rec</span> length2 acu <span class="token operator">=</span> <span class="token keyword">function</span>
	<span class="token operator">|</span> <span class="token punctuation">[</span><span class="token punctuation">]</span> <span class="token operator">-&gt;</span> acu
	<span class="token operator">|</span> x<span class="token punctuation">:</span><span class="token punctuation">:</span>rest <span class="token operator">-&gt;</span> length2 <span class="token punctuation">(</span>acu <span class="token operator">+</span> <span class="token number">1</span><span class="token punctuation">)</span> rest<span class="token punctuation">;</span><span class="token punctuation">;</span>

<span class="token comment">(* Fonction tail-recursive, de type 'a list -&gt; int *)</span>
<span class="token keyword">let</span> length3 l <span class="token operator">=</span>
	<span class="token keyword">let</span> <span class="token keyword">rec</span> loop acu <span class="token operator">=</span> <span class="token keyword">function</span>
		<span class="token operator">|</span> <span class="token punctuation">[</span><span class="token punctuation">]</span> <span class="token operator">-&gt;</span> acu
		<span class="token operator">|</span> x<span class="token punctuation">:</span><span class="token punctuation">:</span>rest <span class="token operator">-&gt;</span> loop <span class="token punctuation">(</span>acu <span class="token operator">+</span> <span class="token number">1</span><span class="token punctuation">)</span> rest
	<span class="token keyword">in</span>
		loop <span class="token number">0</span> l<span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<h2 id="fonctions-dordre-supérieur"><em>Fonctions d’ordre supérieur</em></h2>
<blockquote>
<p>Une fonction d’ordre supérieur est une fonction qui attend en paramètre une autre fonction.</p>
</blockquote>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> fsum f <span class="token operator">=</span> f <span class="token number">0</span> <span class="token operator">+</span> f <span class="token number">1</span> <span class="token operator">+</span> f <span class="token number">2</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
fsum <span class="token punctuation">(</span><span class="token keyword">function</span> x <span class="token operator">-&gt;</span> x <span class="token operator">*</span> <span class="token number">2</span><span class="token punctuation">)</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<h1 id="pattern-matching">Pattern matching</h1>
<blockquote>
<p>Le <strong>pattern matching</strong> est l’équivalent d’un <code>switch</code> dans d’autres langages.</p>
</blockquote>
<p>Il y a plusieurs façons de faire du pattern matching :</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> f x <span class="token operator">=</span>
	<span class="token keyword">match</span> x <span class="token keyword">with</span>
		<span class="token operator">|</span> <span class="token number">0</span> <span class="token operator">-&gt;</span> <span class="token string">"zero"</span>
		<span class="token operator">|</span> <span class="token number">1</span> <span class="token operator">-&gt;</span> <span class="token string">"one"</span>
		<span class="token operator">|</span> <span class="token punctuation">_</span> <span class="token operator">-&gt;</span> <span class="token string">"other"</span><span class="token punctuation">;</span><span class="token punctuation">;</span>

<span class="token keyword">let</span> f <span class="token operator">=</span> <span class="token keyword">function</span>
	<span class="token operator">|</span> <span class="token number">0</span> <span class="token operator">-&gt;</span> <span class="token string">"zero"</span>
	<span class="token operator">|</span> <span class="token number">1</span> <span class="token operator">-&gt;</span> <span class="token string">"one"</span>
	<span class="token operator">|</span> <span class="token punctuation">_</span> <span class="token operator">-&gt;</span> <span class="token string">"other"</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<p>Le cas “autre” est symbolisé par <code>_</code>. On peut matcher une valeur autre et s’intéresser à une autre :</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> f tup <span class="token operator">=</span>
	<span class="token keyword">match</span> tup <span class="token keyword">with</span>
		<span class="token operator">|</span> <span class="token punctuation">(</span><span class="token number">0</span><span class="token punctuation">,</span> <span class="token boolean">true</span><span class="token punctuation">)</span> <span class="token operator">-&gt;</span> <span class="token number">1</span>
		<span class="token operator">|</span> <span class="token punctuation">(</span><span class="token punctuation">_</span><span class="token punctuation">,</span> <span class="token boolean">true</span><span class="token punctuation">)</span> <span class="token operator">-&gt;</span> <span class="token number">2</span>
		<span class="token operator">|</span> <span class="token punctuation">(</span><span class="token punctuation">_</span><span class="token punctuation">,</span> <span class="token boolean">false</span><span class="token punctuation">)</span> <span class="token operator">-&gt;</span> <span class="token number">3</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<p><em>Note : tous les cas doivent être traités.</em></p>
<p>Le symbole <code>_</code> représente une valeur “autre”. On peut remplacer ce symbole par un nom de variable et réutiliser cette variable ensuite :</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> calc <span class="token operator">=</span> <span class="token keyword">function</span>
	<span class="token operator">|</span> <span class="token punctuation">(</span>x<span class="token punctuation">,</span> y<span class="token punctuation">,</span> <span class="token string">"add"</span><span class="token punctuation">)</span> <span class="token operator">-&gt;</span> x <span class="token operator">+</span> y
	<span class="token operator">|</span> <span class="token punctuation">_</span> <span class="token operator">-&gt;</span> <span class="token number">0</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<p>On peut définir des actions pour plusieurs cas à la fois. Dans cet exemple, on renvoie <code>true</code> pour les deux premiers cas matchés :</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> ext<span class="token punctuation">_</span>and a b c <span class="token operator">=</span>
	<span class="token keyword">match</span> <span class="token punctuation">(</span>a<span class="token punctuation">,</span>b<span class="token punctuation">,</span>c<span class="token punctuation">)</span> <span class="token keyword">with</span>
		<span class="token operator">|</span> <span class="token boolean">false</span><span class="token punctuation">,</span> <span class="token punctuation">_</span><span class="token punctuation">,</span> <span class="token boolean">false</span>
		<span class="token operator">|</span> <span class="token punctuation">_</span><span class="token punctuation">,</span> <span class="token boolean">false</span><span class="token punctuation">,</span> <span class="token boolean">false</span> <span class="token operator">-&gt;</span> <span class="token boolean">true</span>
		<span class="token punctuation">.</span><span class="token punctuation">.</span><span class="token punctuation">.</span>
</code></pre>
<p><strong>Attention !</strong> Les variables utilisées dans la clause <code>match ... with</code> sont “locales”.</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> equal a b <span class="token operator">=</span>
	<span class="token keyword">match</span> b <span class="token keyword">with</span>
		<span class="token operator">|</span> a <span class="token operator">-&gt;</span> <span class="token boolean">true</span><span class="token punctuation">;</span>
		<span class="token operator">|</span> <span class="token punctuation">_</span> <span class="token operator">-&gt;</span> <span class="token boolean">false</span><span class="token punctuation">;</span>
</code></pre>
<p>Le comportement attendu n’est pas correct. Ici, <code>a</code> est considéré comme une valeur “autre” ; ce n’est pas le <code>a</code> donné en paramètre qui est utilisé.</p>
<p><strong>Cas où on doit comparer les tailles des listes</strong></p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> <span class="token keyword">rec</span> combine l1 l2 <span class="token operator">=</span>
	<span class="token keyword">match</span> l1<span class="token punctuation">,</span>l2 <span class="token keyword">with</span>
		<span class="token operator">|</span> <span class="token punctuation">[</span><span class="token punctuation">]</span><span class="token punctuation">,</span> <span class="token punctuation">[</span><span class="token punctuation">]</span> <span class="token operator">-&gt;</span> <span class="token punctuation">[</span><span class="token punctuation">]</span>
		<span class="token operator">|</span> x1<span class="token punctuation">:</span><span class="token punctuation">:</span>rest1<span class="token punctuation">,</span> x2<span class="token punctuation">:</span><span class="token punctuation">:</span>rest2 <span class="token operator">-&gt;</span> <span class="token punctuation">(</span>x1<span class="token punctuation">,</span>x2<span class="token punctuation">)</span> <span class="token punctuation">:</span><span class="token punctuation">:</span> combine rest1 rest2
		<span class="token operator">|</span> <span class="token punctuation">_</span> <span class="token operator">-&gt;</span> failwith <span class="token string">"Tailles différentes"</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Cas où on doit prendre un élément de chaque liste (alternativement)</strong></p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> <span class="token keyword">rec</span> interleave l1 l2 <span class="token operator">=</span>
	<span class="token keyword">match</span> l1<span class="token punctuation">,</span> l2 <span class="token keyword">with</span>
		<span class="token operator">|</span> l1<span class="token punctuation">,</span> <span class="token punctuation">[</span><span class="token punctuation">]</span> <span class="token operator">-&gt;</span> l1
		<span class="token operator">|</span> <span class="token punctuation">[</span><span class="token punctuation">]</span><span class="token punctuation">,</span> l2 <span class="token operator">-&gt;</span> l2
		<span class="token operator">|</span> x1<span class="token punctuation">:</span><span class="token punctuation">:</span>rest1<span class="token punctuation">,</span> l2 <span class="token operator">-&gt;</span> x1 <span class="token punctuation">:</span><span class="token punctuation">:</span> interleave l2 rest1<span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Cas où on doit chercher un max dans une liste</strong></p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> latest <span class="token operator">=</span> <span class="token keyword">function</span>
	<span class="token operator">|</span> <span class="token punctuation">[</span><span class="token punctuation">]</span> <span class="token operator">-&gt;</span> None
	<span class="token operator">|</span> x<span class="token punctuation">:</span><span class="token punctuation">:</span><span class="token punctuation">[</span><span class="token punctuation">]</span> <span class="token operator">-&gt;</span> Some x
	<span class="token operator">|</span> x<span class="token punctuation">:</span><span class="token punctuation">:</span>y<span class="token punctuation">:</span><span class="token punctuation">:</span>rest <span class="token operator">-&gt;</span> latest <span class="token punctuation">(</span><span class="token punctuation">(</span><span class="token keyword">if</span> x<span class="token punctuation">.</span>date <span class="token operator">&gt;</span> y<span class="token punctuation">.</span>date <span class="token keyword">then</span> x <span class="token keyword">else</span> y<span class="token punctuation">)</span><span class="token punctuation">:</span><span class="token punctuation">:</span>rest<span class="token punctuation">)</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Cas où on crée une liste à partir d’un arbre</strong></p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> get<span class="token punctuation">_</span>results tree <span class="token operator">=</span>
	<span class="token keyword">let</span> <span class="token keyword">rec</span> loop acu <span class="token operator">=</span> <span class="token keyword">function</span>
		<span class="token operator">|</span> Result x <span class="token operator">-&gt;</span> x<span class="token punctuation">:</span><span class="token punctuation">:</span>acu
		<span class="token operator">|</span> Test <span class="token punctuation">(</span><span class="token punctuation">_</span><span class="token punctuation">,</span> left<span class="token punctuation">,</span> right<span class="token punctuation">)</span> <span class="token operator">-&gt;</span> loop <span class="token punctuation">(</span>loop acu left<span class="token punctuation">)</span> right
	<span class="token keyword">in</span> loop <span class="token punctuation">[</span><span class="token punctuation">]</span> tree<span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<h1 id="types">Types</h1>
<h2 id="records"><em>Records</em></h2>
<p>On peut déclarer un <code>record</code> en utilisant une <strong>déclaration de type</strong> :</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">type</span> coordinates <span class="token operator">=</span>
	<span class="token punctuation">{</span> long<span class="token punctuation">:</span> float <span class="token punctuation">;</span>
	  lat<span class="token punctuation">:</span>  float <span class="token punctuation">}</span><span class="token punctuation">;</span><span class="token punctuation">;</span>

<span class="token keyword">type</span> test <span class="token operator">=</span>
	<span class="token punctuation">{</span> fonc<span class="token punctuation">:</span> <span class="token punctuation">(</span>int <span class="token operator">-&gt;</span> int<span class="token punctuation">)</span> <span class="token punctuation">;</span>
	  arg<span class="token punctuation">:</span> int <span class="token punctuation">;</span>
	  expect<span class="token punctuation">:</span> int <span class="token punctuation">}</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Construction</strong></p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> point <span class="token operator">=</span> <span class="token punctuation">{</span> long <span class="token operator">=</span> <span class="token operator">-</span><span class="token number">0.3</span> <span class="token punctuation">;</span>
			  lat <span class="token operator">=</span> <span class="token number">42.5</span> <span class="token punctuation">}</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Récupération d’une valeur</strong></p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> get<span class="token punctuation">_</span>lat c <span class="token operator">=</span> c<span class="token punctuation">.</span>lat<span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<p>On peut aussi utiliser un pattern :</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> get<span class="token punctuation">_</span>lat <span class="token punctuation">{</span> lat <span class="token operator">=</span> ll <span class="token punctuation">}</span> <span class="token operator">=</span> ll<span class="token punctuation">;</span><span class="token punctuation">;</span>
<span class="token comment">(* ou encore *)</span>
<span class="token keyword">let</span> get<span class="token punctuation">_</span>lat <span class="token punctuation">{</span> lat <span class="token punctuation">}</span> <span class="token operator">=</span> lat<span class="token punctuation">;</span><span class="token punctuation">;</span>

<span class="token keyword">let</span> is<span class="token punctuation">_</span>good <span class="token operator">=</span> <span class="token keyword">function</span>
	<span class="token operator">|</span> <span class="token punctuation">{</span> region<span class="token punctuation">_</span>name <span class="token operator">=</span> <span class="token string">""</span><span class="token punctuation">}</span> <span class="token operator">-&gt;</span> <span class="token boolean">false</span>
	<span class="token operator">|</span> <span class="token punctuation">{</span> borders <span class="token operator">=</span> <span class="token punctuation">[</span><span class="token punctuation">]</span> <span class="token punctuation">}</span> <span class="token operator">-&gt;</span> <span class="token boolean">false</span>
	<span class="token operator">|</span> <span class="token punctuation">_</span> <span class="token operator">-&gt;</span> <span class="token boolean">true</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Modifier juste un paramètre du record</strong><br>
On peut “copier” un record déjà existant tout en modifiant un seul paramètre :</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> point1 <span class="token operator">=</span> <span class="token punctuation">{</span> long <span class="token operator">=</span> <span class="token operator">-</span><span class="token number">0.3</span> <span class="token punctuation">;</span>
			   lat  <span class="token operator">=</span> <span class="token number">42.5</span> <span class="token punctuation">;</span>
			   z <span class="token operator">=</span> <span class="token number">10.0</span><span class="token punctuation">}</span><span class="token punctuation">;</span><span class="token punctuation">;</span>

<span class="token keyword">let</span> point2 <span class="token operator">=</span> <span class="token punctuation">{</span> point1 <span class="token keyword">with</span> long <span class="token operator">=</span> <span class="token operator">-</span><span class="token number">1.0</span> <span class="token punctuation">;</span> lat <span class="token operator">=</span> <span class="token number">5.</span> <span class="token punctuation">}</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Mutable records</strong></p>
<blockquote>
<p>Un <strong>mutable record</strong> est un record dont un ou plusieurs de ses champs est modifiable (c’est donc une structure avec des effets de bord).</p>
</blockquote>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">type</span> player <span class="token operator">=</span>
	<span class="token punctuation">{</span> name<span class="token punctuation">:</span> string <span class="token punctuation">;</span>
	  <span class="token keyword">mutable</span> points<span class="token punctuation">:</span> int <span class="token punctuation">}</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<p>Le champ <code>points</code> peut être modifié alors que le champ <code>name</code> ne peut pas l’être.</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> player1 <span class="token operator">=</span> <span class="token punctuation">{</span>name <span class="token operator">=</span> <span class="token string">"Toto"</span><span class="token punctuation">;</span> points <span class="token operator">=</span> <span class="token number">30</span><span class="token punctuation">}</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
player1<span class="token punctuation">.</span>points <span class="token operator">&lt;-</span> <span class="token number">50</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<p>Pour savoir si un type est mutable ou non, on peut regarder une fonction qui le modifie : si la fonction renvoie un élément de ce type, c’est que ce type ne peut pas être modifié (elle en crée un nouveau). Si le type est mutable, la fonction va directement modifier l’élément et son type sera <code>unit</code>.</p>
<h2 id="arrays"><em>Arrays</em></h2>
<blockquote>
<p>Les arrays sont des types paramétrés.</p>
</blockquote>
<ul>
<li>Pour construire un array :</li>
</ul>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token punctuation">(</span><span class="token operator">*</span> <span class="token number">100</span> cellules qui contiennent <span class="token boolean">true</span><span class="token punctuation">)</span>
<span class="token keyword">let</span> john <span class="token operator">=</span> Array<span class="token punctuation">.</span>make <span class="token number">100</span> <span class="token boolean">true</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<ul>
<li>Pour lire une valeur :</li>
</ul>
<pre class=" language-ocaml"><code class="prism  language-ocaml">john<span class="token punctuation">.</span><span class="token punctuation">(</span>index<span class="token punctuation">)</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<ul>
<li>Pour écrire une valeur :</li>
</ul>
<pre class=" language-ocaml"><code class="prism  language-ocaml">john<span class="token punctuation">.</span><span class="token punctuation">(</span>index<span class="token punctuation">)</span> <span class="token operator">&lt;-</span> <span class="token keyword">value</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<p><em>Plus d’informations et de fonctions : <a href="http://caml.inria.fr/pub/docs/manual-ocaml/libref/Array.html">Module Array</a></em></p>
<h2 id="types-de-données-variantes"><em>Types de données variantes</em></h2>
<p>On peut définir une énumération ainsi :</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">type</span> color <span class="token operator">=</span> White <span class="token operator">|</span> Red <span class="token operator">|</span> Blue<span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<p><em>Les constructeurs doivent commencer par une majuscule.</em></p>
<p>Cependant, on peut affiner certains éléments de l’énumération :</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">type</span> role <span class="token operator">=</span> Player <span class="token keyword">of</span> color <span class="token operator">*</span> int <span class="token operator">|</span> Referee<span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<p>Ici, on a :</p>
<ul>
<li>un nouveau type : <code>role</code> ;</li>
<li>un constructeur <code>Referee</code>, qui n’a pas d’argument ;</li>
<li>un constructeur <code>Player</code>, qui a deux arguments.</li>
</ul>
<p><strong>Construction</strong></p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> role1 <span class="token operator">=</span> Referee<span class="token punctuation">;</span><span class="token punctuation">;</span>
<span class="token keyword">let</span> role2 <span class="token operator">=</span> Player <span class="token punctuation">(</span>Red<span class="token punctuation">,</span> <span class="token number">2</span><span class="token punctuation">)</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Récupérer une valeur</strong><br>
On utilise le pattern-matching :</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> get<span class="token punctuation">_</span>number <span class="token operator">=</span> <span class="token keyword">function</span>
	<span class="token operator">|</span> Referee <span class="token operator">-&gt;</span> <span class="token number">0</span>
	<span class="token operator">|</span> Player<span class="token punctuation">(</span><span class="token punctuation">_</span><span class="token punctuation">,</span> nb<span class="token punctuation">)</span> <span class="token operator">-&gt;</span> nb<span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<h1 id="autres">Autres</h1>
<h2 id="let"><em>Let</em></h2>
<blockquote>
<p><code>let</code> est une expression <em>top-level</em>.</p>
</blockquote>
<p>On peut donc l’utiliser à la racine de notre programme, mais pas par exemple dans une liste :</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token punctuation">[</span><span class="token number">4</span><span class="token punctuation">;</span> <span class="token keyword">let</span> x <span class="token operator">=</span> <span class="token number">5</span><span class="token punctuation">;</span> <span class="token number">6</span><span class="token punctuation">]</span> <span class="token comment">(* Erreur *)</span>
</code></pre>
<p>Pour rappel, le <code>if</code> est une expression qui peut être utilisée n’importe où :</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token punctuation">[</span><span class="token number">4</span><span class="token punctuation">;</span> <span class="token keyword">if</span> b <span class="token keyword">then</span> <span class="token number">5</span> <span class="token keyword">else</span> <span class="token operator">-</span><span class="token number">5</span><span class="token punctuation">;</span> <span class="token number">6</span><span class="token punctuation">]</span><span class="token punctuation">;</span><span class="token punctuation">;</span> <span class="token comment">(* Correct *)</span>
</code></pre>
<blockquote>
<p>Les variables définies avec <code>let</code> peuvent être redéfinies.</p>
</blockquote>
<p>Le contenu précédent est effacé.</p>
<h3 id="inner-let">“Inner let”</h3>
<p><code>let</code> est une instruction top-level, mais il existe une expression qui permet d’utiliser <code>let</code> dans une autre expression :</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> <span class="token punctuation">.</span><span class="token punctuation">.</span><span class="token punctuation">.</span> <span class="token keyword">in</span> <span class="token punctuation">.</span><span class="token punctuation">.</span><span class="token punctuation">.</span>
</code></pre>
<p>Ce qu’on définit dans une <code>let ... in ...</code> peut être utilisé <strong>après</strong>.</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> f n <span class="token operator">=</span>
	<span class="token keyword">let</span> a <span class="token operator">=</span> <span class="token number">2</span> <span class="token operator">*</span> n <span class="token keyword">in</span>
	<span class="token keyword">let</span> b <span class="token operator">=</span> <span class="token number">3</span> <span class="token operator">*</span> a <span class="token keyword">in</span>
		Printf<span class="token punctuation">.</span>printf <span class="token string">"b = %d\n%!"</span> b<span class="token punctuation">;</span><span class="token punctuation">;</span> <span class="token comment">(* b = 18 *)</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<h2 id="print"><em>Print</em></h2>
<p>Pour afficher du texte, on utilise la fonction <code>Printf.printf</code> :</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml">Printf<span class="token punctuation">.</span>printf <span class="token string">"2 + 3 = %d\n%!"</span> <span class="token number">5</span><span class="token punctuation">;</span><span class="token punctuation">;</span> 
</code></pre>
<p>On peut utiliser le <code>%d</code>, <code>%s</code>, etc., comme en C. Penser à <strong>forcer l’affichage</strong> en utilisant <code>%!</code>.</p>
<p><strong>Fonctions de casting</strong><br>
Il existe plusieurs fonction pour caster des types (entiers par exemple) vers le type <code>string</code> :</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml">Printf<span class="token punctuation">.</span>printf <span class="token string">"%s\n%!"</span> <span class="token punctuation">(</span>string<span class="token punctuation">_</span>of<span class="token punctuation">_</span>float <span class="token number">3.</span><span class="token punctuation">)</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
Printf<span class="token punctuation">.</span>printf <span class="token string">"%s\n%!"</span> <span class="token punctuation">(</span>string<span class="token punctuation">_</span>of<span class="token punctuation">_</span>bool <span class="token boolean">true</span><span class="token punctuation">)</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<p><em>Penser à mettre les parenthèses !</em></p>
<h2 id="exceptions"><em>Exceptions</em></h2>
<blockquote>
<p>Les exceptions sont de type <code>exn</code>.</p>
</blockquote>
<p>Il y a plusieurs moyens de définir une exception :</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> a <span class="token operator">=</span> Not<span class="token punctuation">_</span>found<span class="token punctuation">;</span><span class="token punctuation">;</span>
<span class="token keyword">let</span> b <span class="token operator">=</span> Failure <span class="token string">"Erreur"</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<p>Le type <code>exn</code> est un type variable, défini comme :</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">type</span> exn <span class="token operator">=</span> Not<span class="token punctuation">_</span>found <span class="token operator">|</span> Failure <span class="token keyword">of</span> string <span class="token operator">|</span> Division<span class="token punctuation">_</span>by<span class="token punctuation">_</span>zero <span class="token operator">|</span> <span class="token punctuation">.</span><span class="token punctuation">.</span><span class="token punctuation">.</span>
</code></pre>
<p><strong>Pour lever une exception</strong></p>
<pre class=" language-ocaml"><code class="prism  language-ocaml">raise Not<span class="token punctuation">_</span>found<span class="token punctuation">;</span><span class="token punctuation">;</span>
failwith <span class="token string">"Erreur"</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Pour définir une nouvelle exception</strong></p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">exception</span> Horrible<span class="token punctuation">_</span>erreur<span class="token punctuation">;</span><span class="token punctuation">;</span>
<span class="token keyword">exception</span> Bad<span class="token punctuation">_</span>bad<span class="token punctuation">_</span>thing <span class="token keyword">of</span> int <span class="token operator">*</span> string<span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<p><strong>Pour détecter une exception</strong></p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> test<span class="token punctuation">_</span>raise x <span class="token operator">=</span>
	<span class="token keyword">try</span>
		<span class="token keyword">if</span> x <span class="token operator">&lt;</span> <span class="token number">0</span> <span class="token keyword">then</span> raise Not<span class="token punctuation">_</span>found
		<span class="token keyword">else</span> <span class="token keyword">if</span> x <span class="token operator">=</span> <span class="token number">0</span> <span class="token keyword">then</span> failwith <span class="token string">"Zero"</span>
		<span class="token keyword">else</span> <span class="token punctuation">[</span> string<span class="token punctuation">_</span>of<span class="token punctuation">_</span>int x <span class="token punctuation">]</span>
	<span class="token keyword">with</span>
		<span class="token operator">|</span> Not<span class="token punctuation">_</span>found <span class="token operator">-&gt;</span> <span class="token punctuation">[</span><span class="token punctuation">]</span>
		<span class="token operator">|</span> Failure s <span class="token operator">-&gt;</span> <span class="token punctuation">[</span>s<span class="token punctuation">]</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<p>A noter que tous les cas peuvent ne pas être traités. Le code est alors équivalent à :</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token punctuation">.</span><span class="token punctuation">.</span><span class="token punctuation">.</span>
	<span class="token keyword">with</span>
		<span class="token operator">|</span> Not<span class="token punctuation">_</span>found <span class="token operator">-&gt;</span> <span class="token punctuation">[</span><span class="token punctuation">]</span>
		<span class="token operator">|</span> e <span class="token operator">-&gt;</span> raise e<span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<h2 id="séquence"><em>Séquence</em></h2>
<blockquote>
<p>L’opérateur de séquence est <code>;</code>.</p>
</blockquote>
<p>Une séquence <code>a ; b</code> a le même type que <code>b</code>. <code>a</code> doit donc avoir le type <code>unit</code>.</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> f x <span class="token operator">=</span> Printf<span class="token punctuation">.</span>printf <span class="token string">"Bonjour\n%!"</span> <span class="token punctuation">;</span> x <span class="token operator">*</span> <span class="token number">2</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
<span class="token keyword">let</span> a <span class="token operator">=</span> f <span class="token number">5</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<p>Ici, le message “Bonjour” sera affiché, et la valeur retournée sera 10.</p>
<h2 id="begin-...-end"><em>begin … end</em></h2>
<p>On peut aussi <code>begin ... end</code> pour effectuer plusieurs actions :</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">if</span> condition <span class="token keyword">then</span> <span class="token keyword">begin</span> action1<span class="token punctuation">;</span> action2<span class="token punctuation">;</span> <span class="token keyword">end</span><span class="token punctuation">;</span>
			 <span class="token keyword">else</span> <span class="token keyword">begin</span> action3<span class="token punctuation">;</span> action4<span class="token punctuation">;</span> <span class="token keyword">end</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<p>Les deux écritures suivantes sont équivalentes :</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">begin</span> expression <span class="token keyword">end</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
<span class="token punctuation">(</span> expression <span class="token punctuation">)</span><span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>
<h2 id="expressions-et-définitions"><em>Expressions et définitions</em></h2>
<ul>
<li>
<p>Les <strong>définitions</strong> correspondent au top-level <code>let</code>, aux définitions de types, de modules, et quelques autres choses ;</p>
</li>
<li>
<p>Les <strong>expressions</strong> correspondent plus ou moins à tout le reste :</p>
<ul>
<li><code>if</code> / <code>while</code> / <code>for</code></li>
<li><code>let x = expression in expression</code></li>
<li><code>fun</code> / <code>function</code> / <code>match</code></li>
<li><code>begin expression end</code></li>
</ul>
</li>
</ul>
<h2 id="trace"><em>Trace</em></h2>
<p>Il est possible de tracer une fonction. C’est utile pour voir le déroulement d’une fonction récursive.</p>
<pre class=" language-ocaml"><code class="prism  language-ocaml"><span class="token keyword">let</span> length l <span class="token operator">=</span>
	<span class="token punctuation">.</span><span class="token punctuation">.</span><span class="token punctuation">.</span><span class="token punctuation">;</span><span class="token punctuation">;</span>

<span class="token directive function">#trace</span> length<span class="token punctuation">;</span><span class="token punctuation">;</span> <span class="token comment">(* "length is now traced." *)</span>
<span class="token directive function">#untrace</span> length<span class="token punctuation">;</span><span class="token punctuation">;</span>
</code></pre>

