---
title: 'Control Micrófono: referencia | Microsoft Docs'
description: Información sobre el control Micrófono, con propiedades y ejemplos
services: ''
suite: powerapps
documentationcenter: na
author: fikaradz
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: 3ffede0018a371b3c3a4cf4a3a1f9fc8115140de
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2018
---
# <a name="microphone-control-in-powerapps"></a>Control Micrófono en PowerApps
Un control con el que el usuario puede grabar sonidos.

## <a name="description"></a>Descripción
Si agrega este control, el usuario puede actualizar un origen de datos con uno o más sonidos desde donde se esté ejecutando la aplicación.

## <a name="key-properties"></a>Propiedades principales
**Micrófono**: en un dispositivo que tenga más de un micrófono, el identificador numérico del micrófono que usa la aplicación.

**AlDetener**: indica cómo la aplicación responde cuando el usuario detiene la grabación con un control de micrófono.

## <a name="additional-properties"></a>Propiedades adicionales
**[BorderColor](properties-color-border.md)**: el color de un borde del control.

**[BorderStyle](properties-color-border.md)**: si el borde del control es **Solid**, **Dashed**, **Dotted** o **None**.

**[BorderThickness](properties-color-border.md)**: el grosor de un borde del control.

**[Color](properties-color-border.md)**: el color del texto en un control.

**[DisplayMode](properties-core.md)**: indica si el control permite entradas de usuario (**Edit**), solo muestra datos (**View**) o si está deshabilitado (**Disabled**).

**[DisabledBorderColor](properties-color-border.md)**: el color de un borde del control si la propiedad **[DisplayMode](properties-core.md)** del control está establecida en **Disabled**.

**[DisabledColor](properties-color-border.md)**: el color del texto en un control si su propiedad **[DisplayMode](properties-core.md)** está establecida en **Disabled**.

**[DisabledFill](properties-color-border.md)**: el color de fondo de un control si su propiedad **[DisplayMode](properties-core.md)** está establecida en **Disabled**.

**[Fill](properties-color-border.md)**: el color de fondo de un control.

**[Height](properties-size-location.md)**: la distancia entre los bordes superior e inferior de un control.

**[HoverBorderColor](properties-color-border.md)**: el color de un borde del control cuando el usuario mantiene el puntero del mouse sobre ese control.

**[HoverColor](properties-color-border.md)**: el color del texto de un control cuando el usuario mantiene el puntero del mouse sobre él.

**[HoverFill](properties-color-border.md)**: el color de fondo de un control cuando el usuario mantiene el puntero del mouse sobre él.

**[Imagen](properties-visual.md)**: el nombre de la imagen que aparece en un control de imagen, audio o micrófono.

**[PosiciónDeLaImagen](properties-visual.md)**: posición (**Rellenar**, **Ajustar**, **Estirar**, **Icono** o **Centrar**) de una imagen en una pantalla o un control, si no tiene el mismo tamaño que la imagen.

**[OnSelect](properties-core.md)**: indica cómo responde la aplicación cuando el usuario toca o hace clic en un control.

**AlIniciar**: indica cómo la aplicación responde cuando el usuario comienza a grabar con un control de micrófono.

**[PressedBorderColor](properties-color-border.md)**: el color de un borde del control cuando el usuario toca o hace clic en ese control.

**[PressedColor](properties-color-border.md)**: el color de texto de un control cuando el usuario toca o hace clic en ese control.

**[PressedFill](properties-color-border.md)**: el color de fondo de un control cuando el usuario toca o hace clic en ese control.

**[Reset](properties-core.md)**: indica si un control vuelve a su valor predeterminado.

**[Información sobre herramientas](properties-core.md)**: texto explicativo que aparece cuando el usuario mantiene el puntero sobre un control.

**[Visible](properties-core.md)**: indica si un control aparece o está oculto.

**[Width](properties-size-location.md)**: la distancia entre los bordes derecho e izquierdo de un control.

**[X](properties-size-location.md)**: la distancia entre el borde izquierdo de un control y el borde izquierdo de su contenedor primario (la pantalla si no hay un contenedor primario).

**[Y](properties-size-location.md)**: la distancia entre el borde superior de un control y el borde superior de su contenedor primario (la pantalla si no hay un contenedor primario).

## <a name="related-functions"></a>Funciones relacionadas
[**Patch**( *DataSource*, *BaseRecord*, *ChangeRecord* )](../functions/function-patch.md)

## <a name="example"></a>Ejemplo
### <a name="add-sounds-to-a-custom-gallery-control"></a>Agregue sonidos a un control Galería personalizada
1. Agregue un **Micrófono**, asígnele el nombre **MyMic**y establezca su propiedad **AlDetener** en esta fórmula:<br>
   **Collect(MySounds, MyMic.Audio)**
   
    ¿No sabe cómo [agregar, nombrar y configurar un control](../add-configure-controls.md)?
   
    ¿Desea más información sobre la función **[Recopilar](../functions/function-clear-collect-clearcollect.md)** u [otras funciones](../formula-reference.md)?
2. Agregue un control **Galería personalizada** muévalo debajo de **MyMic** establezca la propiedad **[Elementos](properties-core.md)** para el control **Galería personalizada** en **MySounds**.
3. En la plantilla para el control **Galería personalizada** de control, agregue un control **[Audio](control-audio-video.md)** y establezca su propiedad **Multimedia** en **ThisItem.Url**.
4. Presione F5, pulse o haga clic en **MyMic** para iniciar la grabación y luego pulse o haga clic en nuevo para detener la grabación.
5. En el control **Galería personalizada**, pulse o haga clic en el botón de reproducción en el control  **[Audio](control-audio-video.md)**  para reproducir la grabación.
6. Agregue tantas grabaciones como desee y, a continuación, presione Esc para volver al área de trabajo predeterminada.
7. (opcional) En la plantilla para el control **Galería personalizada**, agregue un control **[Botón](control-button.md)**, establezca su propiedad **[AlSeleccionar](properties-core.md)** en **Quitar (MySounds, EsteElemento)**, presione F5 y, a continuación, quite una grabación haciendo clic o pulsando el correspondiente control **Botón**.

Use la función **[SaveData](../functions/function-savedata-loaddata.md)** para guardar las grabaciones localmente o la función **[Patch](../functions/function-patch.md)** para actualizar el origen de datos.
