---
title: "管理パックの上書きを表示する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8261a514-b4c4-4e6b-ac35-40a3e3e090e0
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a28c4ab2ef8f82fdd770203816239ad78e74418e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-display-overrides-for-a-management-pack"></a>管理パックの上書きを表示する方法
管理パックの上書きを表示するには、次の手順を使用します。  
  
### <a name="to-display-overrides-for-a-management-pack"></a>管理パックの上書きを表示するには  
  
1.  管理サーバーで、をクリックして**プログラム**、クリックして**System Center**です。  
  
2.  をクリックして**コマンド シェル**です。  
  
3.  コマンド シェルでは、次のコマンドを入力します。   
    `$mp = get-scommanagementpack -DisplayName "Operations Manager Internal Library"`   
    `$mp.GetOverrides()`  
  
4.  .Csv ファイルが作成されます。 この .csv ファイルは、Office Excel で開くことができます。  
  
    > [!NOTE]  
    >  Office Excel では、.csv ファイルは、テキスト ファイルを指定する必要する必要があります。  
  
 たとえば、次のコマンドは、コア管理パックのいずれかの上書きを表示します。   
`$mp = get-scommanagementpack -DisplayName "Contoso.BizTalk.Overrides.mp"`  
`$mp.GetOverrides()`