---
title: MX メッセージの例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b592034f-2dd3-40e4-8f0b-eb6d65c38fff
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26d86af52d8f93986d7028977166df8cfb28045c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377893"
---
# <a name="examples-of-mx-messages"></a>MX メッセージの例
異なる MX メッセージのソリューション (InfoPath フォーム テンプレート) を生成するコマンドライン  
  
 次の例では、"pacs.004.001.01"と"pain.002.001.01"スキーマは c:\schemas すべてであることが必要です。 これにより、"C:\GeneratedForms"フォルダー内の InfoPath フォーム テンプレートのソリューションが生成されます。 ソリューションのフォルダー名は、メッセージを生成する必要がある InfoPath フォームの名前と同じになります。 これらの例では、ユーティリティが"C:\Program files \microsoft BizTalk Accelerator 用 SWIFT\SDK\FormGeneratorUtility"フォルダーに配置されていることを前提としています。 ユーティリティでの選択した場所を置き換える、以下のコマンド。  
  
-   **Pacs.004.001.01 スキーマ用のフォームを生成するには。**  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\MXTemplates” " C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas pacs.004.001.01`  
  
-   **Pacs.004.001.01 と pain.002.001.01 スキーマ用のフォームを生成するには。**  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\MXTemplates” “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas pacs.004.001.01 pain.002.001.01`