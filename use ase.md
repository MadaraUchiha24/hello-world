```mermaid
use-case
    title Диаграмма прецедентов системы учета ячменя и солода на элеваторе
    
    actor "Начальник элеватора" as Chief
    actor "Мастер элеватора" as Master
    actor "Весовщик" as Weigher
    actor "Лаборант" as Lab
    actor "Бухгалтер по зерну" as Accountant
    actor "Кладовщик отходов" as Storekeeper
    actor "Администратор" as Admin

    usecase "1. Управление учетными записями\nи справочниками" as UC1
    usecase "2. Регистрация поступления партии" as UC2
    usecase "3. Фиксация результатов взвешивания" as UC3
    usecase "4. Ввод лабораторного анализа" as UC4
    usecase "5. Расчет норм естественной убыли" as UC5
    usecase "6. Оформление акта приемки" as UC6
    usecase "7. Оформление подработки партии" as UC7
    usecase "8. Учет движения отходов" as UC8
    usecase "9. Передача сырья в производство" as UC9
    usecase "10. Проведение инвентаризации" as UC10
    usecase "11. Формирование отчетности" as UC11

    ' Связи актеров с прецедентами
    Admin --> UC1
    
    Chief --> UC2
    Chief --> UC6
    Chief --> UC7
    Chief --> UC10
    Chief --> UC11
    
    Master --> UC2
    Master --> UC6
    Master --> UC7
    Master --> UC9
    Master --> UC10
    
    Weigher --> UC3
    Lab --> UC4
    Accountant --> UC11
    Storekeeper --> UC8

    ' Включения
    UC2 ..> UC3 : include
    UC2 ..> UC4 : include
    UC6 ..> UC5 : include
```