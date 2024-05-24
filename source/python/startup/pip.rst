.. _pip:

======================
pip (менеджер пакетів Python)
======================

pip (псевдонім pip3 для Python 3) — менеджер пакетів Python, написаний на Python. Python Software Foundation рекомендує використовувати pip для встановлення програм та залежностей Python. Pip підключається до загальнодоступного онлайн-репозиторію пакетів Python (тобто `Індексу пакетів PythonPyPi<https://pypi.org/>` - ``PyPi``) для реалізації установки пакетів програмного забезпечення та керування ними. Його також можна налаштувати для підключення до локального або віддаленого репозиторію пакетів програмного забезпечення, забезпечуючи реалізацію пропозиції щодо розширення Python (PEP) 503.


Оновлення самого pip
============

Після складання Python virtualenv та запуску pip вам зазвичай буде запропоновано оновити сам pip до останньої версії. На цьому етапі можна оновити pip:

.. literalinclude:: pip/pip_upgrade_pip
   :caption: Оновлення pip до останньої версії

Якщо версія pip занадто висока, ви також можете зменшити версію:

.. literalinclude:: pip/pip_downgrade_pip
   :caption: Зниження версії pip

Встановлення певної версії Python
=========================

У деяких розробках програмного забезпечення використовуються більш старі версії серед програмних пакетів Python, тому вам необхідно вказати версію інсталяції:

.. literalinclude:: pip/pip_install_specific_package
   :caption: pip встановлює вказану версію пакету Python

- Крім того, ``pip`` передбачені методи встановлення для вказівки діапазонів версій:

.. literalinclude:: pip/pip_install_specific_range_package
   :caption: pip встановлює пакети Python у вказаному діапазоні версій

Зниження версії (пакет вже встановлено)
-------------------------------

- Якщо ви встановили пакет програмного забезпечення вищої версії і хочете знизити його версію, метод, що використовується, насправді аналогічний описаному вище методу встановлення зазначеного пакета Python, але вам необхідно використовувати параметр ``-I``( ``--ignore-installed`` ), щоб вказати, що встановлена версія ігнорується або використовувати обов'язкові параметри ``--force-reinstall``:

.. literalinclude:: pip/pip_install_specific_package_force
   :caption: pip знижує версію вказаного пакету Python (примусове встановлення)

Приклад:

У :ref:`` я зіткнувся з тим, що старий проект несумісний із Django 4.x, тому мені довелося перейти на Django 3.2.21 (оскільки виробниче середовище не мало доступу до зовнішньої мережі, для цього використовувався pip). встановити пакет Python в автономному режимі

.. literalinclude:: pip/pip_download
   :caption: Завантажити Django-3.2.21 оффлайн

.. literalinclude:: pip/pip_install_specific_package_force_offline
   :caption: Примусове встановлення вказаної версії в автономному режимі (зниження версії)

Видно, що спочатку фактично видаляється стара вища версія (видаляється також та ж версія), а потім встановлюється (знижується) вказана версія:

.. literalinclude:: pip/pip_install_specific_package_force_offline_output
   :caption: Примусове автономне встановлення зазначеної версії (Downgrade) виводить інформацію

Перевірка встановлених пакетів (версій)
=========================

- Виконайте , щоб переглянути всі встановлені пакети Python:``pip list``:

.. literalinclude:: pip/pip_list
   :caption: ``pip list`` Перевірити всі пакети

Вивiд в консолi показує:

.. literalinclude:: pip/pip_list_output
   :caption: ``pip list`` Виведення переліку пакетів із версіями

- Використовуйте для перегляду інформації про довіру інсталяційного пакету: ``pip show``:

.. literalinclude:: pip/pip_show
   :caption: ``pip show`` Показати детальну інформацію про пакет

Вивiд в консолi показує:

.. literalinclude:: pip/pip_show_output
   :caption: ``pip show`` Результат виводу команди

Выполнить установку ``setup.py``
=========================

Деякі пакети програмного забезпечення Python необхідно скомпілювати та встановити в систему. Наприклад ``mysqlclient``, завантажуваний пакет є tar-пакет ``mysqlclient-2.2.0.tar.gz``. Після розпакування у кореневому каталозі пакету знаходиться файл ``setup.py``. То як його встановити?

.. literalinclude:: pip/pip_setup.py
   :caption: ``setup.py`` Як встановити пакети Python

Справдi просто?! Зверніть увагу, що він не запускається безпосередньо (докладні інструкції щодо написання сценарію установки ``setup.py`` є в `офіційній документації Python <https://docs.python.org/3/distutils/setupscript.html>`)

Посилання
======

- `Pip: Python Package Management Basics <https://3v-host.com/blog/pip-python-package-management-basics/>`_
- `Installing specific package version with pip <https://stackoverflow.com/questions/5226311/installing-specific-package-version-with-pip>`_
- `wikipedia: pip (package manager) <https://en.wikipedia.org/wiki/Pip_(package_manager)>`_
- `How do I check the versions of Python modules? <https://stackoverflow.com/questions/20180543/how-do-i-check-the-versions-of-python-modules>`_
- `What is setup.py? <https://stackoverflow.com/questions/1471994/what-is-setup-py>`_
