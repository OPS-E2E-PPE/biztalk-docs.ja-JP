---
title: 管理パックの上書きを表示する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8261a514-b4c4-4e6b-ac35-40a3e3e090e0
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7b3757781f7567a10db56fceaa6b429309476e1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253422"
---
# <a name="how-to-display-overrides-for-a-management-pack"></a>管理パックの上書きを表示する方法
管理パック用の上書きを表示するには、次の手順を使用します。  
  
### <a name="to-display-overrides-for-a-management-pack"></a>上書き管理パックを表示するには  
  
1. 管理サーバーで次のようにクリックします。**プログラム**、 をクリックし、 **System Center**します。  
  
2. クリックして**コマンド シェル**します。  
  
3. コマンド シェルでは、次のコマンドを入力します。   
   `$mp = get-scommanagementpack -DisplayName "Operations Manager Internal Library"`   
   `$mp.GetOverrides()`  
  
4. .Csv ファイルが作成されます。 .Csv ファイルは、Office Excel で開くことができます。  
  
   > [!NOTE]  
   >  Office Excel で .csv ファイルをテキスト ファイルに指定する必要する必要があります。  
  
   たとえば、次のコマンドは、コア管理パックのいずれかの上書きを表示します。   
   `$mp = get-scommanagementpack -DisplayName "Contoso.BizTalk.Overrides.mp"`  
   `$mp.GetOverrides()`