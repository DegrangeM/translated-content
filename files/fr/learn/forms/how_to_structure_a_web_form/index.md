---
title: Comment structurer un formulaire HTML
slug: Learn/Forms/How_to_structure_a_web_form
tags:
  - Apprentissage
  - Débutant
  - Exemple
  - Formulaires
  - Guide
  - HTML
  - Structure
  - Web
translation_of: Learn/Forms/How_to_structure_a_web_form
original_slug: Web/Guide/HTML/Formulaires/Comment_structurer_un_formulaire_HTML
---
<div>{{LearnSidebar}}</div>

<div>{{PreviousMenuNext("Web/Guide/HTML/Formulaires/Mon_premier_formulaire_HTML", "Web/Guide/HTML/Formulaires/Les_blocs_de_formulaires_natifs", "Web/Guide/HTML/Formulaires")}}</div>

<p>Les bases vues, nous examinons maintenant plus en détail les éléments utilisés pour structurer et donner un sens aux différentes parties d'un formulaire.</p>

<table class="standard-table">
 <tbody>
  <tr>
   <th scope="row">Prérequis :</th>
   <td>Notions concernant les ordinateurs et les <a href="/fr/docs/Learn/HTML/Introduction_to_HTML">connaissances de base du HTML</a>.</td>
  </tr>
  <tr>
   <th scope="row">Objectif :</th>
   <td>Comprendre comment structurer les formulaires HTML et leur adjoindre la sémantique pour qu'ils soient utilisables et accessibles.</td>
  </tr>
 </tbody>
</table>

<p>La souplesse des formulaires HTML fait d'eux une des structures les plus complexes en <a href="/fr/docs/HTML" title="/en-US/docs/HTML">HTML</a>. vous pouvez construire n'importe quel type de formulaire basique en utilisant les éléments et attributs qui leur sont dédiés. En utilisant une architecture correcte lors de la construction d'un formulaire, vous serez sûrs que le formulaire est à la fois utilisable et <a href="/fr/docs/MDN/Doc_status/Accessibility">accessible</a>.</p>

<h2 id="L'élément_&lt;form>">L'élément &lt;form&gt;</h2>

<p>L'élément {{HTMLElement("form")}} définit conventionnellement un formulaire et des attributs qui déterminent le comportement du‑dit formulaire. Chaque fois que vous voulez créer un formulaire HTML, vous devez le débuter par cet élément et mettre tout son contenu à l'intérieur. De nombreuses techniques d'assistance ou greffons de navigateur peuvent détecter les éléments {{HTMLElement("form")}} et implémenter des accroches spéciales pour les rendre plus faciles à utiliser.</p>

<p>Nous l'avons déjà rencontré dans l'article précédent.</p>

<div class="note">
  <p><strong>Note :</strong> Il est strictement interdit d'imbriquer un formulaire dans un autre formulaire. L'imbrication peut conduire à des comportements imprévisibles selon le navigateur utilisé.
  </p>
</div>

<p>Notez qu'il est toujours possible d'utiliser un widget de formulaire en dehors d'un élément {{HTMLElement("form")}} mais si vous le faites, ce widget de formulaire n'a rien à voir avec un formulaire. De tels widgets peuvent être utilisés en dehors d'un formulaire, mais alors vous devriez avoir un plan spécial pour de tels widgets, puisqu'ils ne feront rien tout seuls. Vous devrez personnaliser leur comportement avec JavaScript.</p>

<div class="note">
<p><strong>Note :</strong> HTML5 introduit l'attribut <code>form</code> dans les éléments form du HTML. Il devrait vous permettre de lier explicitement un élément avec un formulaire même s'il n'est pas inclus dans un {{ HTMLElement("form") }}. Malheureusement, pour l'instant, l'implémentation de cette fonctionnalité dans les navigateurs n'est pas encore assez fiable.</p>
</div>

<h2 id="Les_éléments_&lt;fieldset>_et_&lt;legend>">Les éléments &lt;fieldset&gt; et &lt;legend&gt;</h2>

<p>L'élément {{HTMLElement("fieldset")}} est un moyen pratique de créer des groupes de widgets qui partagent le même but, pour le style et la sémantique. Vous pouvez étiqueter un {{HTMLElement("fieldset")}} en incluant un élément {{HTMLElement("legend")}} juste en dessous de la balise d'ouverture &lt;fieldset&gt;. Le contenu textuel de l'élément {{HTMLElement("legend")}} décrit formellement le but de l'élément {{HTMLElement("fieldset")}} inclus à l'intérieur.</p>

<p>De nombreuses technologies d'assistance utiliseront l'élément {{HTMLElement("legend")}} comme s'il faisait partie de l'étiquette de chaque widget à l'intérieur de l'élément {{HTMLElement("fieldset")}} correspondant. Par exemple, certains lecteurs d'écran comme <a href="http://www.freedomscientific.com/products/fs/jaws-product-page.asp" rel="external">Jaws</a> ou <a href="http://www.nvda-project.org/" rel="external">NVDA</a> énonceront le contenu de la légende avant d'indiquer l'étiquette de chaque widget.</p>

<p>Voici un petit exemple :</p>

<pre class="brush:html">&lt;form&gt;
  &lt;fieldset&gt;
    &lt;legend&gt;Taille du jus de fruits&lt;/legend&gt;
    &lt;p&gt;
      &lt;input type="radio" name="size" id="size_1" value="small"&gt;
      &lt;label for="size_1"&gt;Petite&lt;/label&gt;
    &lt;/p&gt;
    &lt;p&gt;
      &lt;input type="radio" name="size" id="size_2" value="medium"&gt;
      &lt;label for="size_2"&gt;Moyenne&lt;/label&gt;
    &lt;/p&gt;
    &lt;p&gt;
      &lt;input type="radio" name="size" id="size_3" value="large"&gt;
      &lt;label for="size_3"&gt;Grande&lt;/label&gt;
    &lt;/p&gt;
  &lt;/fieldset&gt;
&lt;/form&gt;</pre>

<div class="note">
<p><strong>Note :</strong> Vous trouverez cet exemple dans <a href="https://github.com/mdn/learning-area/blob/master/html/forms/html-form-structure/fieldset-legend.html">fieldset-legend.html</a> (voir <a href="https://mdn.github.io/learning-area/html/forms/html-form-structure/fieldset-legend.html">directement aussi</a>).</p>
</div>

<p>En lisant le formulaire ci-dessus, un lecteur d'écran dira « Taille du jus de fruit : petit » pour le premier widget, « Taille du jus de fruit : moyenne » pour le second, et « Taille du jus de fruit : grande » pour le troisième.</p>

<p>Le scenario d'utilisation du lecteur dans cet exemple est l'un des plus importants. Chaque fois que vous avez un ensemble de boutons radio, vous devez les imbriquer dans un élément {{HTMLElement("fieldset")}}. Il y a d'autres scenarii d'utilisation, et en général l'élément {{HTMLElement("fieldset")}} peut aussi être utilisé pour partager un formulaire. Idéalement, les formulaires longs doivent être éclatés sur plusieurs pages, mais si un formulaire long doit être sur une page unique, le fait de placer les différentes sections connexes dans de différents {{HTMLElement("fieldset")}} peut en améliorer l'utilisation.</p>

<p>En raison de son influence sur les techniques d'assistance, l'élément {{HTMLElement("fieldset")}} est l'un des éléments clés pour la création de formulaires accessibles ; cependant, il vous appartient de ne pas en abuser. Si possible, chaque fois que vous créez un formulaire, essayez d'<a href="https://www.nvaccess.org/download/">écouter comment un lecteur d'écran</a> l'interprète. Si cela ne paraît pas naturel, essayez d'améliorer la structure du formulaire.</p>

<h2 id="L'élément_&lt;label>">L'élément &lt;label&gt;</h2>

<p>Comme nous l'avons vu dans l'article précédent, l'élément {{HTMLElement("label")}} est le moyen naturel de définir une étiquette pour un widget de formulaire HTML. C'est l'élément le plus important si vous voulez créer des formulaires accessibles — lorsqu'ils sont correctement implémentés, les lecteurs d'écran énonceront l'étiquette d'un élément de formulaire selon toutes les instructions associées. Prenons cet exemple, que nous avons vu dans l'article précédent :</p>

<pre class="brush: html">&lt;label for="name"&gt;Nom :&lt;/label&gt; &lt;input type="text" id="name" name="user_name"&gt;</pre>

<p>Avec un élément <code>&lt;label&gt;</code> correctement associé à <code>&lt;input&gt;</code> par l'intermédiaire respectivement des attributs <code>for</code> et <code>id</code> (l'attribut <code>for</code> de &lt;label&gt; référence l'attibut <code>id</code> du widget correspondant), un lecteur d'écran lira et dira quelque chose comme « Nom, texte indiqué ».</p>

<p>Si l'étiquette n'est pas correctement paramétrée, le lecteur d'écran dira quelque chose comme « Texte édité vierge », ce qui n'est pas utile du tout.</p>

<p>Notez qu'un widget peut être incorporé dans son élément {{HTMLElement("label")}}, ainsi :</p>

<pre class="brush: html">&lt;label for="name"&gt;
  Nom : &lt;input type="text" id="name" name="user_name"&gt;
&lt;/label&gt;</pre>

<p>Toutefois, même dans ce cas, il est considéré de bonne pratique de définir l'attribut <code>for</code> parce que certaines techniques d'assistance ne font pas implicitement le lien entre les étiquettes et les widgets.</p>

<h3 id="Les_étiquettes_peuvent_être_cliquées_aussi_!">Les étiquettes peuvent être cliquées, aussi !</h3>

<p>Autre avantage de bien configurer les étiquettes : vous pouvez cliquer sur l'étiquette pour activer le widget correspondant, dans tous les navigateurs. Utile, par exemple, pour des entrées de texte : vous pouvez cliquer sur l'étiquette ou la zone de texte pour y obtenir le curseur, mais c'est encore plus utile pour les boutons radio et les cases à cocher — la surface active au clic pour une telle commande peut être très réduite, il est donc utile de l'agrandir autant que possible.</p>

<p>Par exemple :</p>

<pre class="brush:html">&lt;form&gt;
  &lt;p&gt;
    &lt;label for="taste_1"&gt;J'aime les cerises&lt;/label&gt;
    &lt;input type="checkbox" id="taste_1" name="taste_cherry" value="1"&gt;
  &lt;/p&gt;
  &lt;p&gt;
    &lt;label for="taste_2"&gt;J'aime les bananes&lt;/label&gt;
    &lt;input type="checkbox" id="taste_2" name="taste_banana" value="2"&gt;
  &lt;/p&gt;
&lt;/form&gt;</pre>

<div class="note">
<p><strong>Note :</strong> Vous trouverez cet exemple dans <a href="https://github.com/mdn/learning-area/blob/master/html/forms/html-form-structure/checkbox-label.html">checkbox-label.html</a> (à voir <a href="https://mdn.github.io/learning-area/html/forms/html-form-structure/checkbox-label.html">directement aussi</a>).</p>
</div>

<h3 id="Étiquettes_multiples">Étiquettes multiples</h3>

<p>En fait, il est possible d'associer plusieurs étiquettes à un seul widget, mais ce n'est pas une bonne idée car certaines techniques d'assistance peuvent éprouver du trouble pour leur gestion. Dans le cas d'étiquettes multiples, vous devez incorporer le widget et son étiquette dans un seul élément {{htmlelement("label")}}.</p>

<p>Considérons cet exemple :</p>

<pre class="brush: html">&lt;p&gt;Les champs obligatoires sont suivis de &lt;abbr title="required"&gt;*&lt;/abbr&gt;.&lt;/p&gt;

&lt;!-- Donc ceci : --&gt;
&lt;div&gt;
  &lt;label for="username"&gt;Nom :&lt;/label&gt;
  &lt;input type="text" name="username"&gt;
  &lt;label for="username"&gt;&lt;abbr title="required"&gt;*&lt;/abbr&gt;&lt;/label&gt;
&lt;/div&gt;

&lt;!-- sera mieux programmé ainsi : --&gt;
&lt;div&gt;
  &lt;label for="username"&gt;
    &lt;span&gt;Nom :&lt;/span&gt;
    &lt;input id="username" type="text" name="username"&gt;
    &lt;abbr title="required"&gt;*&lt;/abbr&gt;
  &lt;/label&gt;
&lt;/div&gt;

&lt;!-- mais ceci est probablement encore meilleur : --&gt;
&lt;div&gt;
  &lt;label for="username"&gt;Nom :&lt;abbr title="required"&gt;*&lt;/abbr&gt;&lt;/label&gt;
  &lt;input id="username" type="text" name="username"&gt;
&lt;/div&gt;</pre>

<p>Le paragraphe du haut définit la règle pour les éléments obligatoires. Ce doit être au début pour s'assurer que les techniques d'assistance telles que les lecteurs d'écran l'afficheront ou le vocaliseront à l'utilisateur avant qu'il ne trouve un élément obligatoire. Ainsi, ils sauront ce que signifie l'astérisque. Un lecteur d'écran mentionnera l'astérisque en disant « astérisque » ou « obligatoire », selon les réglages du lecteur d'écran — dans tous les cas, ce qui sera dit est clairement précisé dans le premier paragraphe.</p>

<ul>
 <li>Dans le premier exemple, l'étiquette n'est pas lue du tout avec l'entrée — vous obtenez simplement « texte édité vierge », puis les étiquettes réelles sont lues séparément. Les multiples éléments &lt;label&gt; embrouillent le lecteur d'écran.</li>
 <li>Dans le deuxième exemple, les choses sont un peu plus claires — l'étiquette lue en même temps que l'entrée est « nom astérisque nom éditer texte », et les étiquettes sont toujours lues séparément. Les choses sont encore un peu confuses, mais c'est un peu mieux cette fois parce que l'entrée a une étiquette associée.</li>
 <li>Le troisième exemple est meilleur — les véritables étiquettes sont toutes lues ensemble, et l'étiquette énoncée avec l'entrée est « nom astériquer éditer texte ».</li>
</ul>

<div class="note">
<p><strong>Note :</strong> Vous pouvez obtenir des résultats légérement différents, selon votre lecteur d'écran. Ce qui précéde a été testé avec VoiceOver (et NVDA se comporte de la même façon). Nous aimerions avoir un retour sur vos expériences également.</p>
</div>

<div class="note">
<p><strong>Note :</strong> Vous trouverez cet exemple sur GitHub dans <a href="https://github.com/mdn/learning-area/blob/master/html/forms/html-form-structure/required-labels.html">required-labels.html</a> (à voir <a href="https://mdn.github.io/learning-area/html/forms/html-form-structure/required-labels.html">directement aussi</a>). Ne lancez pas l'exemple avec 2 ou 3 version non mises en commentaires — le lecteur d'écran serait totalement embrouillé s'il y a plusieurs étiquettes ET plusieurs entrées avec le même ID !</p>
</div>

<h2 id="Structures_HTML_courantes_dans_les_formulaires">Structures HTML courantes dans les formulaires</h2>

<p>Au-delà des structures propres aux formulaires HTML,rappelons‑nous que les formulaires sont du pur HTML. Vous pouvez donc utiliser toute la puissance du HTML pour structurer un formulaire.</p>

<p>Comme vous avez pu le voir dans les exemples, il est de pratique courante d'envelopper une étiquette et son widget avec un élément {{HTMLElement("div")}}. Les éléments {{HTMLElement("p")}} sont aussi couramment utilisés, tout comme les listes HTML (ces dernières sont très courantes pour structurer plusieurs cases à cocher ou boutons radio).</p>

<p>En plus de l'élément {{HTMLElement("fieldset")}}, il est habituel d'utiliser des titres HTML (par exemple {{htmlelement("h1")}}, {{htmlelement("h2")}}) et des sections (par exemple {{htmlelement("section")}}) pour structurer un formulaire complexe.</p>

<p>Par-dessus tout, il vous appartient de trouver un style où vous vous sentez à l'aise pour coder, et qui se traduit aussi par des formulaires accessibles et utilisables.</p>

<p>Chaque groupe de fonctionnalités séparées doit être contenu dans un élément {{htmlelement("section")}} et les boutons radio dans un élément {{htmlelement("fieldset")}}.</p>

<h3 id="Apprentissage_actif_construire_une_structure_de_formulaire">Apprentissage actif : construire une structure de formulaire</h3>

<p>Mettons ces idées en pratique et construisons une structure de formulaire un peu plus sophistiquée — un formulaire de paiement. Il contiendra un certain nombre de types de widgets que vous ne comprenez pas encore — ne vous inquiétez pas pour l'instant ; vous découvrirez comment ils fonctionnent dans l'article suivant (<a href="/fr/docs/Learn/HTML/Forms/The_native_form_widgets">Les widgets natifs pour formulaire</a>). Pour l'instant, lisez attentivement les descriptions en suivant les instructions ci-dessous et commencez à vous faire une idée des éléments enveloppes que nous utilisons pour structurer le formulaire, et pourquoi.</p>

<ol>
 <li>Pour commencer, faites une copie locale de notre <a href="https://github.com/mdn/learning-area/blob/master/html/introduction-to-html/getting-started/index.html">fichier modèle vierge</a> et des <a href="https://github.com/mdn/learning-area/blob/master/html/forms/html-form-structure/payment-form.css">CSS pour notre formulaire de paiement </a> dans un nouveau répertoire.</li>
 <li>Primo, appliquez les CSS au HTML en ajoutant la ligne suivante dans l'élément {{htmlelement("head")}} du HTML :
  <pre class="brush: html">&lt;link href="payment-form.css" rel="stylesheet"&gt;</pre>
 </li>
 <li>Ensuite, commencez le formulaire en ajoutant un élément {{htmlelement("form")}} :
  <pre class="brush: html">&lt;form&gt;

&lt;/form&gt;</pre>
 </li>
 <li>Entre les balises <code>&lt;form&gt;</code>, ajoutez un en‑tête et un paragraphe pour informer les utilisateurs comment sont marqués les champs obligatoires :
  <pre class="brush: html">&lt;h1&gt;Formulaire de paiement&lt;/h1&gt;
&lt;p&gt;Les champs obligatoires sont suivis par un &lt;strong&gt;&lt;abbr title="required"&gt;*&lt;/abbr&gt;&lt;/strong&gt;.&lt;/p&gt;</pre>
 </li>
 <li>Ensuite, nous ajoutons une grande section de code dans le formulaire, sous la précédente. Ici vous verrez que nous enveloppons les champs d'informations de contact dans des éléments {{htmlelement("section")}} distincts. De plus, nous avons un ensemble de deux boutons radio, que nous mettons chacun à l'intérieur de leur propre élément de liste ({{htmlelement("li")}}). Enfin, nous avons deux zones de texte standard {{htmlelement("input")}} et leurs éléments {{htmlelement("label")}} associés, chacun contenu dans un élément {{htmlelement("p")}}, plus une entrée pour le mot de passe. Ajoutez ce code à votre formulaire maintenant :
  <pre class="brush: html">&lt;section&gt;
    &lt;h2&gt;Informations de contact&lt;/h2&gt;
    &lt;fieldset&gt;
      &lt;legend&gt;Qualité&lt;/legend&gt;
      &lt;ul&gt;
          &lt;li&gt;
            &lt;label for="title_1"&gt;
              &lt;input type="radio" id="title_1" name="title" value="M." &gt;
              Monsieur
            &lt;/label&gt;
          &lt;/li&gt;
          &lt;li&gt;
            &lt;label for="title_2"&gt;
              &lt;input type="radio" id="title_2" name="title" value="Mme."&gt;
              Madame
            &lt;/label&gt;
          &lt;/li&gt;
      &lt;/ul&gt;
    &lt;/fieldset&gt;
    &lt;p&gt;
      &lt;label for="name"&gt;
        &lt;span&gt;Nom : &lt;/span&gt;
        &lt;strong&gt;&lt;abbr title="required"&gt;*&lt;/abbr&gt;&lt;/strong&gt;
      &lt;/label&gt;
      &lt;input type="text" id="name" name="username"&gt;
    &lt;/p&gt;
    &lt;p&gt;
      &lt;label for="mail"&gt;
        &lt;span&gt;e-mail :&lt;/span&gt;
        &lt;strong&gt;&lt;abbr title="required"&gt;*&lt;/abbr&gt;&lt;/strong&gt;
      &lt;/label&gt;
      &lt;input type="email" id="mail" name="usermail"&gt;
    &lt;/p&gt;
    &lt;p&gt;
      &lt;label for="pwd"&gt;
        &lt;span&gt;Mot de passe :&lt;/span&gt;
        &lt;strong&gt;&lt;abbr title="required"&gt;*&lt;/abbr&gt;&lt;/strong&gt;
      &lt;/label&gt;
      &lt;input type="password" id="pwd" name="password"&gt;
    &lt;/p&gt;
&lt;/section&gt;</pre>
 </li>
 <li>Nous arrivons maintenant à la deuxième <code>&lt;section&gt;</code> de notre formulaire — l'information de paiement. Ici nous avons trois widgets distincts avec leur étiquette, chacun contenu dans un paragraphe <code>&lt;p&gt;</code>. Le premier est un menu déroulant ({{htmlelement("select")}}) pour le choix du type de la carte de crédit. Le deuxième  est un élément <code>&lt;input&gt;</code> de type nombre pour entrer le numéro de la carte de crédit. Le dernier est un élément <code>&lt;input&gt;</code> de type <code>date</code> pour entrer la date d'expiration de la carte de crédit (il sera accompagné d'un widget dateur pour les navigateurs prenant en charge cette fonctionnalité, et sera un simple champ textuel pour les navigateurs ne la prenant pas en charge). À nouveau, entrez ce qui suit après la section ci‑dessus :
  <pre class="brush: html">
&lt;section&gt;
    &lt;h2&gt;Informations de paiement&lt;/h2&gt;
    &lt;p&gt;
      &lt;label for="card"&gt;
        &lt;span&gt;Type de carte :&lt;/span&gt;
      &lt;/label&gt;
      &lt;select id="card" name="usercard"&gt;
        &lt;option value="visa"&gt;Visa&lt;/option&gt;
        &lt;option value="mc"&gt;Mastercard&lt;/option&gt;
        &lt;option value="amex"&gt;American Express&lt;/option&gt;
      &lt;/select&gt;
    &lt;/p&gt;
    &lt;p&gt;
      &lt;label for="number"&gt;
        &lt;span&gt;Numéro de carte :&lt;/span&gt;
        &lt;strong&gt;&lt;abbr title="required"&gt;*&lt;/abbr&gt;&lt;/strong&gt;
      &lt;/label&gt;
      &lt;input type="text" id="number" name="cardnumber"&gt;
    &lt;/p&gt;
    &lt;p&gt;
      &lt;label for="date"&gt;
        &lt;span&gt;Validité :&lt;/span&gt;
        &lt;strong&gt;&lt;abbr title="required"&gt;*&lt;/abbr&gt;&lt;/strong&gt;
        &lt;em&gt;format mm/aa&lt;/em&gt;
      &lt;/label&gt;
      &lt;input type="text" id="date" name="expiration"&gt;
    &lt;/p&gt;
&lt;/section&gt;</pre>
 </li>
 <li>La dernière section est plus simple ; elle ne contient qu'un bouton {{htmlelement("button")}} de type <code>submit</code>, pour adresser les données du formulaire. Ajoutez ceci au bas du formulaire :
  <pre class="brush: html">&lt;p&gt; &lt;button type="submit"&gt;Valider le paiement&lt;/button&gt; &lt;/p&gt;</pre>
 </li>
</ol>

<p>Vous pouvez voir le formulaire terminé en action ci‑dessous (vous le trouverez aussi sur GitHub — voir la <a href="https://github.com/mdn/learning-area/blob/master/html/forms/html-form-structure/payment-form.html">source</a> payment-form.html et une exécution <a href="https://mdn.github.io/learning-area/html/forms/html-form-structure/payment-form.html">directe</a>):</p>

<p>{{EmbedLiveSample("Un_formulaire_de_paiement","100%","620", "", "Web/Guide/HTML/Formulaires/Comment_structurer_un_formulaire_HTML/Exemple")}}</p>

<h2 id="Résumé">Résumé</h2>

<p>Nous savons maintenant ce qu'il faut faire pour structurer de manière appropriée un formulaire HTML ; l'article suivant approfondira la mise en œuvre  des divers types de widgets pour formulaire pour collecter les informations utilisateur.</p>

<h2 id="Voir_aussi">Voir aussi</h2>

<ul>
 <li><a href="http://www.alistapart.com/articles/sensibleforms/" rel="external">A List Apart: <em>Sensible Forms: A Form Usability Checklist</em></a></li>
</ul>

<p>{{PreviousMenuNext("Web/Guide/HTML/Formulaires/Mon_premier_formulaire_HTML", "Web/Guide/HTML/Formulaires/Les_blocs_de_formulaires_natifs", "Web/Guide/HTML/Formulaires")}}</p>

<h2 id="Dans_ce_module">Dans ce module</h2>

<ul>
 <li><a href="/fr/docs/Web/Guide/HTML/Formulaires/Mon_premier_formulaire_HTML">Mon premier formulaire HTML</a></li>
 <li>Comment structurer un formulaire HTML</li>
 <li><a href="/fr/docs/Web/Guide/HTML/Formulaires/Les_blocs_de_formulaires_natifs">Les widgets natifs pour formulaire</a></li>
 <li><a href="/fr/docs/Web/Guide/HTML/Formulaires/Envoyer_et_extraire_les_données_des_formulaires">Envoi des données de formulaire</a></li>
 <li><a href="/fr/docs/Web/Guide/HTML/Formulaires/Validation_donnees_formulaire">Validation des données de formulaire</a></li>
 <li><a href="/fr/docs/Web/Guide/HTML/Formulaires/Comment_construire_des_widgets_de_formulaires_personnalisés">Comment construire des widgets personnalisés pour formulaire</a></li>
 <li><a href="/fr/docs/Web/Guide/HTML/Formulaires/Sending_forms_through_JavaScript">Envoi de formulaires à l'aide du JavaScript</a></li>
 <li><a href="/fr/docs/Web/Guide/HTML/Formulaires/HTML_forms_in_legacy_browsers">Formulaires HTML dans les navigateurs anciens</a></li>
 <li><a href="/fr/docs/Web/Guide/HTML/Formulaires/Apparence_des_formulaires_HTML">Mise en forme des formulaires HTML</a></li>
 <li><a href="/fr/docs/Web/Guide/HTML/Formulaires/Advanced_styling_for_HTML_forms">Mise en forme avancée des formulaires HTML</a></li>
 <li><a href="/fr/docs/Web/Guide/HTML/Formulaires/Property_compatibility_table_for_form_widgets">Table de compatibilité des propriétés pour les widgets de formulaire</a></li>
</ul>