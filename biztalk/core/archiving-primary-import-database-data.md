---
title: プライマリ インポート データベースのデータをアーカイブ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Primary Import database [BAM], archiving data
- archived data, BAM
- managing [BAM], archiving data
- data, archiving [BAM]
ms.assetid: 4a014a59-0578-41fa-9441-8b582f54bbe8
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0fdfd55681fabd1b6cfc72f68b7e33150a121f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230418"
---
# <a name="archiving-primary-import-database-data"></a>プライマリ インポート データベースのアーカイブ
管理者は、プライマリ インポート データベースに格納されているアクティビティ インスタンス データをアーカイブする時間枠を指定できます。 この操作には、BAMPrimaryImport データベースの BAM_Metadata_Activities テーブルの OnlineWindowTimeUnit プロパティと OnlineWindowTimeLength プロパティを使用します。  
  
 ビジネス ユーザーが複数のアクティビティを展開している場合、アクティビティごとに別の時間枠を指定することができます。 アクティビティの展開方法の詳細についてを参照してください「ビジネス アクティビティを定義する」*情報ワーカー ユーザー ガイド*です。  
  
 次の表は、OnlineWindowTimeUnit プロパティと OnlineWindowTimeLength プロパティに使用できる値を示しています。  
  
|プロパティ|値|  
|--------------|-----------|  
|OnlineWindowTimeUnit|このプロパティには、month、day、hour、または minute を設定できます。 このプロパティの既定値は month です。|  
|OnlineWindowTimeLength|このプロパティには、整数値を指定する必要があります。 このプロパティの既定値は 6 です。|  
  
 BAM では、パーティションがオンライン時間帯 (OnlineWindowTimeLength と OnlineWindowTimeUnit で示される) よりも古くなったときに、パーティション単位で BAM プライマリ インポート データベースからデータを移動します。 たとえば、OnlineWindowTimeLength = 5 と OnlineWindowTimeUnit = day の場合、5 日以上経過しているパーティションが削除されます。  
  
 BAM では、BAM アーカイブ データベースにアーカイブしたアクティビティ インスタンス データを移動します。 BAM アーカイブ データベースは、BizTalk で BAM を構成するときに指定します。 BizTalk BAM 構成については、次を参照してください。 [BAM 構成スキーマ](../core/bam-configuration-schema.md)です。  
  
 BAM では、インスタンス データを処理してアクティビティ キューブを生成する、BAM キューブ更新のデータ変換サービス (DTS) パッケージを実行していない場合、アクティビティ インスタンスのデータをアーカイブしません。  
  
 BAM データ保守 DTS パッケージの実行方法の詳細については、次を参照してください。[の BAM DTS パッケージ](../core/bam-dts-packages.md)です。  
  
 時間と共に、アクティビティ インスタンスのデータが追加されるにつれて、BAMArchive データベースのサイズが大きくなります。 データベース全体を切り詰める簡単な方法はありませんが、データベース トランザクション ログを定期的に切り詰めて必要なストレージを削減したり、BAMArchive データベース全体のバックアップとアーカイブを定期的に行ったりすることができます。 詳細については、SQL Server Books Online の「トランザクション ログの切り詰め」を参照してください。  
  
## <a name="see-also"></a>参照  
 [時間枠とタイム スライスのプロパティを定義します。](../core/defining-the-time-window-and-time-slice-properties.md)   
 [BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md)