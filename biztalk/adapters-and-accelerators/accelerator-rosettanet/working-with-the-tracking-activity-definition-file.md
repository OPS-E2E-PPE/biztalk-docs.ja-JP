---
title: "追跡アクティビティ定義ファイルの操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tracking, activity definition file
- activity definition file
- activity definition file, about activity definition file
- tracking, managing views
- activity definition file, activity fields
ms.assetid: 0592a844-aad7-4054-b1e7-344f1086f0b1
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 751b05f28682ecc0a0230fc924cf706d0531784d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="working-with-the-tracking-activity-definition-file"></a>追跡アクティビティ定義ファイルの操作
アクティビティ定義ファイルには、追跡に関する情報が含まれています。 プロセスとメッセージ アクティビティ[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]です。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]BizTalk ビジネス アクティビティ監視 (BAM) 追跡データを管理するのにには、このファイルを使用します。 定義ファイルは XML ファイル (Tracking.xml) を[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]でインストール、 \<*ドライブ*>: \Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet \BAMTracking フォルダーです。 通常は、Tracking.xml で定義されたアクティビティで十分に目的を達成できます。  
  
 追跡アクティビティ、ビュー、およびテーブルの詳細については、次を参照してください。[追跡強化](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md)です。 BAM の詳細については、[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] ヘルプの「ビジネス アクティビティ監視 (BAM)」を参照してください。  
  
## <a name="managing-tracking-views"></a>追跡ビューの管理  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] による追跡中は BizTalk 追跡プロファイル エディターを使用しないでください。 追跡ポイントはカスタマイズできないため、アクティビティの定義を変更しないでください。 ただし、BAM ビューと展開の管理は可能です。 変更するためには、[!INCLUDE[btsExcel](../../includes/btsexcel-md.md)]スプレッドシート (Tracking.xls) を[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]でインストール、 \<*ドライブ*>: \Program Files\Microsoft BizTalk 2013 Accelerator for rosettanet \bamtracking フォルダーです。 詳細については、「追跡ビューの管理」を参照してください。  
  
 Tracking.xml に定義されているビューでニーズが満たされない場合は、次のように、BAM で追跡する情報についての別のビューを定義することができます。  
  
#### <a name="to-create-different-tracking-views"></a>別の追跡ビューを作成するには  
  
1.  **[スタート]**ボタンをクリックし、 **[ファイル名を指定して実行]**をクリックします。 入力**cmd**クリックして実行 ダイアログ ボックスの名前 テキスト ボックスで**OK**です。 コマンド ライン ダイアログ ボックスで、tracking.xml の展開を解除し、をクリックするには、次のコードを入力してください**OK**:。  
  
    ```  
    cd %ProgramFiles%\Microsoft BizTalk Server 2013\Tracking  
    bm remove-all  -DefinitionFile:"%ProgramFiles%\Microsoft BizTalk 2013 Accelerator for RosettaNet\BAMTracking\<filename>.xml"  
    ```  
  
2.  [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーに移動*\<ドライブ >*: \Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet \BAM 追跡します。 Tracking.xls をダブルクリックします。  
  
3.  ビジネス アクティビティ監視に新しいビューを作成します。 ビューを作成する方法については、[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] ヘルプの「ビジネス アクティビティ監視の管理」を参照してください。  
  
4.  をクリックして**BAM**、クリックして**XML のエクスポート**です。 目的の場所に移動、(Tracking.xml 以外)、ファイル名を入力し、クリックして**保存**です。  
  
    > [!IMPORTANT]
    >  追跡 XLS ファイルに新しい追跡ビューを定義してこのファイルから XML ファイルをエクスポートすると、一部のフィールド名が少し変更されます。 カスタマイズした追跡 XML ファイルのフィールドを、BTARN セットアップによってインストールされた標準の Tracking.xml のフィールドと照合して、それらのフィールド名を修正します。  
  
5.  新しい追跡 XML ファイルを展開します。 これを行うには、をクリックして**開始**、順にクリック**実行**です。 入力**cmd**クリックして実行 ダイアログ ボックスの名前 テキスト ボックスで**OK**です。 コマンド ライン ダイアログ ボックスで、新しい追跡ファイルを展開し、をクリックするには、次のコードを入力してください。 **OK**です。 既定の Tracking.xml ファイルを上書きしないようにするため、追跡 XML ファイルの名前を変更することをお勧めします。  
  
    ```  
    cd %ProgramFiles%\Microsoft BizTalk Server 2013\Tracking  
    bm.exe deploy-all -DefinitionFile:"%ProgramFiles%\Microsoft BizTalk 2030 Accelerator for RosettaNet\BAMTracking\<filename>.xml"  
    ```  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] データベースに格納されているため、BAM で追跡される情報には、メッセージの内容は含まれません。  
  
 ビジネス アクティビティ監視管理ユーティリティを使用すると、BAM 追跡の展開を管理できます。 このユーティリティの詳細については、[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] ヘルプの「ビジネス アクティビティ監視ユーティリティの使用」を参照してください。  
  
## <a name="activity-fields"></a>アクティビティ フィールド  
 アクティビティ定義ファイルには、次のようなメッセージ アクティビティ フィールドがあります。  
  
-   ActivityName  
  
-   カテゴリ  
  
-   ContentKey  
  
-   DestinationPartyName  
  
-   ErrorDescription  
  
-   HasError  
  
-   InReplyToMessageID  
  
-   IsReceived  
  
-   MessageTrackingID  
  
-   NoFPipInstance  
  
-   PipCode  
  
-   PipInstanceID  
  
-   PiPVersion  
  
-   SourcePartName  
  
-   Timestamp  
  
 アクティビティ定義ファイルには、次のようなプロセス アクティビティ フィールドがあります。  
  
-   EndTime  
  
-   InitiatorPartyName  
  
-   IsInitiatorRole  
  
-   PipCode  
  
-   PipInstanceID  
  
-   PipName  
  
-   PipVersion  
  
-   ResponderPartyName  
  
-   StartTime  
  
-   [状態]  
  
## <a name="see-also"></a>参照  
 [拡張追跡](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md)   
 [構成、証明書、データベース、およびセキュリティを管理します。](manage-configuration-certificates-databases-security.md)