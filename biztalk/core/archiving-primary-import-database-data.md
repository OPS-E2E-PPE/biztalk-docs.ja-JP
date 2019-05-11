---
title: プライマリ インポート データベースのアーカイブ |Microsoft Docs
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
ms.openlocfilehash: 0fff7fe5720df0b73ea84f9387d47a4d35b96051
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530623"
---
# <a name="archiving-primary-import-database-data"></a>プライマリ インポート データベースのアーカイブ
管理者は、プライマリ インポート データベースのアクティビティ インスタンス データをアーカイブする時間枠を指定できます。 BAMPrimaryImport データベースの BAM_Metadata_Activities テーブルで、OnlineWindowTimeUnit プロパティと OnlineWindowTimeLength プロパティを使用するとします。  
  
 ビジネス ユーザーが複数のアクティビティを配置した場合は、アクティビティごとに、異なる時間枠を指定できます。 アクティビティを展開する方法の詳細については、「ビジネス アクティビティを定義する」を参照してください*インフォメーション ワーカー ユーザー ガイド*します。  
  
 次の表では、OnlineWindowTimeUnit と OnlineWindowTimeLength 使用できる値について説明します。  
  
|プロパティ|値|  
|--------------|-----------|  
|OnlineWindowTimeUnit|このプロパティにすることができます。 1 か月、日、時間、または 1 分です。 このプロパティの既定値は、月です。|  
|OnlineWindowTimeLength|このプロパティは整数である必要があります。 このプロパティの既定値は、6 です。|  
  
 BAM では、パーティションがオンライン ウィンドウ (現在の時刻 - OnlineWindowTimeLength の OnlineWindowTimeUnit) よりも古い場合に、パーティションで BAM プライマリ インポート データベースからデータが移動します。 たとえば、OnlineWindowTimeLength = 5 と OnlineWindowTimeUnit 5 日間が削除よりも 1 日、古いパーティションを = です。  
  
 BAM では、BAM アーカイブ データベースにアーカイブ済みアクティビティ インスタンス データを移動します。 BizTalk BAM 構成中にデータベースをアーカイブ、BAM を指定します。 BizTalk BAM 構成の詳細については、次を参照してください。 [BAM 構成スキーマ](../core/bam-configuration-schema.md)します。  
  
 BAM キューブ更新アクティビティ キューブにインスタンス データを処理するデータ変換サービス (DTS) パッケージを実行していない場合、BAM はアクティビティ インスタンス データをアーカイブできません。  
  
 BAM データ保守 DTS パッケージの実行方法の詳細については、次を参照してください。[の BAM DTS パッケージ](../core/bam-dts-packages.md)します。  
  
 時間の経過と共にアクティビティ インスタンス データが追加されるにつれて、BAMArchive データベースはサイズの増加はします。 データベース全体を切り捨てる簡単な方法はありませんが、記憶域の要件を削減するデータベースのトランザクション ログを定期的に切り捨てることができ、定期的にバックアップおよび BAMArchive データベース全体をアーカイブすることができます。 「トランザクション ログの切り捨て」でを参照してください。 SQL Server オンライン ブックの詳細についてはします。  
  
## <a name="see-also"></a>参照  
 [Timewindow プロパティと Timeslice プロパティを定義します。](../core/defining-the-time-window-and-time-slice-properties.md)   
 [BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md)