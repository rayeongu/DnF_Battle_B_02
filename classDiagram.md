```mermaid

classDiagram
        class 캐릭터 {
            <<abstract>>
            #String 캐릭터명
            #int 레벨
            #int HP
            #int 공격력
            +int 스킬발동()*
            +String get스킬명()*
            +String get캐릭터명()
            +int get레벨()
            +int getHP()
            +int get공격력()
        }

        class 전사 {
            +전사(String 캐릭터명, int 레벨)
            +int 스킬발동()
            +String get스킬명()
        }

        class 마법사 {
            +마법사(String 캐릭터명, int 레벨)
            +int 스킬발동()
            +String get스킬명()
        }

        class 플레이어 {
            +boolean 플레이어체크(String 플레이어id)
        }

        class 전투 {
            +캐릭터 캐릭터생성(String 플레이어id, String 캐릭터명, String 직업, int 레벨)
            +String 몬스터공격(String 플레이어id, 캐릭터 character)
        }

    전사 --|> 캐릭터 : 상속 (Generalization)
    마법사 --|> 캐릭터 : 상속 (Generalization)
    전투 ..> 플레이어 : 의존 (Dependency)
    전투 ..> 캐릭터 : 의존 (Dependency)
    전투 ..> 전사 : 의존 (Dependency)
    전투 ..> 마법사 : 의존 (Dependency)
