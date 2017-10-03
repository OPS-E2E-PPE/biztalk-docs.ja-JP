---
title: "ライブ データ ブックの接続文字列を更新する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d2702fb-637c-46db-8b62-08ae15f983ba
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60de5d1ae904bdefffcf490e3a39d000b28a341d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-update-the-connection-string-for-the-live-data-workbook"></a>ライブ データ ブックの接続文字列を更新する方法
BAM プライマリ インポート データベースを別のサーバーに移動するときには、BAM ライブ データ ブックの接続文字列を、新しいサーバーを示すように更新する必要があります。 この更新には Excel 用 BAM アドインを使用します。  
  
### <a name="to-update-the-live-data-workbook-to-point-to-a-new-server"></a>新しいサーバーを示すようライブ データ ブックを更新するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office**、順にクリック**Microsoft Office Excel**です。  
  
2.  クリックして、**ファイル** メニューをクリックして**開く**です。 目的の BAM ライブ データ ブックに移動し、をクリックして**開く**です。  
  
3.  をクリックして、 **BAM**でメニュー、**アドイン** タブをクリックして**BAM データベースの接続**を開くには、 **BAM データベースの** ダイアログ ボックス。  
  
4.  **SQL Server**  ボックスに、BAM プライマリ インポート データベースを今すぐ SQL server の名前が存在する型。  
  
5.  BAM プライマリ インポート データベースを選択して、**データベース名**ドロップダウン リスト。  
  
6.  **[OK]** をクリックして、ダイアログ ボックスを閉じます。  
  
7.  ブックを保存します。  
  
## <a name="see-also"></a>参照  
 [BAM の管理](../core/managing-bam.md)   
 [Excel 用 BAM アドインを使用するための要件](../core/requirements-for-using-the-bam-add-in-for-excel.md)