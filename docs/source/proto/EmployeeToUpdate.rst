EmployeeToUpdate
================

.. code-block:: protobuf

    message EmployeeToUpdate
    {
        optional EmployeePermissionsPatch Permissions = 1;
        optional EmployeePositionPatch Position = 2;
        optional EmployeeCanBeInvitedForChatPatch CanBeInvitedForChat = 3;
    }

Структура содержит информацию о данных сотрудника, которые необходимо изменить. Принимается методом :doc:`../http/UpdateEmployee`.

- :ref:`Permissions <employee-permissions-patch>` - структура для изменения разрешений
- :ref:`Position <employee-position-patch>` - структура для изменения должности
- :ref:`CanBeInvitedForChat <employee-can-be-invited-to-chat-patch>` - структура для изменения необходимости отображать сотрудника в списке получателей Сообщений в веб-интерфейсе

Необходимо заполнить только те поля структуры, которые соотвествуют данным, требующим изменения.

.. _employee-permissions-patch:

EmployeePermissionsPatch
------------------------

.. code-block:: protobuf

    message EmployeePermissionsPatch
    {
        optional EmployeeDepartmentPatch Department = 1;
        optional EmployeeIsAdministratorPatch IsAdministrator = 2;
        optional EmployeeDocumentAccessLevelPatch DocumentAccessLevel = 3;
        optional EmployeeSelectedDepartmentsPatch SelectedDepartments = 4;
        repeated EmployeeAction Actions = 5;
    }

Структура содержит информацию о настройках :doc:`разрешений сотрудника <EmployeePermissions>`, которые необходимо изменить.

- :ref:`Department <employee-department-patch>` - структура для изменения подразделения
- :ref:`IsAdministrator <employee-is-administrator-patch>` - структура для изменения права администрировать организацию
- :ref:`DocumentAccessLevel <employee-document-access-level-patch>` - структура для изменения уровня доступа к документам
- :ref:`SelectedDepartments <employee-selected-departments-patch>` - структура для изменения списка подразделений, к которым имеет доступ сотрудник (играет роль только в случае *DocumentAccessLevel = SelectedDepartments*)
- :doc:`Actions <EmployeePermissions>` - действия сотрудника, права на которые требуется добавить или убрать

Необходимо заполнить только те поля структуры, которые соотвествуют данным, требующим изменения.

.. _employee-department-patch:

EmployeeDepartmentPatch
~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: protobuf

    message EmployeeDepartmentPatch
    {
        required string DepartmentId = 1;
    }

Структура для изменения подразделения сотрудника.

- *DepartmentId* - идентификатор подразделения, в которое необходимо переместить сотрудника

.. _employee-is-administrator-patch:

EmployeeIsAdministratorPatch
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: protobuf

    message EmployeeDepartmentPatch
    {
        required bool IsAdministrator = 1;
    }

Структура для изменения права сотрудника администрировать организацию.

- *IsAdministrator* - имеет ли право сотрудник администрировать организацию

.. _employee-document-access-level-patch:

EmployeeDocumentAccessLevelPatch
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: protobuf

    message EmployeeDocumentAccessLevelPatch
    {
        required DocumentAccessLevel DocumentAccessLevel = 1;
    }

Структура для изменения уровня доступа сотрудника к документам.

- :doc:`DocumentAccessLevel` - новый уровень доступа к документам

.. _employee-selected-departments-patch:

EmployeeSelectedDepartmentsPatch
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: protobuf

    message EmployeeSelectedDepartmentsPatch
    {
        repeated string SelectedDepartmentIds = 1;
    }
    
Структура для изменения списка подразделений, к которым имеет доступ сотрудник (играет роль только в случае *DocumentAccessLevel = SelectedDepartments*).

- *SelectedDepartmentIds* - новый список подразделений, к которым имеет доступ сотрудник

.. _employee-position-patch:

EmployeePositionPatch
---------------------

.. code-block:: protobuf

    message EmployeePositionPatch
    {
        optional string Position = 1;
    }

Структура для изменения должности сотрудника.

- *Position* - новая должность сотрудника

.. _employee-can-be-invited-to-chat-patch:

EmployeeCanBeInvitedForChatPatch
--------------------------------

.. code-block:: protobuf

    message EmployeeCanBeInvitedForChatPatch
    {
        required bool CanBeInvitedForChat = 1;
    }

Структура для изменения необходимости отображать сотрудника в списке получателей Сообщений в веб-интерфейсе.

- *Position* - нужно ли отображать сотрудника в списке получателей Сообщений в веб-интерфейсе

