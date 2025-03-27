
tag # V1.3.0 #87

Изменения:

В области информационной архитектуры:

- Пример обновлен в соответствии с новой метамоделью SEAF CORE 1.2.9
- Пример дополнен объектами описания архитектуры в области проката фильмов
- Пример переведен на условные компании примера: flix и alfa

В области технической архитектуры:

- Объекты примера модифицированы в соответствии с изменениями сущностей ММ SEAF по результатам мерджа метамодели технической архитектуры и IAAS, в том числе на сущности:
    
    - seaf.ta.reverse.vmwarecloud.egws
    - seaf.ta.reverse.vmwarecloud.egws_fw
    - seaf.ta.reverse.vmwarecloud.egws_nat
    - seaf.ta.reverse.vmwarecloud.orgnets
    - seaf.ta.reverse.vmwarecloud.orgs
    - seaf.ta.reverse.vmwarecloud.vappnets
    - seaf.ta.reverse.vmwarecloud.vapps
    - seaf.ta.reverse.vmwarecloud.vdcgroups
    - seaf.ta.reverse.vmwarecloud.vdcs
- Для демонстрации в примере возможности DC быть в разных AZ разных провайдеров, добавлены объекты сущности placement_segment.
    
- В области управления изменениями архитектуры:
    
    - Добавлены примеры описания требований