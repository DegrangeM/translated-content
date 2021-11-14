---
title: Table de compatibilité des propriétés pour les widgets de formulaire
slug: Learn/Forms/Property_compatibility_table_for_form_controls
tags:
  - Avancé
  - CSS
  - Formulaires
  - Guide
  - HTML
  - Indésirables
  - Mises à jour
  - Web
translation_of: Learn/Forms/Property_compatibility_table_for_form_controls
original_slug: Web/Guide/HTML/Formulaires/Property_compatibility_table_for_form_widgets
---
<div>{{learnsidebar}}{{PreviousMenu("Web/Guide/HTML/Formulaires/Advanced_styling_for_HTML_forms", "Web/Guide/HTML/Formulaires")}}</div>

<p>Les tables de compatibilité suivantes tentent de résumer l'état de la prise en charge des CSS par les formulaires HTML. Eu égard à la complexité des CSS et des formulaires HTML, ces tables ne peuvent pas être considérées comme un élément de référence parfait. Toutefois, elles vous donneront un bon aperçu de ce qui peut et de ce qui ne peut pas être fait, ce qui vous aidera à apprendre comment faire les choses.</p>

<h2 id="Comment_lire_les_tables">Comment lire les tables</h2>

<h3 id="Valeurs">Valeurs</h3>

<p>Pour chaque propriété, il y a quatre valeurs possibles :</p>

<dl>
 <dt>OUI</dt>
 <dd>La prise en charge de la propriété est raisonnablement cohérente d'un navigateur à l'autre. Il se peut que vous soyez encore confronté à des effets collatéraux étranges dans certains cas limites.</dd>
 <dt>PARTIEL</dt>
 <dd>Bien que la propriété soit acceptée, vous pouvez fréquemment être confronté à des effets collatéraux bizarres ou à des incohérences. Vous devriez probablement éviter ces propriétés si vous n'avez pas d'abord maîtrisé ces effets secondaires.</dd>
 <dt>NON</dt>
 <dd>La propriété ne fonctionne tout simplement pas ou est si incohérente qu'elle n'est pas fiable.</dd>
 <dt>N.A.</dt>
 <dd>La propriété n'a aucune signification pour ce type de widget.</dd>
</dl>

<h3 id="Rendu">Rendu</h3>

<p>Pour chaque propriété il y a deux rendus possibles :</p>

<dl>
 <dt>N (Normal)</dt>
 <dd>Indique que la propriété est appliquée telle quelle.</dd>
 <dt>A (Altéré)</dt>
 <dd>Indique que la propriété est appliquée avec la règle supplémentaire ci-dessous :</dd>
</dl>

<pre class="brush: css">* {
/* Ceci désactive l'aspect et le comportement natif des navigateurs basés sur WebKit. */
  -webkit-appearance: none;

/* Ceci désactive l'aspect et le comportement natif des navigateurs basés sur Gecko. */
  -moz-appearance: none;

/* Ceci désactive l'aspect et le comportement natif sur plusieurs divers navigateurs
   y compris Opera, Internet Explorer et Firefox */
  background: none;
}</pre>

<h2 id="Tables_de_compatibilité">Tables de compatibilité</h2>

<h3 id="Comportements_globaux">Comportements globaux</h3>

<p>Certains comportements sont communs à de nombreux navigateurs au niveau global :</p>

<dl>
 <dt>{{cssxref("border")}}, {{cssxref("background")}}, {{cssxref("border-radius")}}, {{cssxref("height")}}</dt>
 <dd>L'utilisation de l'une de ces propriétés peut désactiver partiellement ou totalement l'aspect natif des widgets sur certains navigateurs. Prudence lorsque vous les utilisez.</dd>
 <dt>{{cssxref("line-height")}}</dt>
 <dd>Cette propriété est prise en charge de manière non cohérente d'un navigateur à l'autre et vous devriez l'éviter.</dd>
 <dt>{{cssxref("text-decoration")}}</dt>
 <dd>Cette propriété n'est pas prise en charge par Opera sur les widgets de formulaire.</dd>
 <dt>{{cssxref("text-overflow")}}</dt>
 <dd>Opera, Safari et IE9 ne prennent pas en charge cette propriété sur les widgets de formulaire.</dd>
 <dt>{{cssxref("text-shadow")}}</dt>
 <dd>Opera ne prend pas en charge {{cssxref("text-shadow")}} sur les widgets de formulaire et IE9 ne le prend pas du tout en charge.</dd>
</dl>

<h3 id="Champs_texte">Champs texte</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Propriété</th>
   <th scope="col" style="text-align: center;">N</th>
   <th scope="col" style="text-align: center;">A</th>
   <th scope="col">Note</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Modèle de boîte CSS</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("width")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("height")}}</th>
   <td>Partiel</td>
   <td>Oui</td>
   <td>
    <ol>
     <li>Les navigateurs WebKit (principalement sur Mac OSX et iOS) utilisent apparence et comportement natifs pour les champs de recherche. Par conséquent, il est nécessaire d'utiliser <code>-webkit-appearance:none</code> pour pouvoir appliquer cette propriété aux champs de recherche.</li>
     <li>Sous Windows 7, Internet Explorer 9 n'applique pas la bordure à moins que <code>background:none</code> ne soit utilisé.</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("border")}}</th>
   <td>Partiel</td>
   <td>Oui</td>
   <td>
    <ol>
     <li>Les navigateurs WebKit (principalement sur Mac OSX et iOS) utilisent apparence et comportement natifs pour les champs de recherche. Par conséquent, il est nécessaire d'utiliser <code>-webkit-appearance:none</code> pour pouvoir appliquer cette propriété aux champs de recherche.</li>
     <li>Sous Windows 7, Internet Explorer 9 n'applique pas la bordure à moins que <code>background:none</code> ne soit utilisé.</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("margin")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("padding")}}</th>
   <td>Partiel</td>
   <td>Oui</td>
   <td>
    <ol>
     <li>Les navigateurs WebKit (principalement sur Mac OSX et iOS) utilisent apparence et comportement natifs pour les champs de recherche. Par conséquent, il est nécessaire d'utiliser <code>-webkit-appearance:none</code> pour pouvoir appliquer cette propriété aux champs de recherche.</li>
     <li>Sous Windows 7, Internet Explorer 9 n'applique pas la bordure à moins que <code>background:none</code> ne soit utilisé.</li>
    </ol>
   </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Texte et polices</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("color")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td>
    <ol>
     <li>Si la propriété {{cssxref("border-color")}} n'est pas mentionnée, certains navigateurs fondés sur WebKit appliqueront la propriété {{cssxref("color")}} aussi bien à la bordure qu'à la police avec l'élément {{HTMLElement("textarea")}}.</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("font")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td>Voir la note à propos de {{cssxref("line-height")}}</td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("letter-spacing")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-align")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-decoration")}}</th>
   <td>Partiel</td>
   <td>Partiel</td>
   <td>Voir la note à propos de Opera</td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-indent")}}</th>
   <td>Partiel</td>
   <td>Partiel</td>
   <td>
    <ol>
     <li>IE9 prend en charge cette propriété uniquement sur les éléments {{HTMLElement("textarea")}}, alors que Opera ne la prend en charge que sur les champs texte sur une ligne.</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-overflow")}}</th>
   <td>Partiel</td>
   <td>Partiel</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-shadow")}}</th>
   <td>Partiel</td>
   <td>Partiel</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-transform")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Bordure et arrière-plan</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("background")}}</th>
   <td>Partiel</td>
   <td>Oui</td>
   <td>
    <ol>
     <li>Les navigateurs WebKit (principalement sur Mac OSX et iOS) utilisent apparence et comportement natifs pour les champs de recherche. Par conséquent, il est nécessaire d'utiliser<code> -webkit-appearance:none</code> pour pouvoir appliquer cette propriété aux champs de recherche. Sous Windows 7, Internet Explorer 9 n'applique pas la bordure à moins que <code>background:none</code> ne soit utilisé.</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("border-radius")}}</th>
   <td>Partiel</td>
   <td>Oui</td>
   <td>
    <ol>
     <li>Les navigateurs WebKit (principalement sur Mac OSX et iOS) utilisent apparence et comportement natifs pour les champs de recherche. Par conséquent, il est nécessaire d'utiliser<code> -webkit-appearance:none</code> pour pouvoir appliquer cette propriété aux champs de recherche. Sous Windows 7, Internet Explorer 9 n'applique pas la bordure à moins que <code>background:none</code> ne soit utilisé.</li>
     <li>Sur Opera la propriété {{cssxref("border-radius")}} n'est appliquée que si une bordure est explicitement définie.</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("box-shadow")}}</th>
   <td>Non</td>
   <td>Partiel</td>
   <td>
    <ol>
     <li>IE9 ne prend pas en charge cette propriété.</li>
    </ol>
   </td>
  </tr>
 </tbody>
</table>

<h3 id="Boutons">Boutons</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Propriété</th>
   <th scope="col" style="text-align: center;">N</th>
   <th scope="col" style="text-align: center;">A</th>
   <th scope="col">Note</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Modèle de boîte CSS</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("width")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("height")}}</th>
   <td>Partiel</td>
   <td>Oui</td>
   <td>
    <ol>
     <li>Cette propriété n'est pas appliquée sur les navigateurs fondés sur WebKit sur Mac OSX ou iOS.</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("border")}}</th>
   <td>Partiel</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("margin")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("padding")}}</th>
   <td>Partiel</td>
   <td>Oui</td>
   <td>
    <ol>
     <li>Cette propriété n'est pas appliquée sur les navigateurs fondés sur WebKit sur Mac OSX ou iOS.</li>
    </ol>
   </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Texte et polices</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("color")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("font")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td>Voir la note à propos de {{cssxref("line-height")}}.</td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("letter-spacing")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-align")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-decoration")}}</th>
   <td>Partiel</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-indent")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-overflow")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-shadow")}}</th>
   <td>Partiel</td>
   <td>Partiel</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-transform")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Bordure et arrière-plan</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("background")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("border-radius")}}</th>
   <td>Yes</td>
   <td>Yes</td>
   <td>
    <ol>
     <li>Sur Opera la propriété {{cssxref("border-radius")}} n'est appliquée que si une bordure est explicitement définie.</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("box-shadow")}}</th>
   <td>Non</td>
   <td>Partiel</td>
   <td>
    <ol>
     <li>IE9 ne prend pas en charge cette propriété.</li>
    </ol>
   </td>
  </tr>
 </tbody>
</table>

<h3 id="Widget_number">Widget <code>number</code></h3>

<p>Sur les navigateurs qui implémentent le widget <code>number</code>, il n'y a pas de méthode standard pour changer le style des roulettes utilisées pour changer la valeur du champ. Il est à noter que les roulettes de Safari sont en dehors du champ.</p>

<table>
 <thead>
  <tr>
   <th scope="col">Propriété</th>
   <th scope="col" style="text-align: center;">N</th>
   <th scope="col" style="text-align: center;">A</th>
   <th scope="col">Note</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Modèle de boîte CSS</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("width")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("height")}}</th>
   <td>Partiel</td>
   <td>Partiel</td>
   <td>
    <ol>
     <li>Sur Opera, les roulettes sont zoomés, ce qui peut masquer le contenu du champ.</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("border")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("margin")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("padding")}}</th>
   <td>Partiel</td>
   <td>Partiel</td>
   <td>
    <ol>
     <li>Sur Opera, les roulettes sont zoomés, ce qui peut masquer le contenu du champ.</li>
    </ol>
   </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Texte et polices</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("color")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("font")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td>Voir la note à propos de {{cssxref("line-height")}}.</td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("letter-spacing")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-align")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-decoration")}}</th>
   <td>Partiel</td>
   <td>Partiel</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-indent")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-overflow")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-shadow")}}</th>
   <td>Partiel</td>
   <td>Partiel</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-transform")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Bordure et arrière‑plan</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("background")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td colspan="1" rowspan="3">
    <p>Pris en charge mais il y a trop d'incohérence entre les navigateurs pour que ce soit fiable.</p>
   </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("border-radius")}}</th>
   <td>Non</td>
   <td>Non</td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("box-shadow")}}</th>
   <td>Non</td>
   <td>Non</td>
  </tr>
 </tbody>
</table>

<h3 id="Cases_à_cocher_et_boutons_radio">Cases à cocher et boutons radio</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Propriété</th>
   <th scope="col" style="text-align: center;">N</th>
   <th scope="col" style="text-align: center;">A</th>
   <th scope="col">Note</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Modèle de boîte CSS</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("width")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td>
    <ol>
     <li>Certains navigateurs ajoutent des marges supplémentaires et d'autres étirent le widget.</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("height")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td>
    <ol>
     <li>Certains navigateurs ajoutent des marges supplémentaires et d'autres étirent le widget.</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("border")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("margin")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("padding")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Texte et polices</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("color")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("font")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("letter-spacing")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-align")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-decoration")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-indent")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-overflow")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-shadow")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-transform")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Bordure et arrière-plan</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("background")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("border-radius")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("box-shadow")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
 </tbody>
</table>

<h3 id="Boîtes_à_sélection_(ligne_unique)">Boîtes à sélection (ligne unique)</h3>

<p>Firefox ne fournit aucun moyen de changer la flèche vers le bas sur l'élément {{HTMLElement("select")}}.</p>

<table>
 <thead>
  <tr>
   <th scope="col">Propriété</th>
   <th scope="col" style="text-align: center;">N</th>
   <th scope="col" style="text-align: center;">A</th>
   <th scope="col">Note</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Modèle de boîte CSS</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("width")}}</th>
   <td>Partiel</td>
   <td>Partiel</td>
   <td>
    <ol>
     <li>Cette propriété est correcte sur l'élément {{HTMLElement("select")}}, mais cela peut ne pas être le cas sur les éléments {{HTMLElement("option")}} ou {{HTMLElement("optgroup")}}.</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("height")}}</th>
   <td>Non</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("border")}}</th>
   <td>Partiel</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("margin")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("padding")}}</th>
   <td>Non</td>
   <td>Partiel</td>
   <td>
    <ol>
     <li>La propriété est appliquée, mais de manière incohérente entre navigateurs sous Mac OSX.</li>
     <li>La propriété est bien appliquée sur l'élément {{HTMLElement("select")}}, mais est traitée de manière incohérente sur les éléments {{HTMLElement("option")}} et {{HTMLElement("optgroup")}}.</li>
    </ol>
   </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Texte et polices</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("color")}}</th>
   <td>Partiel</td>
   <td>Partiel</td>
   <td>
    <ol>
     <li>Sur Mac OSX, les navigateurs fondés sur WebKit ne prennent pas en charge cette propriété sur les widgets natifs et, avec Opera, ils ne la prennent pas du tout en charge sur les éléments {{HTMLElement("option")}} et {{HTMLElement("optgroup")}}.</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("font")}}</th>
   <td>Partiel</td>
   <td>Partiel</td>
   <td>
    <ol>
     <li>Sur Mac OSX, les navigateurs fondés sur WebKit ne prennent pas en charge cette propriété sur les widgets natifs et, avec Opera, ils ne la prennent pas du tout en charge sur les éléments {{HTMLElement("option")}} et {{HTMLElement("optgroup")}}.</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("letter-spacing")}}</th>
   <td>Partiel</td>
   <td>Partiel</td>
   <td>
    <ol>
     <li>IE9 ne prend pas en charge cette propriété sur les éléments {{HTMLElement("select")}}, {{HTMLElement("option")}}, et {{HTMLElement("optgroup")}} ; les navigateurs fondés sur WebKit sur Mac OSX ne prennent pas en charge cette propriété sur les éléments {{HTMLElement("option")}} et {{HTMLElement("optgroup")}}.</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-align")}}</th>
   <td>No</td>
   <td>No</td>
   <td>
    <ol>
     <li>IE9 sous Windows 7 et les navigateurs fondés sur WebKit sous Mac OSX ne prennent pas en charge cette propriété pour ce widget.</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-decoration")}}</th>
   <td>Partiel</td>
   <td>Partiel</td>
   <td>
    <ol>
     <li>Seul Firefox fournit une prise en charge totale de cette propriété. Opera ne la prend pas du tout en charge et d'autres navigateur ne le font que pour l'élément  {{HTMLElement("select")}}.</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-indent")}}</th>
   <td>Partiel</td>
   <td>Partiel</td>
   <td>
    <ol>
     <li>La plupart des navigateurs ne prennent en charge cette propriété que pour l'élément {{HTMLElement("select")}}.</li>
     <li>IE9 ne prend pas en charge cette propriété.</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-overflow")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-shadow")}}</th>
   <td>Partiel</td>
   <td>Partiel</td>
   <td>
    <ol>
     <li>La plupart des navigateurs ne prennent en charge cette propriété que pour l'élément {{HTMLElement("select")}}.</li>
     <li>IE9 ne prend pas en charge cette propriété.</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-transform")}}</th>
   <td>Partiel</td>
   <td>Partiel</td>
   <td>
    <ol>
     <li>La plupart des navigateurs ne prennent en charge cette propriété que pour l'élément {{HTMLElement("select")}}.</li>
    </ol>
   </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Bordure et arrière-plan</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("background")}}</th>
   <td>Partiel</td>
   <td>Partiel</td>
   <td colspan="1" rowspan="3">
    <ol>
     <li>La plupart des navigateurs ne prennent en charge cette propriété que pour l'élément {{HTMLElement("select")}}.</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("border-radius")}}</th>
   <td>Partiel</td>
   <td>Partiel</td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("box-shadow")}}</th>
   <td>Non</td>
   <td>Partiel</td>
  </tr>
 </tbody>
</table>

<h3 id="Boîtes_à_sélection_(multilignes)">Boîtes à sélection (multilignes)</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Propriété</th>
   <th scope="col" style="text-align: center;">N</th>
   <th scope="col" style="text-align: center;">A</th>
   <th scope="col">Note</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Modèle de boîte CSS</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("width")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("height")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("border")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("margin")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("padding")}}</th>
   <td>Partiel</td>
   <td>Partiel</td>
   <td>
    <ol>
     <li>Opera ne prend pas en charge {{cssxref("padding-top")}} et {{cssxref("padding-bottom")}} sur l'élément {{HTMLElement("select")}}.</li>
    </ol>
   </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Texte et polices</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("color")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("font")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td>Voir la note à propos de {{cssxref("line-height")}}.</td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("letter-spacing")}}</th>
   <td>Partiel</td>
   <td>Partiel</td>
   <td>
    <ol>
     <li>IE9 ne prend pas en charge cette propriété sur les éléments {{HTMLElement("select")}}, {{HTMLElement("option")}}, et {{HTMLElement("optgroup")}} ; les navigateurs fondés sur WebKit sur Mac OSX ne prennent pas en charge cette propriété sur les éléments {{HTMLElement("option")}} et {{HTMLElement("optgroup")}}.</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-align")}}</th>
   <td>No</td>
   <td>No</td>
   <td>
    <ol>
     <li>IE9 sous Windows 7 et les navigateurs fondés sur WebKit sous Mac OSX ne prennent pas en charge cette propriété sur ce widget.</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-decoration")}}</th>
   <td>No</td>
   <td>No</td>
   <td>
    <ol>
     <li>Uniquement pris en charge par Firefox et IE9+.</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-indent")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-overflow")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-shadow")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-transform")}}</th>
   <td>Partiel</td>
   <td>Partiel</td>
   <td>
    <ol>
     <li>La plupart des navigateurs ne prennent en charge cette propriété que pour l'élément {{HTMLElement("select")}}.</li>
    </ol>
   </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Bordure et arrière-plan</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("background")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("border-radius")}}</th>
   <td>Yes</td>
   <td>Yes</td>
   <td>
    <ol>
     <li>Sur Opera la propriété {{cssxref("border-radius")}} n'est appliquée que si une bordure est explicitement définie.</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("box-shadow")}}</th>
   <td>Non</td>
   <td>Partiel</td>
   <td>
    <ol>
     <li>IE9 ne prend pas en charge cette propriété.</li>
    </ol>
   </td>
  </tr>
 </tbody>
</table>

<h3 id="Datalist">Datalist</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Propriété</th>
   <th scope="col" style="text-align: center;">N</th>
   <th scope="col" style="text-align: center;">A</th>
   <th scope="col">Note</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Modèle de boîte CSS</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("width")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("height")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("border")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("margin")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("padding")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Texte et polices</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("color")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("font")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("letter-spacing")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-align")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-decoration")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-indent")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-overflow")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-shadow")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-transform")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Bordure et arrière-plan</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("background")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("border-radius")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("box-shadow")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
 </tbody>
</table>

<h3 id="Sélecteur_de_fichiers">Sélecteur de fichiers</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Propriété</th>
   <th scope="col" style="text-align: center;">N</th>
   <th scope="col" style="text-align: center;">A</th>
   <th scope="col">Note</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Modèle de boîte CSS</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("width")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("height")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("border")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("margin")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("padding")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Texte et polices</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("color")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("font")}}</th>
   <td>No</td>
   <td>No</td>
   <td>
    <ol>
     <li>Pris en charge mais il y a trop d'incohérence entre les navigateurs pour que ce soit fiable.</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("letter-spacing")}}</th>
   <td>Partiel</td>
   <td>Partiel</td>
   <td>
    <ol>
     <li>Beaucoup de navigateurs appliquent cette propriété sur le bouton de sélection.</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-align")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-decoration")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-indent")}}</th>
   <td>Partiel</td>
   <td>Partiel</td>
   <td>
    <ol>
     <li>Agit plus ou moins comme une marge supplementaire en dehors du widget.</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-overflow")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-shadow")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-transform")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Bordure et arrière-plan</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("background")}}</th>
   <td>No</td>
   <td>No</td>
   <td>
    <ol>
     <li>Pris en charge mais il y a trop d'incohérence entre les navigateurs pour que ce soit fiable.</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("border-radius")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("box-shadow")}}</th>
   <td>Non</td>
   <td>Partiel</td>
   <td>
    <ol>
     <li>IE9 ne prend pas en charge cette propriété.</li>
    </ol>
   </td>
  </tr>
 </tbody>
</table>

<h3 id="Sélecteurs_de_date">Sélecteurs de date</h3>

<p>Beaucoup de propriétés sont prises en charge mais il y a trop d'incohérence entre les navigateurs pour que ce soit fiable.</p>

<table>
 <thead>
  <tr>
   <th scope="col">Propriété</th>
   <th scope="col" style="text-align: center;">N</th>
   <th scope="col" style="text-align: center;">A</th>
   <th scope="col">Note</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Modèle de boîte CSS</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("width")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("height")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("border")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("margin")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("padding")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Texte et polices</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("color")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("font")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("letter-spacing")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-align")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-decoration")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-indent")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-overflow")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-shadow")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-transform")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Bordure et arrière-plan</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("background")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("border-radius")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("box-shadow")}}</th>
   <td>Non</td>
   <td>Non</td>
   <td> </td>
  </tr>
 </tbody>
</table>

<h3 id="Sélecteurs_de_couleurs">Sélecteurs de couleurs</h3>

<p>Il n'y a pas actuellement suffisamment d'implémentation pour obtenir des comportements fiables.</p>

<table>
 <thead>
  <tr>
   <th scope="col">Propriété</th>
   <th scope="col" style="text-align: center;">N</th>
   <th scope="col" style="text-align: center;">A</th>
   <th scope="col">Note</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Modèle de boîte CSS</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("width")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("height")}}</th>
   <td>No</td>
   <td>Oui</td>
   <td>
    <ol>
     <li>Opera gère cette propriété comme pour un widget <code>select </code>avec les mêmes restrictions.</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("border")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("margin")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("padding")}}</th>
   <td>No</td>
   <td>Oui</td>
   <td>
    <ol>
     <li>Opera gère cette propriété comme pour un widget <code>select </code>avec les mêmes restrictions.</li>
    </ol>
   </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Texte et polices</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("color")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("font")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("letter-spacing")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-align")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-decoration")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-indent")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-overflow")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-shadow")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-transform")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Bordure et arrière-plan</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("background")}}</th>
   <td>No</td>
   <td>No</td>
   <td colspan="1" rowspan="3">
    <ol>
     <li>Pris en charge mais il y a trop d'incohérence entre les navigateurs pour que ce soit fiable.</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("border-radius")}}</th>
   <td>No</td>
   <td>No</td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("box-shadow")}}</th>
   <td>No</td>
   <td>No</td>
  </tr>
 </tbody>
</table>

<h3 id="Widgets_meter_et_progress">Widgets <code>meter</code> et <code>progress</code></h3>

<p>Il n'y a pas actuellement suffisemment d'implémentation pour obtenir des comportements fiables.</p>

<table>
 <thead>
  <tr>
   <th scope="col">Propriété</th>
   <th scope="col" style="text-align: center;">N</th>
   <th scope="col" style="text-align: center;">A</th>
   <th scope="col">Note</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Modèle de boîte CSS</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("width")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("height")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("border")}}</th>
   <td>Partiel</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("margin")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("padding")}}</th>
   <td>Oui</td>
   <td>Partiel</td>
   <td>
    <ol>
     <li>Chrome cache les éléments {{HTMLElement("progress")}} et {{HTMLElement("meter")}} quand la propriété {{cssxref("padding")}} est appliquée sur un élément altéré.</li>
    </ol>
   </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Texte et polices</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("color")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("font")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("letter-spacing")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-align")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-decoration")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-indent")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-overflow")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-shadow")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-transform")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Bordure et arrière-plan</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("background")}}</th>
   <td>No</td>
   <td>No</td>
   <td colspan="1" rowspan="3">
    <ol>
     <li>Pris en charge mais il y a trop d'incohérence entre les navigateurs pour que ce soit fiable.</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("border-radius")}}</th>
   <td>No</td>
   <td>No</td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("box-shadow")}}</th>
   <td>No</td>
   <td>No</td>
  </tr>
 </tbody>
</table>

<h3 id="Widget_range">Widget <code>range</code></h3>

<p>Il n'y a pas de méthode standard pour changer le style de la poignée de<code> range</code> et Opera n'a aucun moyen de modifier le rendu par défaut du widget <code>range</code>.</p>

<table>
 <thead>
  <tr>
   <th scope="col">Propriété</th>
   <th scope="col" style="text-align: center;">N</th>
   <th scope="col" style="text-align: center;">A</th>
   <th scope="col">Note</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Modèle de boîte CSS</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("width")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("height")}}</th>
   <td>Partiel</td>
   <td>Partiel</td>
   <td>
    <ol>
     <li>Chrome et Opera ajoutent quelque espace supplémentaire autour du widget, alors que Opera sous Windows 7 réduit la poignée de <code>range</code>.</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("border")}}</th>
   <td>Non</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("margin")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("padding")}}</th>
   <td>Partiel</td>
   <td>Oui</td>
   <td>
    <ol>
     <li>La propriété {{cssxref("padding")}} est appliquée, mais elle n'a aucun effet visible.</li>
    </ol>
   </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Texte et polices</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("color")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("font")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("letter-spacing")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-align")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-decoration")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-indent")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-overflow")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-shadow")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-transform")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Bordure et arrière-plan</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("background")}}</th>
   <td>No</td>
   <td>No</td>
   <td colspan="1" rowspan="3">
    <ol>
     <li>Pris en charge mais il y a trop d'incohérence entre les navigateurs pour que ce soit fiable.</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("border-radius")}}</th>
   <td>No</td>
   <td>No</td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("box-shadow")}}</th>
   <td>No</td>
   <td>No</td>
  </tr>
 </tbody>
</table>

<h3 id="Boutons_image">Boutons image</h3>

<table>
 <thead>
  <tr>
   <th scope="col">Propriété</th>
   <th scope="col" style="text-align: center;">N</th>
   <th scope="col" style="text-align: center;">A</th>
   <th scope="col">Note</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Modèle de boîte CSS</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("width")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("height")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("border")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("margin")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("padding")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td> </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Texte et polices</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("color")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("font")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("letter-spacing")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-align")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-decoration")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-indent")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-overflow")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-shadow")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("text-transform")}}</th>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td style="text-align: center; vertical-align: top;">N.A.</td>
   <td> </td>
  </tr>
 </tbody>
 <tbody>
  <tr>
   <th colspan="4" scope="col"><em>Bordure et arrière-plan</em></th>
  </tr>
  <tr>
   <th scope="row">{{cssxref("background")}}</th>
   <td>Oui</td>
   <td>Oui</td>
   <td colspan="1"> </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("border-radius")}}</th>
   <td>Partiel</td>
   <td>Partiel</td>
   <td colspan="1">
    <ol>
     <li>IE9 ne prend pas en charge cette propriété.</li>
    </ol>
   </td>
  </tr>
  <tr>
   <th scope="row">{{cssxref("box-shadow")}}</th>
   <td>Partiel</td>
   <td>Partiel</td>
   <td colspan="1">
    <ol>
     <li>IE9 ne prend pas en charge cette propriété.</li>
    </ol>
   </td>
  </tr>
 </tbody>
</table>

<p>{{PreviousMenu("Web/Guide/HTML/Formulaires/Advanced_styling_for_HTML_forms", "Web/Guide/HTML/Formulaires")}}</p>

<h2 id="Dans_ce_module">Dans ce module</h2>

<ul>
 <li><a href="/fr/docs/Web/Guide/HTML/Formulaires/Mon_premier_formulaire_HTML">Mon premier formulaire HTML</a></li>
 <li><a href="/fr/docs/Web/Guide/HTML/Formulaires/Comment_structurer_un_formulaire_HTML">Comment structurer un formulaire HTML</a></li>
 <li><a href="/fr/docs/Web/Guide/HTML/Formulaires/Les_blocs_de_formulaires_natifs">Les widgets natifs pour formulaire</a></li>
 <li><a href="/fr/docs/Web/Guide/HTML/Formulaires/Envoyer_et_extraire_les_données_des_formulaires">Envoi des données de formulaire</a></li>
 <li><a href="/fr/docs/Web/Guide/HTML/Formulaires/Validation_donnees_formulaire">Validation des données de formulaire</a></li>
 <li><a href="/fr/docs/Web/Guide/HTML/Formulaires/Comment_construire_des_widgets_de_formulaires_personnalisés">Comment construire des widgets personnalisés pour formulaire</a></li>
 <li><a href="/fr/docs/Web/Guide/HTML/Formulaires/Sending_forms_through_JavaScript">Envoi de formulaires à l'aide du JavaScript</a></li>
 <li><a href="/fr/docs/Web/Guide/HTML/Formulaires/HTML_forms_in_legacy_browsers">Formulaires HTML dans les navigateurs anciens</a></li>
 <li><a href="/fr/docs/Web/Guide/HTML/Formulaires/Apparence_des_formulaires_HTML">Mise en forme des formulaires HTML</a></li>
 <li><a href="/fr/docs/Web/Guide/HTML/Formulaires/Advanced_styling_for_HTML_forms">Mise en forme avancée des formulaires HTML</a></li>
 <li>Table de compatibilité des propriétés pour les widgets de formulaire</li>
</ul>