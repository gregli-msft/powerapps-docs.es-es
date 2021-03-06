---
title: Instalar y configurar el ejemplo de informe de gastos en aplicaciones de lienzo | Microsoft Docs
description: Instrucciones paso a paso para instalar y configurar en PowerApps el ejemplo de informe de gastos en aplicaciones de lienzo.
author: caburk
manager: kvivek
ms.service: powerapps
ms.topic: sample
ms.custom: canvas
ms.reviewer: anneta
ms.date: 04/08/2018
ms.author: caburk
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 43d1dc6ef2d264dd60b6a9f3de0f5c0fed633283
ms.sourcegitcommit: d3d665500b9c49c14657d044b084bdd64c52c5a3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44124484"
---
# <a name="install-and-configure-the-expense-report-sample-for-canvas-apps-in-powerapps"></a>Instalar y configurar el ejemplo de informe de gastos en aplicaciones de lienzo en PowerApps

Instrucciones paso a paso para instalar y configurar el ejemplo de informe de gastos. También puede obtener una vista previa de la aplicación de ejemplo [aquí](https://aka.ms/previewmyexpenses).

Tiempo estimado para completar estos pasos: **10-15 minutos**

> [!TIP]
> Vea [este vídeo](https://youtu.be/kJXZPILfbwU) para una demostración sobre cómo usar la aplicación de ejemplo de informe de gastos. 

Mantenga un seguimiento de los informes de gastos desde que se envían hasta que se aprueban. Registre las partidas como una acumulación de gastos individuales y envíelos para su aprobación cuando estén listos. Esta aplicación requiere un mínimo de configuración para personalizarla.

![Pantalla inicial del informe de gastos de PowerApps](./media/expense-report-install/expense-report-powerapp.png)

> [!TIP]
> Vea [este](https://youtu.be/h6E9cdrOvMU) vídeo para aprender a usar el ejemplo de informe de gastos de PowerApps.

## <a name="prerequisites"></a>Requisitos previos

- [Inicie sesión](../signup-for-powerapps.md) en PowerApps.

## <a name="create-the-expenses-sharepoint-list"></a>Crear la lista de SharePoint de gastos

En esta lista se almacenan los informes de gastos.

1. Abra un explorador web y vaya a https://portal.office.com.
2. Inicie sesión con una cuenta que tenga permiso para crear listas.
3. Desplácese a la colección de sitios donde quiera alojar la lista de gastos.
4. Haga clic en el **icono de engranaje** situado en la parte superior derecha de la página web.
5. Haga clic en **Agregar una aplicación**.
6. En el cuadro de texto **Buscar una aplicación**, escriba **Personalizado**.
7. Haga clic en el **icono de búsqueda**.
8. Haga clic en la aplicación **Lista personalizada**.
9. En el cuadro de texto **Nombre**, escriba **Gastos**.

    > [!IMPORTANT]
    > Si elige otro nombre para la lista, asegúrese de anotarlo ya que tendrá que sustituirlo en todos los casos por Gastos durante el proceso de instalación y configuración.

10. Haga clic en **Crear**.

### <a name="create-cost-center-column"></a>Crear una columna Cost Center

1. Haga clic en la lista **Gastos**.
2. Haga clic en el **icono de engranaje** situado en la parte superior derecha de la página web.
3. Haga clic en **Configuración de la lista**.
4. Haga clic en **Crear columna**.
5. En el cuadro de texto **Nombre de columna**, escriba **Cost Center**.
6. En la lista de botones de radio **El tipo de información de esta columna es**, seleccione **Elección**.
7. En el cuadro de texto **Escriba cada opción en una línea distinta**, especifique los valores siguientes, cada uno en una línea diferente: 
    - Microsoft
    - Contoso
8. En el cuadro de texto **Valor predeterminado**, escriba **Microsoft**.
9. Haga clic en **Aceptar**.

### <a name="create-comments-column"></a>Crear una columna de comentarios

1. Haga clic en **Crear columna**.
2. En el cuadro de texto **Nombre de columna**, escriba **Comentarios**.
3. En la lista de botones de radio **El tipo de información de esta columna es**, seleccione **Varias líneas de texto**.
4. Haga clic en **Aceptar**.

### <a name="create-status-column"></a>Crear una columna de estado

1. Haga clic en la lista **Gastos**.
2. Haga clic en el **icono de engranaje** situado en la parte superior derecha de la página web.
3. Haga clic en **Configuración de la lista**.
4. Haga clic en **Crear columna**.
5. En el cuadro de texto **Nombre de columna**, escriba **Estado**.
6. En la lista de botones de radio **El tipo de información de esta columna es**, seleccione **Elección**.
7. En el cuadro de texto **Escriba cada opción en una línea distinta**, especifique los valores siguientes, cada uno en una línea diferente: 
    - Abierto
    - Pendiente
    - Approved
8. En el cuadro de texto **Valor predeterminado**, escriba **Abierto**.
9. Haga clic en **Aceptar**.

### <a name="create-approvername-column"></a>Crear una columna ApproverName

1. Haga clic en **Crear columna**.
2. En el cuadro de texto **Nombre de columna**, escriba **ApproverName**.
3. En la lista de botones de radio **El tipo de información de esta columna es**, seleccione **Persona o grupo**.
4. En la lista de botones de radio **Esta columna debe contener información**, seleccione **Sí**.
5. Haga clic en **Aceptar**.

### <a name="create-datesubmitted-column"></a>Crear una columna DateSubmitted

1. Haga clic en **Crear columna**.
2. En el cuadro de texto **Nombre de columna**, escriba **DateSubmitted**.
3. En la lista de botones de radio **El tipo de información de esta columna es**, seleccione **Fecha y hora**.
4. En la lista de botones de radio **Esta columna debe contener información**, seleccione **Sí**.
5. Haga clic en **Aceptar**.

### <a name="create-startdate-column"></a>Crear una columna StartDate

1. Haga clic en **Crear columna**.
2. En el cuadro de texto **Nombre de columna**, escriba **StartDate**.
3. En la lista de botones de radio **El tipo de información de esta columna es**, seleccione **Fecha y hora**.
4. En la lista de botones de radio **Esta columna debe contener información**, seleccione **Sí**.
5. Haga clic en **Aceptar**.

### <a name="create-enddate-column"></a>Crear una columna EndDate

1. Haga clic en **Crear columna**.
2. En el cuadro de texto **Nombre de columna**, escriba **EndDate**.
3. En la lista de botones de radio **El tipo de información de esta columna es**, seleccione **Fecha y hora**.
4. En la lista de botones de radio **Esta columna debe contener información**, seleccione **Sí**.
5. Haga clic en **Aceptar**.

## <a name="create-the-line-items-sharepoint-list"></a>Crear la lista de SharePoint de elementos de línea

En esta lista se almacenan los elementos de línea asociados a los informes de gastos.

1. Desplácese a la misma colección de sitios donde creó la lista de gastos.
2. Haga clic en el **icono de engranaje** situado en la parte superior derecha de la página web.
3. Haga clic en **Agregar una aplicación**.
4. En el cuadro de texto **Buscar una aplicación**, escriba **Personalizado**.
5. Haga clic en el **icono de búsqueda**.
6. Haga clic en la aplicación **Lista personalizada**.
7. En el cuadro de texto **Nombre**, escriba **LineItems**.

    > [!IMPORTANT] 
    > Si elige otro nombre para la lista, asegúrese de anotarlo ya que tendrá que sustituirlo en todos los casos por Gastos durante el proceso de instalación y configuración.

8. Haga clic en **Crear**.
 
### <a name="create-category-column"></a>Crear una columna de categoría

1. Haga clic en la lista **LineItems**.
2. Haga clic en el **icono de engranaje** situado en la parte superior derecha de la página web.
3. Haga clic en **Configuración de la lista**.
4. Haga clic en **Crear columna**.
5. En el cuadro de texto **Nombre de columna**, escriba **Categoría**.
6. En la lista de botones de radio **El tipo de información de esta columna es**, seleccione **Elección**.
7. En el cuadro de texto **Escriba cada opción en una línea distinta**, especifique los valores siguientes, cada uno en una línea diferente: 
    - Comida y bebida
    - Transporte
    - Necesidades del negocio
8. En el cuadro de texto **Valor predeterminado**, escriba **Comida y bebida**.
9. Haga clic en **Aceptar**.

### <a name="create-cost-column"></a>Crear una columna de costo

1. Haga clic en **Crear columna**.
2. En el cuadro de texto **Nombre de columna**, escriba **Costo**.
3. En la lista de botones de radio **El tipo de información de esta columna es**, seleccione **Número (1, 10, 100)**.
4. En la lista de botones de radio **Esta columna debe contener información**, seleccione **Sí**.
5. Haga clic en **Aceptar**.

### <a name="create-date-column"></a>Crear una columna de fecha

1. Haga clic en **Crear columna**.
2. En el cuadro de texto **Nombre de columna**, escriba **Fecha**.
3. En la lista de botones de radio **El tipo de información de esta columna es**, seleccione **Fecha y hora**.
4. En la lista de botones de radio **Esta columna debe contener información**, seleccione **Sí**.
5. Haga clic en **Aceptar**.

### <a name="create-description-column"></a>Crear una columna de descripción

1. Haga clic en **Crear columna**.
2. En el cuadro de texto **Nombre de columna**, escriba **Descripción**.
3. En la lista de botones de radio **El tipo de información de esta columna es**, seleccione **Varias líneas de texto**.
4. En la lista de botones de radio **Esta columna debe contener información**, seleccione **Sí**.
5. En la lista de botones de radio **Especificar el tipo de texto que se permite**, seleccione **Texto sin formato**.
6. Haga clic en **Aceptar**.

### <a name="create-reportid-column"></a>Crear una columna ReportID

1. Haga clic en **Crear columna**.
2. En el cuadro de texto **Nombre de columna**, escriba **ReportID**.
3. En la lista de botones de radio **El tipo de información de esta columna es**, seleccione **Búsqueda (información ya disponible en este sitio)**.
4. En la lista de botones de radio **Esta columna debe contener información**, seleccione **Sí**.
5. En la lista desplegable **Obtener información de**, seleccione la lista **Gastos** que ha creado.
6. En la lista desplegable **En esta columna**, seleccione **Id**.
7. Haga clic en **Aceptar**.

### <a name="edit-title-column"></a>Editar columna de título

1. Haga clic en el vínculo de la columna **Título**.
2. En la lista de botones de radio **Esta columna debe contener información**, seleccione **No**.
3. Haga clic en **Aceptar**.

## <a name="download-the-expense-report-powerapp"></a>Descargar la aplicación de PowerApps de informe de gastos

1.  En un explorador web, desplácese hasta el siguiente vínculo:

    [http://pappsfeprodwestuscontent.blob.core.windows.net/sampleapps/myexpenses/docs/MyExpenses(SP_List).zip](http://pappsfeprodwestuscontent.blob.core.windows.net/sampleapps/myexpenses/docs/MyExpenses(SP_List).zip).

2.  Descargue el paquete de ejemplo de PowerApps de informe de gastos y guárdelo en su equipo.

## <a name="create-connections"></a>Crear conexiones

1.  En un explorador web, vaya a [web.powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).
2.  Inicie sesión con las mismas credenciales que utilizó para suscribirse.
3.  En el menú de la izquierda, seleccione **Conexiones**.

### <a name="create-approvals-connection"></a>Crear una conexión de aprobaciones

1.  Haga clic en **+ Nueva conexión**.
2.  En el cuadro de búsqueda **Buscar**, escriba **Aprobaciones**.
3.  Seleccione **Aprobaciones** en la lista.
4.  Haga clic en **Crear**.
    
### <a name="create-office-365-outlook-connection"></a>Crear una conexión de Outlook de Office 365

1.  Haga clic en **+ Nueva conexión**.
2.  En el cuadro de búsqueda **Buscar**, escriba **Office 365 Outlook**.
3.  Seleccione **Office 365 Outlook** en la lista.
4.  Haga clic en **Crear**.
5.  En la ventana emergente, seleccione la cuenta con la que inició sesión.

### <a name="create-sharepoint-connection"></a>Crear una conexión de SharePoint

1.  Haga clic en **+ Nueva conexión**.
2.  En el cuadro de texto **Buscar**, escriba **SharePoint**.
3.  Seleccione **SharePoint** en la lista.
4.  Haga clic en **Crear**.
5.  En la ventana emergente, seleccione la cuenta con la que inició sesión.

## <a name="import-the-expense-report-powerapp"></a>Importar la aplicación de PowerApps de informe de gastos

1. En un explorador web, vaya a https://web.powerapps.com.
2. Inicie sesión con las mismas credenciales que utilizó para suscribirse.
3. En el menú de la izquierda, seleccione **Aplicaciones**. 
4. Haga clic en **Importar paquete (versión preliminar)**.
    
   ![Pantalla Importar paquete](./media/expense-report-install/import-package.png)

5. Haga clic en el botón **Cargar** y seleccione el paquete de PowerApps que descargó en pasos anteriores.
6. Para los tipos de recurso **Aplicación** y **Flujo**, establezca **IMPORTAR CONFIGURACIÓN** en **Crear como nueva**.
7. Para las conexiones **SharePoint** y **Outlook**, establezca **IMPORTAR CONFIGURACIÓN** en **Seleccionar durante la importación**.
    
   ![Pantalla Importar configuración](./media/expense-report-install/import-settings.png)

8. Haga clic en el **icono rojo** correspondiente a la **conexión de SharePoint**.
9. En la lista de conexiones, haga clic en el elemento que tenga su nombre de usuario.

   ![Pantalla Importar configuración](./media/expense-report-install/import-settings-sharepoint.png)

10. Haga clic en **Guardar**.
11. Haga clic en el **icono rojo** correspondiente a la **conexión de aprobación**.
12. En la lista de conexiones, haga clic en el elemento que tenga su nombre de usuario.

    ![Pantalla Importar configuración](./media/expense-report-install/import-settings-approvals.png)

13. Haga clic en **Guardar**.
14. Haga clic en el **icono rojo** correspondiente a la **conexión de Office 365 Outlook**.
15. En la lista de conexiones, haga clic en el elemento que tenga su nombre de usuario.

    ![Pantalla Importar configuración](./media/expense-report-install/import-settings-office365outlook.png)

16. Haga clic en **Guardar**.

    > [!TIP] 
    > Cuando haya terminado, tendrá un aspecto similar al siguiente:

    ![Pantalla Importar configuración](./media/expense-report-install/import-settings-done.png)

17. Haga clic en **Importar** y espere hasta que finalice el proceso.

    ![Pantalla Importar configuración](./media/expense-report-install/import-done.png)

## <a name="configure-the-powerapp-to-use-the-sharepoint-lists"></a>Configurar la aplicación de PowerApps para usar las listas de SharePoint

1. En el explorador web, haga clic en **Aplicaciones**.
2. Haga clic en los **puntos suspensivos** junto a la aplicación Informe de gastos de PowerApps.
3. Haga clic en **Editar en la Web**.
4. Haga clic en **Permitir**.

### <a name="delete-connections"></a>Eliminar conexiones
1. Haga clic en **Ver**.
2. Haga clic en **Orígenes de datos**.
3. En el panel **Datos**, haga clic en los **puntos suspensivos** junto a **Gastos**.
4. Haga clic en **Quitar**.
5. En el panel **Datos**, haga clic en los **puntos suspensivos** junto a **LineItems**.
6. Haga clic en **Quitar**.

### <a name="expenses-list"></a>Lista de gastos

1. Haga clic en **Ver**.
2. Haga clic en **Orígenes de datos**.
3. En el panel **Datos**, haga clic en **+ Agregar origen de datos**.
4. Haga clic en **+ Nueva conexión**.
5. Seleccione **SharePoint**.
6. Haga clic en **Crear**.
7. En la lista **Sitios recientes**, seleccione el sitio de SharePoint en el que creó la lista de gastos.

    > [!TIP] 
    > Si el sitio no aparece en la lista, escriba en el cuadro de texto la dirección URL que lleva al sitio de SharePoint y haga clic en **Ir**.

8. En el cuadro de texto **Buscar** de la parte superior de la lista, escriba **Gastos**.
9. Active la casilla junto a la lista **Gastos**.
10. Haga clic en **Conectar**.

### <a name="lineitems-list"></a>Lista de LineItems

1. Haga clic en **Ver**.
2. Haga clic en **Orígenes de datos**.
3. En el panel **Datos**, haga clic en **+ Agregar origen de datos**.
4. Haga clic en **+ Nueva conexión**.
5. Seleccione **SharePoint**.
6. Haga clic en **Crear**.
7. En la lista **Sitios recientes**, seleccione el sitio de SharePoint en el que creó la lista de LineItems.

    > [!TIP] 
    > Si el sitio no aparece en la lista, escriba en el cuadro de texto la dirección URL que lleva al sitio de SharePoint y haga clic en **Ir**.

8. En el cuadro de texto **Buscar** de la parte superior de la lista, escriba **LineItems**.
9. Active la casilla junto a la lista **LineItems**.
10. Haga clic en **Conectar**.
11. Haga clic en **Archivo**.
12. Haga clic en **Guardar**.
13. Haga clic en **Publicar**.
14. Haga clic en **Publicar esta versión**.

## <a name="modify-the-flow"></a>Modificar el flujo

1.  En el menú de la izquierda, seleccione **Flujos**.
2.  Si es necesario, inicie sesión con las mismas credenciales que utilizó para suscribirse.
3.  Seleccione **Mis flujos** en el menú superior.
4.  Junto al flujo **ApproveExpense**, haga clic en el **icono de lápiz**.
 
    ![Pantalla Editar flujo](./media/expense-report-install/edit-flow.png)

5.  Expanda la acción **Obtener elementos**. 
6.  Modifique los campos **Dirección del sitio** y **Nombre de lista** para que coincidan con la lista Gastos de SharePoint que ha creado.
    
    ![Pantalla Editar flujo](./media/expense-report-install/edit-flow-getitems.png)

    > [!TIP] 
    > No es necesario que se escriban manualmente, se pueden elegir en las listas desplegables.

7.  Expanda la **Condición**.
8.  Expanda la sección **En caso positivo**.
9.  Expanda la acción **Cambiar estado de elemento a Aprobado**.
10. Modifique los campos **Dirección del sitio** y **Nombre de lista** para que coincidan con la lista Gastos de SharePoint que ha creado.

    ![Pantalla Editar flujo](./media/expense-report-install/edit-flow-condition-ifyes.png) 

    > [!TIP] 
    > No es necesario que se escriban manualmente, se pueden elegir en las listas desplegables.

11. Expanda la sección **En caso negativo**.
12. Expanda la acción **Cambiar estado de elemento a Abierto**.
13. Modifique los campos **Dirección del sitio** y **Nombre de lista** para que coincidan con la lista Gastos de SharePoint que ha creado. 

    ![Pantalla Editar flujo](./media/expense-report-install/edit-flow-condition-ifno.png)

    > [!TIP] 
    > No es necesario que se escriban manualmente, se pueden elegir en las listas desplegables.

14. Haga clic en **Actualizar flujo**.

## <a name="play-the-powerapp"></a>Reproducir la aplicación de PowerApps

1. En el explorador web, haga clic en **Aplicaciones**.
2. Haga clic en los **puntos suspensivos** junto a la aplicación Informe de gastos de PowerApps.
3. Haga clic en **Abrir**.


## <a name="next-steps"></a>Pasos siguientes
- [Personalizar un formulario de lista de SharePoint](https://docs.microsoft.com/powerapps/maker/canvas-apps/customize-list-form)
- [Agregar y configurar un control](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-configure-controls)
- [Editar y administrar permisos para una lista de SharePoint o una biblioteca](https://support.office.com/en-us/article/edit-and-manage-permissions-for-a-sharepoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782)



