---
title: MT メッセージの例を示します |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 629042cc-b941-4c58-b0dd-ede056caf573
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73098c20aeb03e8013f7e20e04c8bb37ce31266e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22208890"
---
# <a name="examples-of-mt-messages"></a>MT メッセージの例
**ソリューション (InfoPath フォーム テンプレート) を異なる MT メッセージを生成するためのコマンドします。**  
  
 次の例では、"SWIFT ベース Types.xsd"、"SWIFT 共通データ Types.xsd","MT102.xsd"、"MT500.xsd"および"MT103.xsd"のスキーマをすべて c:\schemas が必要です。 これにより、"C:\GeneratedForms"フォルダー内の InfoPath フォーム テンプレートのソリューションが生成されます。 ソリューションのフォルダー名は、メッセージを生成する必要がある InfoPath フォームの名前と同じになります。 これらの例では、ユーティリティが"C:\FormGeneratorUtility2008"フォルダーに格納されていることを前提としています。 ユーティリティ用に選択した場所を交換して、以下のコマンド。  
  
-   **MT103 スキーマ用にフォームを生成します。**  
  
     `FormGenerator.exe -b “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas MT103`  
  
-   **MT103、MT102、および MT500 スキーマ用にフォームを生成します。**  
  
     `FormGenerator.exe -b “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas MT103 MT102 MT500`  
  
-   **(ファイル) から MT103 スキーマ用にフォームを生成するには。**  
  
     `FormGenerator.exe -b “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas -f P1forms.txt`