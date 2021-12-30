# **Summary**

For the Rolling-Scopes-school assignment.

## Profile

Kozyrin Dmitriy Igorevich

<img alt="Photo resume" width="100em" height="100em" align="right" src="assets/img/avatar.jpg">

## Contacts for communication

- ** Email: ** Kozyrin-di@yandex.ru
- ** GitHub: ** RigelTLT
- ** Discord: ** Dmitrii (@RigelTlt)

## Contact information about yourself

- Male, 27 years old
- I live in the city of Togliatti

Objectives to gain experience and knowledge in programming. The priority languages ​​are JavaScript and Java. Worked in the IT field for about 6 years. Launch, installation and maintenance of servers, networks, workplaces, telephony and video surveillance. Development and testing of the application creation system (CRM).

**Business qualities:** purposefulness, diplomacy, high efficiency, sociability, quick learning, striving for continuous development, proactive and creative approach to work.

## Skills

Knowledge of the basics of programming in the language

- PHP
- JavaScript
- SQL
- HTML

Good knowledge of PC hardware and office equipment. Knowledge of servers, network technologies and telephony at the administrator level.

## Projects

Support and modification of the DTM based on Dolibarr. Used programming languages ​​PHP, JavaScript. The project is not in the public domain.

Boot reminder module

```
$min15date = date('Y-m-d H:i:s',  strtotime("".$dateseic." +15 minutes"));
$sqlzag = 'SELECT com.ref_client, com.rowid FROM '.MAIN_DB_PREFIX.'commande com LEFT JOIN '.MAIN_DB_PREFIX.'commande_extrafields comex ON com.rowid = comex.fk_object LEFT JOIN '.MAIN_DB_PREFIX.'societe soc ON com.fk_soc = soc.rowid LEFT JOIN '.MAIN_DB_PREFIX.'commande_provzag_i_zig comp ON com.rowid = comp.rowid_fk_comm WHERE soc.fournisseur = 0 AND (com.fk_user_author ='.$user->id.' OR com.fk_user_author2 ='.$user->id.') AND com.fk_statut=2 AND comex.chszagp <= "'.$dateseic1.'"';
$resqlzag = $db->query($sqlzag);

$nazag= array();
$indexzag = 0;
while ($rowzag=$db->fetch_object($resqlzag)) {
	$nazag[$indexzag] = $rowzag;
	$indexzag++;
}
if($nazag){
	for ($i = 0 ; $i < $indexzag ; ++$i)
	{
		$sqlzagprov = 'SELECT rowid FROM '.MAIN_DB_PREFIX.'commande_provzag_i_zig WHERE rowid_fk_comm = '.$nazag[$i]->rowid.'';
		$resqlzagprov = $db->query($sqlzagprov);
		$array_zagprov=$db->fetch_object($resqlzagprov);
		$zagprov =$array_zagprov->rowid;
		if(!$zagprov){
			$encodes = iconv("UTF-8","WINDOWS-1251",$nazag[$i]->ref_client);
			echo"<script>
				$.confirm({
                    title: 'Загрузка по заявке!',
                    content: 'Загрузка по заявке ".$nazag[$i]->ref_client." была совершена? Нажмите Напомнить позже для повторение оповещения через 15 мин или Изменить для изменения даты загрузки',
					buttons: {
						Подтвердить: function () {
							$.ajax({
								type: 'GET',
								url: 'http://192.168.0.34/dolibarr/zagvig.php',
								data: { ZAG: 1, IDC: '".urlencode($encodes)."', DATE: '".$dateseic1."', USER: ".$user->id.", IDCOM: ".$nazag[$i]->rowid."},
								dataType: 'html'
							});
						},
						Изменить: function () {
							$.ajax({
								type: 'GET',
								url: 'http://192.168.0.34/dolibarr/zagvig.php',
							    data: { ZAG: 3, IDC:  '".urlencode($encodes)."', DATE: '".$dateseic1."', USER: ".$user->id.", IDCOM: ".$nazag[$i]->rowid."},
								dataType: 'html'
							});
								window.open('/dolibarr/commande/cardedit.php?comid=".$nazag[$i]->rowid."&action=edit&ref=".$nazag[$i]->ref_client."&edit&nom=ZAG3&backtopage=" . $_SERVER["PHP_SELF"] ."');
						},
						Напомнить: {
							text: 'Напомнить позже',
							btnClass: 'btn-blue',
							keys: ['enter', 'shift'],
							action: function(){
								$.ajax({
									type: 'GET',
									url: 'http://192.168.0.34/dolibarr/zagvig.php',
									data: { ZAG: 0, IDC: '".urlencode($encodes)."', DATE: '".$min15date."', USER: ".$user->id.", IDCOM: ".$nazag[$i]->rowid."},
									dataType: 'html'
								});
							}
						}
					}
				});
			</script>";
		}
	}
}
```

2 Tasks from Codewars

[Square Every Digit](https://www.codewars.com/kata/546e2562b03326a88e000020)

```
function squareDigits (num) {
  var arraycut = num.toString (). split ('');
  var arranum = arraycut.map (Number)
  var index;
  var sting = '';
for (index = 0; index <arranum.length; ++ index) {
    var number = arranum [index] * arranum [index];
    var sting = sting + number.toString ();
}
  return Number (sting);
}
```

[Multiply](https://www.codewars.com/kata/50654ddff44f800200000004)

```
function multiply (a, b) {
  var c;
  c = a * b;
  return c;
}
```

## Education

**Education** Higher (Master's degree).

Volga State University of Service, Togliatti Information Electronic Service, Software Engineering

| Name of educational institution   | Faculty                                                        | Specialty Qualification |
| --------------------------------- | -------------------------------------------------------------- | ----------------------- |
| Volga State University of Service | Information and technical service, budget (in person)          | Software Engineering    |
| Volga State University of Service | Master of Information Technology Service, Budget (in absentia) | Software Engineering    |

**Additional education:** NetCracker on the course "Quality Assurance of Software Products"

## Languages

English (basic level).
