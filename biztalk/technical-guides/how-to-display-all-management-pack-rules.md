---
title: すべての管理パックのルールを表示する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7fdec550-6713-4f5f-8c04-d9218bf2df3c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c22102080d5852ab838ce8fa3ce1d421e9a42900
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253503"
---
# <a name="how-to-display-all-management-pack-rules"></a>すべての管理パックのルールを表示する方法
インポートした管理パックのルールの一覧を表示するのにには、次の手順を使用します。 Office Excel では、ルールの一覧を表示できます。  
  
### <a name="to-display-management-pack-rules"></a>管理パックのルールを表示するには  
  
1.  管理サーバーで次のようにクリックします。**プログラム**、 をクリックし、 **System Center**します。  
  
2.  クリックして**コマンド シェル**します。  
  
3.  コマンド シェルでは、次のコマンドを入力します。   
    `get-scommanagementpack -DisplayName "BizTalk Server Monitoring" | Get-SCOMRule | export-csv "c:\rules.csv"`  
  
4.  .Csv ファイルが作成されます。 Office Excel で .csv ファイルを開くことができます。  
  
    > [!NOTE]  
    >  Office Excel で .csv ファイルをテキスト ファイルに指定する必要する必要があります。