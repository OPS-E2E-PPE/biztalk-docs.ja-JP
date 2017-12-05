---
title: "BAM 開発プロセスの概要 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 098db3f6-2a61-4cc8-88c7-2299c2e2a55e
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78ae5f1c61f2a00359e88acd75c093e2b6c2fb91
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="overview-of-the-bam-development-process"></a>BAM 開発プロセスの概要
このトピックでは、開発プロセス、および BAM データを格納するデータベースおよびテーブルについて説明します。  
  
## <a name="prerequisites-for-developing-with-bam"></a>BAM を使用した開発に必要なスキルと知識  
 BAM を使用した開発を開始するにあたっては、次の前提条件に注意してください。  
  
-   アプリケーションをインストルメント化するには、アクティビティの展開が必要です。  
  
-   SQL Server データベースに対する DBO 権限を持っているし、BAM イベント ライター ロール セキュリティ コンテキストのメンバーである必要があります。  
  
-   Microsoft .NET 4 を使用すると、アプリケーションを開発するのに必要があります。 使用すること (C#) お勧めしますが、任意の .NET 言語を使用できます。  
  
-   コンピューターに Microsoft.BizTalk.BAM.EventObservation.dll をインストールする必要があります。 DLL は 2 とおりの方法で入手できます。  
  
    -   BizTalk Server 構成マネージャーを使用して BAM ツールをインストールします。 構成マネージャーを使用することをお勧めします。構成マネージャーによって、アップグレードに必要なエントリがレジストリに自動的に追加されます。 BAM を構成する方法の詳細については、次を参照してください。[を構成する BAM ツールを使用して、Configuration Manager](http://go.microsoft.com/fwlink/?LinkId=70561) (http://go.microsoft.com/fwlink/?LinkId=70561)。  
  
    -   DLL が既にインストールされているコンピューターからコピーします。 Microsoft BizTalk Server に存在する DLL\<バージョン\>\Tracking フォルダーです。  
  
## <a name="bam-development-process"></a>BAM 開発プロセス  
 次の図は、BAM 開発フローを示しています。  
  
 ![BAM 開発作業の流れ](../core/media/dwb-bamdevelopmentflowc.gif "dwb_bamdevelopmentflowc")  
  
 BAM を使用したソリューションの開発の基本的な手順を次に示します。  
  
#### <a name="to-develop-a-bam-enabled-solution"></a>BAM によるソリューションを開発するには  
  
1.  Excel 用 BAM アドインを使用した監視モデルを作成します。  
  
    > [!NOTE]
    >  この手順で説明する手順の例で、BAM API (BizTalk Server サンプル) にあります[http://go.microsoft.com/fwlink/?LinkId=69968](http://go.microsoft.com/fwlink/?LinkId=69968)です。  
  
2.  BAM 管理ユーティリティを使用して、アクティビティを PID に展開します。  
  
3.  BAM EventStream コードを追加することによって、アプリケーションをインストルメント化します。  
  
4.  アプリケーションを実行します。 これを実行する場合、コードの内容は次のようになります。  
  
    -   プレース ホルダー レコードを bam _ 追加\<*アクティビティ名*\>_Active テーブル。  
  
    -   レコードのデータ項目を更新します。  
  
    -   アクティビティを終了し、bam _ にレコードを移動\<*アクティビティ名**\>_completed テーブル。  
  
## <a name="where-bam-data-is-stored"></a>BAM データの格納場所  
 BAM は、BAM イベントの処理に使用する EventStream クラスを持つ EventObservation 名前空間を提供します。  
  
 BAM 追跡データは、BAM プライマリ インポート データベース (PID) に格納されます。 BAM 管理ユーティリティを使用して監視モデルを展開すると、次の 5 つのテーブルが PID に作成されます。  
  
|名前|Description|  
|----------|-----------------|  
|アクティブ テーブル|Bam _ という名前\<*アクティビティ名*\>_Active、このテーブルがまだ完了していないこの種類のアクティビティを格納します。|  
|アクティブ リレーションシップ テーブル|Bam _ という名前\<*アクティビティ名*\>_ActiveRelationships、このテーブルにはまだ完了していないアクティビティの関連のアクティビティが含まれています。|  
|Continuation テーブル|Bam _ という名前\<*アクティビティ名*\>_continuations、次の表に、アクティビティの continuation アクティビティ、アクティビティが一覧表示します。|  
|完了したテーブル|Bam _ という名前\<*アクティビティ名*\>_completed です。|  
|完了したリレーションシップ テーブル|Bam _ という名前\<*アクティビティ名*\>_CompletedRelationships、次の表に、アクティビティの完了した関連アクティビティが含まれています。|  
  
 BAM アクティビティの 4 つのデータ型を取得します。  
  
-   文字列  
  
-   Data/Time (一般的にマイルストーンと呼ばれます)  
  
-   Integer  
  
-   Float