







Описание дэшборда с bgp-communities.

Ссылка: prod_dir/Geo_BGP_communities_with_dicts_mod_from_1810__msk__spb__novosib__with_fixed_mv-1697633207308.json

  <table>
    <thead>
      <tr>
        <th>Название визуализации</th>
        <th>Ссылка</th>
        <th>Что отображает</th>
        <th>Фильтры</th>
        <th>Источник</th>
      </tr>
    </thead>
    <tbody>
        <tr>
            <td>Intersection of the number of prefixes with the known and nonvalid bgp-communities in the context of the city (checked from 1810)</td>
            <td></td>
            <td>Отображает число анонсированных префиксов, для которых известно хотя бы одно bgp-community (т.е. подсчитывается число префиксов, для 
            которых в поле comms найдено хотя бы одно пересечение с теми bgp-communities, которые получены в результате обращения к whois). 
            Отображение происходит 
            в разрезе города (унифицированные названия из dadata) и номера автономной системы (отображается в строках визуализации). </td>
            <td>В данной визуализации предусмотрен фильтр по городу, котором был анонсирован перфикс. Значения для этого фильтра находятся в 
            переменной: (${city:singlequote}). Также предусмотрен фильтр по автономной системы. Значение для него находятся в переменной (${condition_asn:singlequote}) </td>
            <td>common_mv_1309_wo_as3216_peers_with_dict3_1710_test (materialized view) </td>
        </tr>
        <tr>
            <td>The ratio of prefixes with known and unknown bgp-communities (checked from 1810)</td>
            <td></td>
            <td>Отображает соотношение числа префиксов с известными  и неизвестными bgp-communities. 
                Считается, что префикс относится к числу тех, для которых
            известно bgp-communities, если для него найдено хотя бы одно пересечением bgp-communities, 
            перечисленных в поле comms с теми, которые были получены после выгрузки из whois</td>
            <td>В этой визуализации предусмотрен фильтр по автономной системе и городу, в котром 
                префикс был анонсирован. Значения этих фильтров находятся
            в переменной (${condition_asn:singlequote}) и (${city:singlequote}) соответственно </td>
            <td> mv_for_identified_communities_1309_wo_as3216_peers_with_dict2_1710_test (materialized view)</td>
        </tr>
        <tr>
            <td>Distribution of the number of prefixes with known bgp-communities (by date, as, community) (checked from 1810)</td>
            <td></td>
            <td>Отображает за текущую дату для выбранной автономной системы распределние числа префиксов с известными bgp-communities 
            по городам (которые ассоциированы с bgp-communities) (поле amount_of_prefs_with_founded_comms_by_city_and_asn), 
            а также общее число префиксов с известными bgp-communities по всем городам для выбранной автономной системы (за текущую дату) 
            (поле total_asn_amount_of_prefs_with_founded_comms). </td>
            <td>В этой физуализации предусмотрены фильтр по городам, в котором префикс анонсирован, а также по номеру автономной системы. 
            Значения для этих фильтров 
            находятся в переменных (${condition_asn:singlequote}) и (${city:singlequote}) соответственно</td>
            <td>common_mv_1309_wo_as3216_peers_with_dict3_1710_test (materialized view)</td>
        </tr>
        <tr>
            <td>Total number of prefixes with known bgp-communities (to check the correctness of the total) (checked from 1810)</td>
            <td></td>
            <td> Данная визуализация отображает общее число префиксов с известными 
                bgp-communities для автономной системы, которая отображается в 
            визуацизации Distribution of the number of prefixes with known  
            bgp-communities (by date, as, community) (checked from 1810). 
            Эта визуализация используется
            для проверки правильности общего числа префиксов с найденными bgp-communities 
            в столбце total_asn_amount_of_prefs_with_founded_comms. 
            Отображаемое на этой визуализации значение должно всегда совпадать со значение 
            в поле total_asn_amount_of_prefs_with_founded_comms в 
            визуализации Distribution of the number of prefixes with known bgp-communities 
            (by date, as, community) (checked from 1810) </td>
            <td> В этой физуализации предусмотрены фильтр по городам, в котором префикс анонсирован, 
                а также по номеру автономной системы. Значения для этих фильтров  находятся в 
                переменных (${condition_asn:singlequote}) и (${city:singlequote}) </td>
            <td>common_mv_1309_wo_as3216_peers_with_dict3_1710_test</td>
        </tr>
        <tr>
            <td>Distribution of the number of prefixes with known bgp-communities (by date, as, community) (with % of founded prefs by cities) 
            (checked from 1810) </td>
            <td></td>
            <td>Отображает за текущую дату для выбранной автономной системы распределние числа префиксов с известными bgp-communities по 
            городам (которые ассоциированы с bgp-communities) (поле amount_of_prefs_with_founded_comms_by_city_and_asn), а также общее число 
            префиксов с известными bgp-communities по всем городам для выбранной автономной системы (за текущую дату) (поле total_asn_amount_of_prefs_with_founded_comms). Кроме того, в поле percentage_of_prefixes_with_founded_comm_by_cities отображается 
            для каждого города процент префиксов с известными bgp-communities (от общего числа 
            префиксов с идентифицированными communities). </td>
            <td>В этой физуализации предусмотрены фильтр по городам, в котором префикс анонсирован, а также по номеру автономной системы. 
            Значения для этих фильтров находятся в переменных (${condition_asn:singlequote}) и (${city:singlequote}) соответственно</td>
            <td>common_mv_1309_wo_as3216_peers_with_dict3_1710_test</td>
        </tr>
        <tr>
            <td>Total number of prefixes with known bgp-communities (%) (to check the correctness of the total) (checked from 1810)</td>
            <td></td>
            <td>Данная визуализация отображает общий % префиксов с известными bgp-communities для автономной системы, которая отображается в 
            визуацизации Distribution of the number of prefixes with known bgp-communities (by date, as, community) (with % of founded prefs by cities) 
            (checked from 1810). Эта визуализация используется
            для проверки правильности общего % префиксов с найденными bgp-communities в столбце percentage_of_prefixes_with_founded_comm_by_cities. 
            В этой визуализации всегда должно отображаться 100%. </td>
            <td>В этой физуализации предусмотрены фильтр по городам, в котором префикс анонсирован, а также по номеру автономной системы. 
            Значения для этих фильтров находятся в переменных (${condition_asn:singlequote}) и (${city:singlequote}) соответственно</td>
            <td>common_mv_1309_wo_as3216_peers_with_dict3_1710_test</td>
        <tr>
        </tr>
    </tbody>
    <tfoot>
        </tr>
            <td>Distribution of the number of prefixes with known  bgp-communities (by date, as, community) (checked from 1810) (with ip_prefix field) 
            (with ip_prefix field)</td>
            <td></td>
            <td>Отображает за текущую дату для выбранной автономной системы распределние числа префиксов с известными bgp-communities по городам 
            (которые ассоциированы с bgp-communities) (поле amount_of_prefs_with_founded_comms_by_city_and_asn), а также общее число префиксов с 
            известными bgp-communities по всем городам для выбранной автономной системы (за текущую дату) (поле total_asn_amount_of_prefs_with_founded_comms). 
            Кроме того, в поле ip_prefix отображатся те префиксы,
            которые входят в число префиксов в поле amount_of_prefs_with_founded_comms_by_city_and_asn. Т.е. в поле ip_prefix отображаются те префиксы, которые 
            входят в число префиксов с известными bgp-communities и относятся к городу, который указан в поле conv_city (название города/региона, которое 
            ассоциировано с bgp-community)</td>
            <td>В этой физуализации предусмотрены фильтр по городам, в котором префикс анонсирован, 
                а также по номеру автономной системы. 
            Значения для этих фильтров находятся в переменных (${condition_asn:singlequote}) и 
            (${city:singlequote}) соответственно </td>
            <td> common_mv_1309_wo_as3216_peers_with_dict3_1710_test </td>
        </tr>
    <tfoot>     
  </table>
