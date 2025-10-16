use-case
    title Диаграмма прецедентов системы учета ячменя и солода на элеваторе
    
    actor "Начальник элеватора" as Chief
    actor "Мастер элеватора" as Master
    actor "Весовщик" as Weigher
    actor "Лаборант" as Lab
    actor "Бухгалтер по зерну" as Accountant
    actor "Кладовщик отходов" as Storekeeper
    actor "Администратор" as Admin

    usecase "UC-1: Управление учетными записями" as UC1
    usecase "UC-2: Ведение справочников" as UC2
    usecase "UC-3: Регистрация поступления партии" as UC3
    usecase "UC-4: Фиксация результатов взвешивания" as UC4
    usecase "UC-5: Ввод результатов лабораторного анализа" as UC5
    usecase "UC-6: Расчет норм естественной убыли" as UC6
    usecase "UC-7: Формирование акта приемки" as UC7
    usecase "UC-8: Оформление подработки партии" as UC8
    usecase "UC-9: Учет образования отходов" as UC9
    usecase "UC-10: Передача сырья в производство" as UC10
    usecase "UC-11: Проведение инвентаризации" as UC11
    usecase "UC-12: Формирование отчетности" as UC12

    Chief --> UC3
    Chief --> UC7
    Chief --> UC8
    Chief --> UC11
    Chief --> UC12
    
    Master --> UC3
    Master --> UC7
    Master --> UC8
    Master --> UC10
    
    Weigher --> UC4
    
    Lab --> UC5
    
    Accountant --> UC12
    
    Storekeeper --> UC9
    
    Admin --> UC1
    Admin --> UC2

    UC3 ..> UC4 : include
    UC3 ..> UC5 : include
    UC7 ..> UC6 : include
    UC8 ..> UC9 : include