O Physics Field System permite afetar as simulações de física da [[Chaos Engine]] em runtime em uma região específica do espaço. Podem ser configurados para afetar as simulações de físicas de diferentes maneiras.

Um Field System pode ser criado no menu de criação de Blueprint selecionando a classe _FieldSystemActor_:

![[fieldsystem1.png]]

Nele podemos adicionar diversos componentes para aplicar "forças" que influem na simulação de física:

![[fieldsystem3.png]]

No event graph podemos configurar estes componentes e depois aplica-los usando o node  _Add Transient Field_

![[fieldsystem2.png]]

