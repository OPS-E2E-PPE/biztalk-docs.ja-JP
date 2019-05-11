---
title: MT メッセージの例 |Microsoft Docs
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
ms.openlocfilehash: d6406a5d1e11ddeefd0aeb86c0d350acf5892361
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378033"
---
# <a name="examples-of-mt-messages"></a>MT メッセージの例
**異なる MT メッセージのソリューション (InfoPath フォーム テンプレート) を生成するためのコマンドします。**  
  
 次の例では、"SWIFT ベース Types.xsd"、"SWIFT 共通データ Types.xsd","MT102.xsd"、"MT500.xsd"および"MT103.xsd"スキーマは c:\schemas すべてであることが必要です。 これにより、"C:\GeneratedForms"フォルダー内の InfoPath フォーム テンプレートのソリューションが生成されます。 ソリューションのフォルダー名は、メッセージを生成する必要がある InfoPath フォームの名前と同じになります。 これらの例では、ユーティリティが"C:\FormGeneratorUtility2008"フォルダーに配置されていることを前提としています。 ユーティリティでの選択した場所を置き換える、以下のコマンド。  
  
-   **MT103 スキーマ用のフォームを生成するには。**  
  
     `FormGenerator.exe -b “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas MT103`  
  
-   **MT103、MT102、および MT500 スキーマ用のフォームを生成するには。**  
  
     `FormGenerator.exe -b “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas MT103 MT102 MT500`  
  
-   **(ファイル) から MT103 スキーマ用のフォームを生成するには。**  
  
     `FormGenerator.exe -b “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas -f P1forms.txt`