参考
====


模板国际化
==========


* 安装gettext

    要使用国际化，必须安装 `GNU gettext <http://www.gnu.org/software/gettext/>`_ 。

    如果你是windows，直接访问 `windows Gettext <https://mlocati.github.io/articles/gettext-iconv-windows.html>`_


* settings.py配置


.. code-block:: python
    :linenos:
    :emphasize-lines: 1,7,11

    LANGUAGES = (
        ('en', ('English')),
        ('zh-hans', ('中文简体')),
        ('zh-hant', ('中文繁體')),
    )

    LOCALE_PATHS = (
        os.path.join(BASE_DIR, 'locale'),
    )

    TEMPLATE_CONTEXT_PROCESSORS = (
        "django.core.context_processors.i18n",
    )


* 工程根目录新建locale文件夹


* 在模板文件中引用国际化标签


 ``{% trans "Welcome to CMS monitor platform" %}``


* 生成po国际化文件


  ``python manage.py makemessages -l zh_hans``

  ``python manage.py makemessages -l en``

  此时，在locale目录下生成

    ``zh_hans/LC_MESSAGES/django.mo``

    ``en/LC_MESSAGES/django.mo``


* po文件


  ``msgid "Welcome to CMS monitor platform"``

  ``msgstr ""``


  msgid：是模板中的标签

  msgstr：是对应语言的翻译，这里需要 **自行翻译**

* 生成mo文件

  ``python manage.py compilemessages``


异常
    比较接近的msgid，生成po文件时可能输出以下标签，提示可能两个相近，如果确认不同，必须去掉，翻译才会生效

    #, fuzzy

    #| msgid "Change Language"


切换多语言代码

.. code-block:: python
    :linenos:

    <form action="{% url 'set_language' %}" method="post">{% csrf_token %}
        <input name="next" type="hidden" value="{{ redirect_to }}" />
        <select name="language">
            {% get_current_language as LANGUAGE_CODE %}
            {% get_available_languages as LANGUAGES %}
            {% get_language_info_list for LANGUAGES as languages %}
            {% for language in languages %}
                <option value="{{ language.code }}"{% if language.code == LANGUAGE_CODE %} selected{% endif %}>
                    {{ language.name_local }} ({{ language.code }})
                </option>
            {% endfor %}
        </select>
        <input type="submit" value="Go" />
    </form>

