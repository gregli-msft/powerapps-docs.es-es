---
title: 'Control Galería: referencia | Microsoft Docs'
description: Información sobre el control Galería, con propiedades y ejemplos
services: ''
suite: powerapps
documentationcenter: na
author: RickSaling
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/25/2017
ms.author: sharik
ms.openlocfilehash: 9839059cca741e47f5f519a45e7291847c1bc792
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2018
---
# <a name="gallery-control-in-powerapps"></a>Control Galería en PowerApps
Un control que contiene otros controles y muestra un conjunto de datos.

## <a name="description"></a>Descripción
Un control **Galería** puede mostrar varios registros de un origen de datos, y cada registro puede contener varios tipos de datos. Por ejemplo, un control **Galería** puede mostrar varios contactos y cada elemento mostrar a su vez información de contacto que incluye un nombre, una dirección y un número de teléfono para cada contacto. Cada campo de datos aparece en un control independiente dentro del control **Galería** y esos controles se pueden configurar en su plantilla. La plantilla aparece como primer elemento dentro de la galería, en el borde izquierdo de un control **Galería** en orientación horizontal o vertical y en la parte superior de un control **Galería** en orientación vertical. Los cambios realizados en la plantilla se reflejarán en todo el control **Galería**.

Hay disponibles plantillas predefinidas de la galería para mostrar imágenes, texto, así como una galería de elementos de alto variable.

## <a name="key-properties"></a>Propiedades principales
**[Predeterminado](properties-core.md)**: el elemento o registro del origen de datos que se va a seleccionar en la galería al iniciarse la aplicación.

**[Elementos](properties-core.md)**: origen de datos que aparece en un control, como una galería, una lista o un gráfico.

**Seleccionados**: el elemento seleccionado.

## <a name="additional-properties"></a>Propiedades adicionales
**TodosLosElementos**: todos los elementos de una galería, como valores de control adicionales que sean parte de la plantilla de la galería.

**[BorderColor](properties-color-border.md)**: el color de un borde del control.

**[BorderStyle](properties-color-border.md)**: si el borde del control es **Solid**, **Dashed**, **Dotted** o **None**.

**[BorderThickness](properties-color-border.md)**: el grosor de un borde del control.

**[DisplayMode](properties-core.md)**: indica si el control permite entradas de usuario (**Edit**), solo muestra datos (**View**) o si está deshabilitado (**Disabled**).

**[Fill](properties-color-border.md)**: el color de fondo de un control.

**[Height](properties-size-location.md)**: la distancia entre los bordes superior e inferior de un control.

**Layout**: indica si el usuario se desplaza por la galería o ajusta un control deslizante de arriba a abajo (**Vertical**) o de izquierda a derecha (**Horizontal**).

**PasoDeNavegación**: indica lo lejos que se desplaza una galería si su propiedad **Mostrar Navegación** está establecida en **true** y el usuario selecciona una flecha de navegación de cualquier extremo de esa galería.

**MostrarNavegación**: indica si aparece una flecha en cada extremo de una galería para que un usuario puede desplazarse por los elementos de la galería haciendo clic en una flecha o pulsando en ella.

**MostrarBarraDesplazamiento**: indica si aparecerá una barra de desplazamiento cuando el usuario mantenga el cursor sobre una galería.

**Snap**: indica si, cuando un usuario se desplaza por una galería, esta se ajusta automáticamente para que aparezca el siguiente elemento en su totalidad.

**RellenoDePlantilla**: el color de fondo de una galería.

**EspaciadoInternoDePlantilla**: la distancia entre los elementos de una galería.

**TamañoDePlantilla**: el alto de la plantilla en una galería en orientación vertical o el ancho de la plantilla en una galería en orientación horizontal o vertical.

**Transition**: el efecto visual (**Pop**, **Push** o **None**) cuando el usuario mantiene el puntero sobre un elemento de la galería.

**[Visible](properties-core.md)**: indica si un control aparece o está oculto.

**[Width](properties-size-location.md)**: la distancia entre los bordes derecho e izquierdo de un control.

**WrapCount**: número de elementos que se muestran por fila o columna en función del diseño horizontal o vertical.

**[X](properties-size-location.md)**: la distancia entre el borde izquierdo de un control y el borde izquierdo de su contenedor primario (la pantalla si no hay un contenedor primario).

**[Y](properties-size-location.md)**: la distancia entre el borde superior de un control y el borde superior de su contenedor primario (la pantalla si no hay un contenedor primario).

## <a name="related-functions"></a>Funciones relacionadas
[**Filter**( *DataSource*, *Formula* )](../functions/function-filter-lookup.md)

## <a name="examples"></a>Ejemplos
### <a name="show-and-filter-data"></a>Mostrar y filtrar los datos
* [Mostrar texto](control-text-box.md#show-data-in-a-gallery)
* [Mostrar imágenes](control-image.md#show-a-set-of-images-from-a-data-source)
* [Filtrar datos mediante la selección de una opción de la lista](control-drop-down.md#example)
* [Filtrar datos mediante el ajuste de un control deslizante](control-slider.md#example)

### <a name="get-data-from-the-user"></a>Obtener datos del usuario
* [Obtener texto](control-text-input.md#collect-data)
* [Obtener imágenes](control-add-picture.md#add-images-to-an-image-gallery-control)
* [Obtener fotografías](control-camera.md#example)
* [Obtener sonidos](control-microphone.md#example)
* [Obtener dibujos](control-pen-input.md#create-a-set-of-images)
