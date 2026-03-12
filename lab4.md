```
flowchart 

title[<em>Блок ПРИБОР</em>]
subgraph Прибор
direction TB
par1((режим))-.->h3
Ini@{shape: lean-r, label: "I::"} -.- h1
HTf@{shape: lean-r, label: "Tслом = 100"}
h1(["BPEMЯ=Tслом"])==> h2["сост:=<br>сломан"]
h2 e11@ ==> h3(["режим=<br>работа"])
h3 ==> h4(["мастер<br>=своб"])
h4 ==> h5["мастер:=занят<br>Tрем:=funс(x)"]
h5 e20@ ==> h6(["ВРЕМЯ=Трем"])
h6 ==> h7["сост:=рабочий<br>мастер:=своб<br>Tслом:=func(x)"]
h7 e10@ ==> h1

h2 -.->par3((сост))
h7 -.->par3
par2((мастер))-.->h4

h5 -.->par2
h7 -.->par2
h5 -.->par4((Трем))
par4 -.-> h6
end 

subgraph Мастер
direction TB
h8("режим:=<br>отдых") ==> h9(["ВРЕМЯ=Tраб"])
h9 ==> h10["режим:=работа<br>Tотд:=func__"]
h10 ==> h11(["ВРЕМЯ=Tотд"])
h11 ==> h12["Tраб:=func__"]
h12 ==> h13{"мастер<br>=..."}
h13 ==>|"...= занят"| h14["Tрем:=Трем+<br>Траб-ВРЕМЯ"]
h13 ==>|"...= своб"| h8
h14 ==> h8
h14 -.->par4((Трем))
par2((мастер))-.->h13
h8 -.-> par1((режим))
h10 -.-> par1((режим))


Inu@{shape: lean-r, label: "I::"} -.- h8
HTr@{shape: lean-r, label: "Tраб = 9ч"}
end



classDef navig fill:#eda,stroke:#333,stroke-width:1px;
 class h15 navig;
classDef cond fill:#bee,stroke:#aaa,stroke-width:1px;
 classDef state fill:#9e8,stroke:#333,stroke-width:1px;
 class h5,h8,h2,h7,h10,h12,h14 state;
class h1,h3,h4,h6,h9,h11 cond;
style par1 fill:#fcc,stroke:#111,stroke-width:2px;
 style par2 fill:#fae,stroke:#bbb,stroke-width:2px;
 style par3 fill:#caf,stroke:#555,stroke-width:2px;
 style par4 fill:#cfc,stroke:#555,stroke-width:2px;
style Прибор fill:#e8f4fd;
style Мастер fill:#e8f4fd;
style title fill:yellow,stroke:red;
style h13 fill:yellow,stroke:red;
```
