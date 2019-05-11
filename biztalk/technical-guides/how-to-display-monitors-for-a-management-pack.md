---
title: 管理パックのモニタを表示する方法 |Microsoft Docs
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
ms.openlocfilehash: 0d98cca640b7fa818ad49d3b9c95c3e3bdcbf5c9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253480"
---
# <a name="how-to-display-monitors-for-a-management-pack"></a>管理パックのモニタを表示する方法
管理パックのモニタおよび上書きコマンド シェルを使用して出力の一覧を表示するには、次の手順を使用します。  
  
### <a name="to-display-monitors-for-a-management-pack"></a>管理パックのモニタを表示するには  
  
1. 管理サーバーで次のようにクリックします。**プログラム**、 をクリックし、 **System Center。**  
  
2. クリックして**コマンド シェル**します。  
  
3. コマンド シェルでは、次のコマンドを入力します。   
   `get-scommanagementpack –DisplayName “DisplayName” | get-scommonitor | export.csv filename`  
  
4. .Csv ファイルが作成されます。 .Csv ファイルは、Microsoft Office Excel で開くことができます。  
  
   > [!NOTE]  
   >  Excel では、.csv ファイルをテキスト ファイルに指定する必要する必要があります。  
  
   たとえば、次のコマンドは、コア管理パックのいずれかに関連付けられているモニターのデータを取得します。   
   `get-scommanagementpack -DisplayName "BizTalk Server Monitoring" | Get-ScomMonitor | export-csv "c:\monitors.csv"`