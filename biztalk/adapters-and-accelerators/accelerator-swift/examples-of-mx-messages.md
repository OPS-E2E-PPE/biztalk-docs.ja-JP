---
title: "MX メッセージの例を示します |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b592034f-2dd3-40e4-8f0b-eb6d65c38fff
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f5280f8ec2ce16344562907a95c1b0afa8c6627
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="examples-of-mx-messages"></a>MX メッセージの例
ソリューション (InfoPath フォーム テンプレート) を異なる MX メッセージを生成するコマンドライン  
  
 次の例では、"pacs.004.001.01"および"pain.002.001.01"のスキーマをすべて c:\schemas が必要です。 これにより、"C:\GeneratedForms"フォルダー内の InfoPath フォーム テンプレートのソリューションが生成されます。 ソリューションのフォルダー名は、メッセージを生成する必要がある InfoPath フォームの名前と同じになります。 これらの例では、ユーティリティが"C:\Program files \microsoft BizTalk Accelerator 用 SWIFT\SDK\FormGeneratorUtility"フォルダーに格納されていることを前提としています。 ユーティリティ用に選択した場所を交換して、以下のコマンド。  
  
-   **Pacs.004.001.01 スキーマ用にフォームを生成します。**  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\MXTemplates” " C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas pacs.004.001.01`  
  
-   **Pacs.004.001.01 と pain.002.001.01 スキーマ用にフォームを生成するには。**  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\MXTemplates” “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas pacs.004.001.01 pain.002.001.01`