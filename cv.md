
# **Резюме**
Для задания по Rolling-Scopes-school.

## ФИО
Козырин Дмитрий Игоревич
<img alt="Фото резюме" width="100em" height="140em" align="right" src="https://sun9-81.userapi.com/impg/krbvG_t1mcwpLNEXLQyEK1ECbR6BMLAlJ5z6NQ/sm3R1XnNXPs.jpg?size=827x1063&quality=96&sign=4778282e6bb9a2a147f78f8861c6c472&type=album">

## Контакты для связи
* **Телефон:** +7 (937) 233-88-60
* **Электронная почта:** Kozyrin-di@yandex.ru
* **GitHub:** RigelTLT
* **Discord:** Dmitrii(@RigelTlt)

## Контактная информация о себе
* Мужчина, 27 лет, родился 17 января 1994
* Проживаю в городе Тольятти

Цели получить опыт и знание в программировании. Приоритетные языки JavaScript и Java. Проработал в сфере IT около 6 лет. Запуск, монтаж и поддержание серверов, сетей, рабочих мест, телефонии и видеонаблюдения. Разработка и тестирования системы создания заявок(ЦРМ).

**Деловые качества:** целеустремленность, дипломатичность, высокая работоспособность, коммуникабельность, быстрая обучаемость, стремление к постоянному развитию, инициативный и творческий подход в работе.

## Навыки
Знание основ программирования на языке 
* PHP
* JavaScript
* SQL
* HTML
  
Хорошее знание аппаратной части ПК и офисной техники. Знание серверов, сетевых технологий и телефонии на уровне администратора.

## Опыт работы
Поддержка и модификация ЦРМ на основе Dolibarr. Использованы языки программирования PHP, JavaScript. Проект находиться не в свободном доступе.

Модуль напоминания о загрузке
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
2 задачи из Codewars

[Square Every Digit](https://www.codewars.com/kata/546e2562b03326a88e000020)
```
function squareDigits(num){
  var arraycut = num.toString().split('');
  var arranum = arraycut.map(Number)
  var index;
  var sting='';
for (index = 0; index < arranum.length; ++index) {
    var number= arranum[index]*arranum[index];
    var sting= sting + number.toString();
}
  return Number(sting);
}
```
[Multiply](https://www.codewars.com/kata/50654ddff44f800200000004)
```
function multiply(a, b){
  var c;
  c=a * b;
  return c;
}
```
## Образование
**Образование** Высшее(магистр).

Поволжский государственный университет сервиса, Тольятти Информационный электронный сервис, Программная инженерия

| Дата поступления  | Дата окончания | Название учебного заведения | Факультет | Специальность Квалификация |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| 2012  | 2016 | Поволжский государственный университет сервиса | Информационно-технического сервиса, бюджет (очно) | Программная инженерия |
| 2016  | 2018  | Поволжский государственный университет сервиса | Магистратура Информационно-технического сервиса, бюджет (заочно) | Программная инженерия |

**Дополнительное образование:** NetCracker по курсу «Обеспечение качества программных продуктов»

## Образование
Английский (базовый уровень).