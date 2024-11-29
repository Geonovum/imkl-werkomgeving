# Bijlage: Changelog IMKL

Wijzigingen in het Informatiemodel kabels en leidingen.

Hieronder staan de wijzigingen die in deze versie hebben plaatsgevonden na [IMKL versie 2.0](https://docs.geostandaarden.nl/kl/def-st-imkl-20210715/)
Er worden alleen wezenlijke veranderingen genoemd die invloed hebben op betrokkenen als software-ontwikkelaars. Dus bv geen correcties op typefouten, spelling of leesbaarheid.



## Wijzigingen doorgevoerd in versie 3.0

|**nummer**| **Github issue**                                 | **Soort wijziging**                  | **Wijziging**                                |
| ---------|------------------------------------------------- | ------------------------------------ | -------------------------------------------- |
| 1        |[307](https://github.com/Geonovum/imkl2015-review/issues/307) | Attribuut toegevoegd                 | Toegevoegd: ExtraDetailInfo.aanlegmethodeGestuurdeBoring|
| 2        |[314](https://github.com/Geonovum/imkl2015-review/issues/314)| Attribuut toegevoegd                  | Toegevoegd: KabelOfLeiding.kleur|
| 3        |[314](https://github.com/Geonovum/imkl2015-review/issues/314)| Attribuut toegevoegd                 | Toegevoegd: KabelOfLeiding.fysiekeIdentificatie|
| 4        |[324](https://github.com/Geonovum/imkl2015-review/issues/324)| Attribuut toegevoegd                    | Toegevoegd: Mantelbuis.eigenaar|
| 5        |[324](https://github.com/Geonovum/imkl2015-review/issues/324)| Attribuut toegevoegd                     | Toegevoegd: Mantelbuis.gebruiktVan |
| 6        |[344](https://github.com/Geonovum/imkl2015-review/issues/344)| Attribuut verwijderd                     | Verwijderd: Organisatie.postbusadres |
| 7        |[345](https://github.com/Geonovum/imkl2015-review/issues/345)| Multipliciteit aangepast              | Buisspecifiek.buismateriaalType 0..1 -> 1|
| 8        |[345](https://github.com/Geonovum/imkl2015-review/issues/345)| Multipliciteit aangepast              | KabelSpecifiek.kabeldiameter 0..1 -> 1|
| 9        |[345](https://github.com/Geonovum/imkl2015-review/issues/345)| Constraint              | Voor Duct en Kabelbed: AantalKabelsIsVerplicht|
| 10       |[345](https://github.com/Geonovum/imkl2015-review/issues/345)| Multipliciteit aangepast              | KabelEnLeidingContainer.bovengrondsZichtbaar 0..1 -> 1|
| 11       |[345](https://github.com/Geonovum/imkl2015-review/issues/345)| Multipliciteit aangepast              | OverigSpecifiek.pressure 0..1 -> 1|
| 12       |[345](https://github.com/Geonovum/imkl2015-review/issues/345)| Constraint              | Appurtenance.specifiekAppurtenanceType 0..1 -> 0|
| 13       |[345](https://github.com/Geonovum/imkl2015-review/issues/345)| Multipliciteit aangepast              | ContainerLeidingelement.bovengrondsZichtbaar 0..1 -> 1|
| 14       |[345](https://github.com/Geonovum/imkl2015-review/issues/345)| Constraint              | Rioolleiding: pressure is verplicht|
| 15       |[345](https://github.com/Geonovum/imkl2015-review/issues/345)| Constraint              | Waterleiding: pressure is verplicht|
| 16       |[345](https://github.com/Geonovum/imkl2015-review/issues/345)| Constraint              | ThermischePijpleiding: pressure is verplicht|
| 17       |[346](https://github.com/Geonovum/imkl2015-review/issues/346)| Multipliciteit aangepast              | GebiedsinformatieAanvraag.soortwerkzaamheden 0..* -> 0..1|
| 18       |[346](https://github.com/Geonovum/imkl2015-review/issues/346)| Datatype aangepast              | GebiedsinformatieAanvraag.soortwerkzaamheden.WerkzaamhedenInfo|
| 19      |[346](https://github.com/Geonovum/imkl2015-review/issues/346)| Gegevensgroep toegevoegd              | WerkzaamhedenInfo|
| 20      |[346](https://github.com/Geonovum/imkl2015-review/issues/346)| Attribuut toegevoegd              | WerkzaamhedenInfo.soortwerkzaamheden|
| 21      |[346](https://github.com/Geonovum/imkl2015-review/issues/346)| Attribuut toegevoegd              | WerkzaamhedenInfo.methode|
| 22      |[346](https://github.com/Geonovum/imkl2015-review/issues/346)| Attribuut toegevoegd              | WerkzaamhedenInfo.maximaleWerkdiepte|
| 23       |[347](https://github.com/Geonovum/imkl2015-review/issues/347)| Attribuut toegevoegd              | Kabelbed.infoKabels|
| 24       |[347](https://github.com/Geonovum/imkl2015-review/issues/347)| Gegevensgroep toegevoegd              | InfoKabelbedkabel|
| 25       |[347](https://github.com/Geonovum/imkl2015-review/issues/347)| Attribuut toegevoegd              | InfoKabelbedkabel.currentStatus|
| 26       |[347](https://github.com/Geonovum/imkl2015-review/issues/347)| Attribuut toegevoegd              | InfoKabelbedkabel.nominalVoltage|
| 27      |[347](https://github.com/Geonovum/imkl2015-review/issues/347)| Attribuut toegevoegd              | InfoKabelbedkabel.kabelDiameter|
| 28       |[347](https://github.com/Geonovum/imkl2015-review/issues/347)| Attribuut toegevoegd              | InfoKabelbedkabel.materiaal|
| 29       |[347](https://github.com/Geonovum/imkl2015-review/issues/347)| Attribuut toegevoegd              | InfoKabelbedkabel.kleur|
| 30       |[347](https://github.com/Geonovum/imkl2015-review/issues/347)| Attribuut toegevoegd              | InfoKabelbedkabel.fysiekeIdentificatie|
| 31     |[353](https://github.com/Geonovum/imkl2015-review/issues/353)| Objecttype aangepast             | Bijlage en EisVoorzorgsmaatregelBijlage samengevoegd en Bijlage verwijderd|
| 32       |[347](https://github.com/Geonovum/imkl2015-review/issues/347)| Attribuut toegevoegd              | InfoKabelbedkabel.materiaal|
| 33       |[347](https://github.com/Geonovum/imkl2015-review/issues/347)| Attribuut toegevoegd              | InfoKabelbedkabel.kleur|
| 34       |[347](https://github.com/Geonovum/imkl2015-review/issues/347)| Attribuut toegevoegd              | InfoKabelbedkabel.fysiekeIdentificatie|
| 35       |[353](https://github.com/Geonovum/imkl2015-review/issues/353)| Objecttype aangepast             | Bijlage en EisVoorzorgsmaatregelBijlage samengevoegd en Bijlage verwijderd|
| 36       |[353](https://github.com/Geonovum/imkl2015-review/issues/353)| Objecttype aangepast             | Bijlage en EisVoorzorgsmaatregelBijlage samengevoegd en Bijlage verwijderd|
| 37       |[318](https://github.com/Geonovum/imkl2015-review/issues/318)| Multipliciteit aangepast             |PostbusAdres.landcode 0..1 -> 1: Let op! dit was in het IMKL-wiond.xsd al zo en is dus geen schema aanpassing |
| 38       |[318](https://github.com/Geonovum/imkl2015-review/issues/318)| Multipliciteit aangepast             |Adres.landcode 0..1 -> 1: Let op dit was in het IMKL-wibon.xsd al zo en is dus geen schema aanpassing |
| 39       |[333](https://github.com/Geonovum/imkl2015-review/issues/333)| Constraint toegevoegd             |GebiedsinformatieAanvraag.referentie heeft maximaal 60 karakters|
| 40       |[309](https://github.com/Geonovum/imkl2015-review/issues/309)| Tekst/regel aanpassing            |In paragraaf [Nadere GML implementatie specificaties](#nadere-gml-implementatie-specificaties): gml:Arc en gml:Circle zijn niet toegestaan|
| 41       || Attribuut toegevoegd            |Mantelbuis.kleur|
| 42       |[346](https://github.com/Geonovum/imkl2015-review/issues/346)| Constraints            |GebiedsinformatieAanvraag: constraints herformuleerd|
| 43       |[307](https://github.com/Geonovum/imkl2015-review/issues/307)| Multipliciteit aangepast           |ExtraDetailInfo.bestandIdentificator 1 -> 0..1|
| 44       |[307](https://github.com/Geonovum/imkl2015-review/issues/307)| Multipliciteit aangepast           |ExtraDetailInfo.ligging 1 -> 0..1|