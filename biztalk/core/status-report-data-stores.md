---
title: "状態レポート データ ストア |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6cd40ce8-1ac6-43b4-9cef-7cd045e8893c
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da876f1151b641216cf9613f6830ed84049da83d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="status-report-data-stores"></a>状態レポート データ ストア
状態レポート追跡データは、BAM プライマリ インポート データベースに格納されます。 このデータベースの多数のテーブル (dbo.bam_AS2、dbo.bam.batching、dbo.bam.InterchangeStatusActivity などで始まるテーブルを含む) は、EDI および AS2 メッセージ データに使用されます。 EDI レポートが無効になっている場合でも、状態データはプライマリ インポートに格納されます。 状態レポートがアクティブになっている場合、実行できるのは、状態レポート内のこのデータの表示と照会のみです。  
  
 否認不可を目的とするメッセージ データを格納できるようにすると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は BizTalk 追跡データベース (BizTalkDTADb) の EDI メッセージ コンテンツ テーブルに EDI または AS2 データを格納します。 ペイロードの詳細を表示するメッセージの内容の記憶域を有効にした場合 (を選択して、 **reporting 用メッセージ ペイロードを格納**アグリーメント プロパティで、**全般プロパティ**のページ**全般** タブで、**アグリーメントのプロパティ** ダイアログ ボックス)、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]もこのテーブルにトランザクション セットを保存します。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、BAM プライマリ インポート データベースと BizTalkDTADb データベースからデータをアーカイブして削除します。 データベースのテーブルは、定期的にクリーンアップされます。  
  
> [!NOTE]
>  BAM プライマリ インポート データベースと DTA DB データベースは、それぞれのアーカイブ間隔が異なる場合、同期しない可能性があります。  
  
 EDI および AS2 状態レポートは、パフォーマンスに影響する可能性があります。 詳細についてを参照してください「のパフォーマンスに関する考慮事項の EDI および AS2 状態レポート」 [EDI と AS2 のパフォーマンスの既知の問題](../core/known-issues-with-edi-and-as2-performance.md)です。  
  
## <a name="see-also"></a>参照  
 [EDI および AS2 状態レポートのデータを格納する方法](../core/how-data-is-stored-for-edi-and-as2-status-reports.md)