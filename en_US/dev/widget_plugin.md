# Management of plugin widgets

There are several possibilities to make custom widgets for plugins :

- the first with the toHtml function (instance method) which inherits from the eqLogic class
- by the template system (v4 only)

## ToHtml function

Thereupon, nothing special, the toHtml function must return the widget in html, you have an example [the](https://github.com/jeedom/plugin-weather/blob/beta/core/class/weather.class.php#L647)

The important thing is especially the 1st lines :

````php
$replace = $this->preToHtml($_version);
yew (!is_array ($ replace)) {
	return $ replace;
}
````

La fonction preToHtml renvoi :

- une string si le widget est en cache (si il est en cache, c'est qu'il n'y a pas eu de changements depuis la dernière génération donc autant le renvoyer tout de suite)
- un tableau avec les replaces principaux, vous avez la liste [here](https://github.com/jeedom/core/blob/alpha/core/class/eqLogic.class.php#L663)

## Le système de template

Le système de template de widget dans le code est en fait exactement le même que celui sur la page Outils -> Widget de jeedom.

Vohere un exemple :

````php
public static function templateWidget(){
	$return = array('info' => array('string' => array()));
	$return['info']['string']['state'] = array(
		'template' => 'tmplmultistate',
		'test' => array(
			array('operation' => '#value# == 2','state_light' => '<i class="icon maison-vacuum6"></i>','state_dark' => '<i class="icon maison-vacuum6"></i>'),
			array('operation' => '#value# == 3','state_light' => '<i class="fa fa-pause"></i>','state_dark' => '<i class="fa fa-pause"></i>'),
			array('operation' => '#value# > 3 || #value# < 2','state_light' => '<i class="fa fa-home"></i>','state_dark' => '<i class="fa fa-home"></i>')
		)
	);
	return $ return;
}
````

Here, we will create a new widget based on the "tmplmultistate" template (you have the list of templates [here](https://github.com/jeedom/core/tree/alpha/core/template/dashboard) it's those with tmpl in their name), for an info type command and under string type.

> **IMPORTANT**
>
> Each template is for a given type and subtype, so you have to check that the template you want to use exists for the type and subtype

Then, since it is a template with several states, you have to define the icons according to the state. It is done in the test part of the table.

Example : for the first test, we say if the value of the command is worth 2 then it will be necessary to replace the tag #\_state_# (in the html code of the template) by </i>

Another example based on another template could be :

````php
public static function templateWidget(){
	$return = array('info' => array('string' => array()));
	$return['info']['binary']['toto'] = array(
		'template '=>' tmplicon',
		'replace '=> array(
			'#_icon_on_#' => '<i class=\'icon_green icon jeedom-porte-ferme\'></i>',
			'#_icon_off_#' => '<i class=\'icon_red icon jeedom-porte-ouverte\'></i>'
			)
	);
	return $ return;
}
````

Ici, je crée un widget toto basé sur le template "tmplicon" en type info et sous-type binaire. Quand il vaut 1 alors l'icône sera <i class='icon_green icon jeedom-porte-ferme'></i> et quand il vaut 0, ça sera <i class='icon_red icon jeedom-porte-ouverte'></i>

>**TIPS**
>
> Petite astuce, vous pouvez à la place d'une icône mettre une balise image (attention au chemin)

Ensuite, pour utiliser votre widget :

````php
$cmd->setTemplate('dashboard','neato::state');
$cmd->setTemplate('mobile','neato::state');
````

It is like for a normal widget except for the name of the widget which is in the form id_plugin::name_widget. For the 2nd example, it will be id_plugin::toto


