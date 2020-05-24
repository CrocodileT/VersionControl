Программа с помощью меню реализует следующие команды:

	Базовые:
 - open <fname> <version> - открываем файл в версии <version>. Если версия не задана - открываем корневую версию (ее номер по умолчанию равен 0)
 - print - отображает на экран текущую версию файла, с которым работаем.

	Ф-ии редактирования:
 - edit <i> <j> <data> - замена в текущей версии файла данных с индексом i (включительно) по индекс j (не включительно) на символы data
 - add <i> <data> - добавление к текущей версии файла данных, начиная с позиции с индексом i 
 - remove <i> <j> - удаляем данные, как в лабе 3

	Ф-ии работы с версиями:
 - push - сохраняем текущую версию в виде разностного образа с предыдущей версией (не с корневой!). Функция возвращает номер версии, по которому можно впоследствии откатиться к этой версии.
 - pull <№ версии> - делает текущей версию с переданным номером (т.е. перемещается по дереву версий, получая текущую версию из разностной информации на пути). Дальнейшее редактирование запоминается как изменения(разность) относительно этой (текущей) версией.
 - delete_version <<№ версии> - удаляет версию из дерева. При этом корректируются наследники этой версии в дереве - разность теперь высчитывается относительно нового корня(предка удаленной вершины)
 - rebase - перебалансирует дерево, помещая текущую версию в корень дерева путем перерассчета разностей версий относительно нового корня. Все номера версий остаются прежними, кроме 2х версий - текущей и бывшей корневой. Их номера меняются местами (т.е. текущая версия становится корнем дерева
с номером 0, прежний корень забирает себе бывший номер этой версии)
