---
title: Colores accesibles | Microsoft Docs
description: Directrices de contraste de color para PowerApps
author: tahoon
manager: kvivek
ms.service: powerapps
ms.topic: article
ms.custom: canvas
ms.reviewer: anneta
ms.date: 04/23/2018
ms.author: tahoon
ms.openlocfilehash: 289026f18d341381d64423e76effb1abf586557c
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/13/2018
ms.locfileid: "39014820"
---
# <a name="accessible-colors-in-powerapps"></a>Colores accesibles en PowerApps
Los colores utilizados en una aplicación deben ser accesibles para los usuarios daltónicos y con deficiencia visual. Todos los temas de PowerApps son accesibles de forma predeterminada. Si desea modificar los colores utilizados en una aplicación, siga estas instrucciones para asegurarse de que sean accesibles. Hay varias herramientas disponibles en línea que pueden ayudarle a identificar problemas de contraste de color.

## <a name="minimum-contrast-for-text"></a>Contraste mínimo para el texto
* El texto y su fondo deben tener al menos una relación de contraste 4.5:1
* El texto grande debe tener una relación de contraste de al menos 3:1
* El texto deshabilitado no tiene ningún requisito de contraste

En términos prácticos, todos los controles interactivos deben tener el contraste de color adecuado entre:
* **[Color](controls/properties-color-border.md)** y **[Fill](controls/properties-color-border.md)**
* **[PressedColor](controls/properties-color-border.md)** y **[PressedFill](controls/properties-color-border.md)**
* **[HoverColor](controls/properties-color-border.md)** y **[HoverFill](controls/properties-color-border.md)**

## <a name="minimum-contrast-for-non-text"></a>Contraste mínimo para no texto

> [!NOTE]
> En el estándar [WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-contrast.html), los requisitos de contraste solo se aplican al texto. Para una mayor accesibilidad, tenga en cuenta las próximas [orientaciones de contraste de WCAG 2.1](https://www.w3.org/TR/WCAG21/#non-text-contrast) para los componentes de interfaz de usuario esenciales, como los botones de los iconos. Se recomienda una proporción mínima de 3:1 para estos componentes. Las directrices descritas en esta sección son **opcionales** para el cumplimiento de WCAG 2.0.

### <a name="user-interface-components"></a>Componentes de la interfaz de usuario
Todos los controles interactivos deben tener el contraste de color adecuado entre:
* **[FocusedBorderColor](controls/properties-color-border.md)** y el color situado fuera del control

Es necesario realizar comprobaciones de contraste de color adicionales para los controles donde el área completa es interactiva o informativa. Por ejemplo, un **[Botón](controls/control-button.md)**  o un **[Icono](controls/control-shapes-icons.md)** que se utiliza como botón. Esto garantiza que los límites del control están claros y que los usuarios sabe dónde pueden hacer clic o pulsar.

Si hay un borde para tales controles, debería haber contraste de color adecuado entre:
* **[BorderColor](controls/properties-color-border.md)** y el color situado fuera del control
* **[PressedBorderColor](controls/properties-color-border.md)** y el color situado fuera del control
* **[HoverBorderColor](controls/properties-color-border.md)** y el color situado fuera del control

Si no hay ningún borde, debería haber un contraste de color adecuado entre:
* **[Fill](controls/properties-color-border.md)** y el color situado fuera del control
* **[PressedFill](controls/properties-color-border.md)** y el color situado fuera del control
* **[HoverFill](controls/properties-color-border.md)** y el color situado fuera del control

### <a name="graphical-objects"></a>Objetos gráficos
Si una imagen transmite información importante, considere la posibilidad de comprobar los problemas de contraste. Esto se aplica a los controles en los que se puede mostrar una imagen: **[Audio](controls/control-audio-video.md)**, **[Imagen](controls/control-image.md)**, **[Micrófono ](controls/control-microphone.md)** y **[Vídeo](controls/control-audio-video.md)**.

En el caso del contenido de vídeo, considere la comprobación de los problemas de contraste. De forma alternativa o adicional, proporcione [subtítulos](controls/control-audio-video.md) que describan el vídeo.

## <a name="provide-other-visual-cues"></a>Provisión de otras indicaciones visuales
Asegúrese de que la aplicación no transmite información con solo color. Por ejemplo, los usuarios que no puedan distinguir el color rojo no serán capaces de diferenciar un mensaje de error rojo de un mensaje de éxito verde.

Indicaciones adicionales, como un **[icono](controls/control-shapes-icons.md)** o estilos de texto, como **[cursiva](controls/properties-text.md)** y **[subrayado](controls/properties-text.md)**, pueden ayudar a transmitir el significado.

## <a name="next-steps"></a>Pasos siguientes
Obtenga información sobre las [propiedades de accesibilidad](controls/properties-accessibility.md) en los controles de PowerApps e intente [usar el Comprobador de accesibilidad](accessibility-checker.md).
