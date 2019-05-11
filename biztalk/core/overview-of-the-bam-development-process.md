---
title: BAM 開発プロセスの概要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 098db3f6-2a61-4cc8-88c7-2299c2e2a55e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a5665e5c8b9cdf098972b6d2c82d772c5cdfee7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393399"
---
# <a name="overview-of-the-bam-development-process"></a>BAM 開発プロセスの概要
このトピックでは、開発プロセスと、データベースおよび BAM データを格納するテーブルについて説明します。  
  
## <a name="prerequisites-for-developing-with-bam"></a>BAM を使用した開発の前提条件  
 BAM を使用した開発を開始する前に、次の前提条件に注意してください。  
  
-   アプリケーションをインストルメント化するには、アクティビティの展開が必要です。  
  
-   SQL Server データベースの DBO 権限を持っているし、BAM イベント ライター ロール セキュリティ コンテキストのメンバーである必要があります。  
  
-   Microsoft .NET 4 を使用して、アプリケーションを開発する必要があります。 任意の .NET 言語を使用できますが、使用することをお勧めします。C#します。  
  
-   Microsoft.BizTalk.BAM.EventObservation.dll をコンピューターにインストールする必要があります。 2 つの方法で DLL を入手できます。  
  
    -   BAM ツールをインストールするのにには、BizTalk Server 構成マネージャーを使用します。 レジストリのアップグレードに適切なエントリに配置するために、Configuration Manager を使用することをお勧めします。 BAM を構成する方法の詳細については、次を参照してください。[を構成する BAM ツールを使用して、Configuration Manager](http://go.microsoft.com/fwlink/?LinkId=70561) (http://go.microsoft.com/fwlink/?LinkId=70561)します。  
  
    -   既にインストールされているコンピューターから DLL をコピーします。 Microsoft BizTalk Server で、DLL が存在する\<バージョン\>\Tracking フォルダー。  
  
## <a name="bam-development-process"></a>BAM 開発プロセス  
 次の図には、BAM 開発フローについて説明します。  
  
 ![BAM 開発作業の流れ](../core/media/dwb-bamdevelopmentflowc.gif "dwb_bamdevelopmentflowc")  
  
 次の手順では、BAM によるソリューションを開発するための基本的な手順が一覧表示します。  
  
#### <a name="to-develop-a-bam-enabled-solution"></a>BAM が有効なソリューションを開発するには  
  
1.  Excel 用 BAM アドインに監視モデルを作成します。  
  
    > [!NOTE]
    >  この手順でメモした手順の例については、BAM api (BizTalk Server サンプル) で見つかります[ http://go.microsoft.com/fwlink/?LinkId=69968](http://go.microsoft.com/fwlink/?LinkId=69968)します。  
  
2.  アクティビティを PID に展開するのにには、BAM 管理ユーティリティを使用します。  
  
3.  BAM EventStream コードを追加することで、アプリケーションをインストルメント化します。  
  
4.  アプリケーションを実行します。 これを行うと、コードが行われます。  
  
    -   プレース ホルダー レコードが、bam _ \<*アクティビティ名*\>_Active テーブル。  
  
    -   レコード内のデータ項目を更新します。  
  
    -   アクティビティを終了し、bam _ にレコードを移動\<* アクティビティ名 * *\>_completed テーブル。  
  
## <a name="where-bam-data-is-stored"></a>BAM データの保存場所  
 BAM では、BAM イベントを処理するために使用する EventStream クラスを含む持つ EventObservation 名前空間を提供します。  
  
 BAM の追跡データは、BAM プライマリ インポート データベース (PID) に格納されます。 BAM 管理ユーティリティを使用して監視モデルを展開するときに、次の 5 つのテーブルが PID に作成されます。  
  
|名前|説明|  
|----------|-----------------|  
|アクティブなテーブル|Bam _ という名前\<*アクティビティ名*\>(_a)、このテーブルにはまだ完了していないこの種類のアクティビティが格納されます。|  
|アクティブ リレーションシップ テーブル|Bam _ という名前\<*アクティビティ名*\>_ActiveRelationships、このテーブルにはまだ完了していないアクティビティの関連のアクティビティが含まれています。|  
|Continuation テーブル|Bam _ という名前\<*アクティビティ名*\>_continuations、次の表に、アクティビティの continuation アクティビティが一覧表示されます。|  
|完了したテーブル|Bam _ という名前\<*アクティビティ名*\>_completed します。|  
|完了したリレーションシップ テーブル|Bam _ という名前\<*アクティビティ名*\>_CompletedRelationships、次の表に、アクティビティの完了した関連アクティビティが含まれています。|  
  
 4 つの種類のデータを BAM アクティビティをキャプチャするには。  
  
-   String  
  
-   日付/時刻 (マイルス トーンとも呼ばれます)  
  
-   Integer  
  
-   float