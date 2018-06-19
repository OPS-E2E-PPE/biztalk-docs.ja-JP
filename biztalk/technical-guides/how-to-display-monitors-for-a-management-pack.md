---
title: 管理パックのモニタを表示する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7c4d2b3-9c01-40f5-b983-bf29a3a5cacc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b3954052159633894e59b4251ee20b1ea0844a6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298010"
---
# <a name="how-to-display-monitors-for-a-management-pack"></a>管理パックのモニタを表示する方法
管理パックのモニタおよびコマンド シェルを使用して上書きの出力の一覧を表示するには、次の手順を使用します。  
  
### <a name="to-display-monitors-for-a-management-pack"></a>管理パックのモニタを表示するには  
  
1.  管理サーバーで、をクリックして**プログラム**、クリックして**System Center です。**  
  
2.  をクリックして**コマンド シェル**です。  
  
3.  コマンド シェルでは、次のコマンドを入力します。   
    `get-scommanagementpack –DisplayName “DisplayName” | get-scommonitor | export.csv filename`  
  
4.  .Csv ファイルが作成されます。 この .csv ファイルは、Microsoft Office Excel で開くことができます。  
  
    > [!NOTE]  
    >  Excel では、.csv ファイルをテキスト ファイルに指定する必要する必要があります。  
  
 たとえば、次のコマンドは、コア管理パックのいずれかに関連付けられているモニターのデータを取得します。   
`get-scommanagementpack -DisplayName "BizTalk Server Monitoring" | Get-ScomMonitor | export-csv "c:\monitors.csv"`