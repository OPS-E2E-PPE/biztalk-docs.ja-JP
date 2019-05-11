---
title: 状態レポート データ ストア |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6cd40ce8-1ac6-43b4-9cef-7cd045e8893c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0cb1d8d2a85cc88364da5bb43131213903b37d2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392877"
---
# <a name="status-report-data-stores"></a>状態レポート データ ストア
状態レポート追跡データは、BAM プライマリ インポート データベースに格納されます。 このデータベース内のテーブルの数は、以降で dbo.bam_AS2、dbo.bam.batching、dbo.bam.InterchangeStatusActivity、およびその他のユーザー テーブルを含む EDI および AS2 のメッセージ データに使用されます。 状態データは、EDI レポートが無効になっている場合でも、プライマリ インポートに格納されます。 表示と、状態レポート UI の状態レポートが有効な場合にこのデータを照会するのみなります。  
  
 否認不可のために、メッセージ データのストレージを有効にした場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]BizTalk 追跡データベース (BizTalkDTADb) の EDI メッセージ コンテンツ テーブルに EDI または AS2 データを格納します。 メッセージの内容、ペイロードの詳細を表示するためのストレージを有効にした場合 (選択して、**メッセージ ペイロードを格納するレポートの**アグリーメントのプロパティ、**全般プロパティ**のページ**全般** タブで、**アグリーメントのプロパティ** ダイアログ ボックス)、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]このテーブルにトランザクション セットを格納もされます。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アーカイブして、BAM プライマリ インポート データベースと BizTalkDTADb データベースからデータを削除します。 データベースのテーブルに定期的なスケジュールに従ってクリーンアップされます。  
  
> [!NOTE]
>  BAM プライマリ インポート データベースと DTA DB データベースは同期していない場合、それぞれにアーカイブするためのさまざまな間隔で可能性があります。  
  
 EDI および AS2 状態レポートと、パフォーマンスに影響を与えるをがあります。 詳細についてを参照してください「のパフォーマンスに関する考慮事項の EDI および AS2 状態レポート」 [EDI および AS2 のパフォーマンスに関する既知の問題](../core/known-issues-with-edi-and-as2-performance.md)します。  
  
## <a name="see-also"></a>参照  
 [EDI および AS2 状態レポートのデータ格納方法](../core/how-data-is-stored-for-edi-and-as2-status-reports.md)