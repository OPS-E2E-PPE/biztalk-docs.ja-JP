---
title: "管理パックのすべてのルールを表示する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7fdec550-6713-4f5f-8c04-d9218bf2df3c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08ec94eb3adb87bf6feaff032e00a61bc9b0fead
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-display-all-management-pack-rules"></a>管理パックのすべてのルールを表示する方法
次の手順を使用すると、インポートした管理パックのルールの一覧を表示できます。 Office Excel では、ルールの一覧を表示できます。  
  
### <a name="to-display-management-pack-rules"></a>管理パックのルールを表示するには  
  
1.  管理サーバーで、をクリックして**プログラム**、クリックして**System Center**です。  
  
2.  をクリックして**コマンド シェル**です。  
  
3.  コマンド シェルでは、次のコマンドを入力します。   
    `get-scommanagementpack -DisplayName "BizTalk Server Monitoring" | Get-SCOMRule | export-csv "c:\rules.csv"`  
  
4.  .Csv ファイルが作成されます。 Office Excel では、.csv ファイルを開くことができます。  
  
    > [!NOTE]  
    >  Office Excel では、.csv ファイルは、テキスト ファイルを指定する必要する必要があります。