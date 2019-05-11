---
title: 追跡アクティビティ定義ファイルの操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracking, activity definition file
- activity definition file
- activity definition file, about activity definition file
- tracking, managing views
- activity definition file, activity fields
ms.assetid: 0592a844-aad7-4054-b1e7-344f1086f0b1
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f528125d0fe25139dbd7b8e4a2a2792f42d9264
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379102"
---
# <a name="working-with-the-tracking-activity-definition-file"></a>追跡アクティビティ定義ファイルの操作
アクティビティ定義ファイルには、追跡に関する情報が含まれています。 Microsoft® プロセスとメッセージ アクティビティ[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]します。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] BizTalk ビジネス アクティビティ監視 (BAM) 追跡データを管理するのにには、このファイルを使用します。 定義ファイルは、XML ファイル (Tracking.xml) を[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]でインストール、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet \BAMTracking フォルダー。 通常は、Tracking.xml で定義されたアクティビティで十分に目的を達成できます。  
  
 追跡アクティビティ、ビュー、およびテーブルの詳細については、次を参照してください。[拡張追跡](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md)します。 BAM の詳細については、"ビジネス アクティビティ監視 (BAM)"で BizTalk Server のヘルプを参照してください。  
  
## <a name="managing-tracking-views"></a>追跡ビューの管理  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] による追跡中は BizTalk 追跡プロファイル エディターを使用しないでください。 追跡ポイントはカスタマイズできないため、アクティビティの定義を変更しないでください。 ただし、BAM ビューと展開の管理は可能です。 これを行うには、変更する、[!INCLUDE[btsExcel](../../includes/btsexcel-md.md)]スプレッドシート (Tracking.xls) を[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]でインストール、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk 2013 Accelerator for してBAMTracking フォルダーです。 詳細については、「追跡ビューの管理」を参照してください。  
  
 Tracking.xml に定義されているビューでニーズが満たされない場合は、次のように、BAM で追跡する情報についての別のビューを定義することができます。  
  
#### <a name="to-create-different-tracking-views"></a>別の追跡ビューを作成するには  
  
1. **[スタート]** ボタンをクリックし、 **[ファイル名を指定して実行]** をクリックします。 入力**cmd**のクリックして実行 ダイアログ ボックスでは、開いているテキスト ボックスに**OK**します。 コマンド ライン ダイアログ ボックスで、tracking.xml の展開を解除し、をクリックするには、次のコードを入力します**OK**:。  
  
   ```  
   cd %ProgramFiles%\Microsoft BizTalk Server 2013\Tracking  
   bm remove-all  -DefinitionFile:"%ProgramFiles%\Microsoft BizTalk 2013 Accelerator for RosettaNet\BAMTracking\<filename\>.xml"  
   ```  
  
2. [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーに移動*\<ドライブ\>*: \Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet \BAM 追跡します。 Tracking.xls をダブルクリックします。  
  
3. ビジネス アクティビティ監視に新しいビューを作成します。 これを行う方法については、BizTalk Server ヘルプの「ビジネス アクティビティ監視の管理」を参照してください。  
  
4. クリックして**BAM**、 をクリックし、 **XML のエクスポート**します。 目的の場所に移動、(Tracking.xml 以外)、ファイル名を入力し、クリックして**保存**します。  
  
   > [!IMPORTANT]
   >  追跡 XLS ファイルに新しい追跡ビューを定義してこのファイルから XML ファイルをエクスポートすると、一部のフィールド名が少し変更されます。 カスタマイズした追跡 XML ファイルのフィールドを、BTARN セットアップによってインストールされた標準の Tracking.xml のフィールドと照合して、それらのフィールド名を修正します。  
  
5. 新しい追跡 XML ファイルを展開します。 これを行うには、次のようにクリックします。**開始**、 をクリックし、**実行**します。 入力**cmd**のクリックして実行 ダイアログ ボックスでは、開いているテキスト ボックスに**OK**します。 コマンド ライン ダイアログ ボックスで、新しい追跡ファイルを展開し、をクリックするには、次のコードを入力します。 **OK**します。 既定の Tracking.xml ファイルを上書きしないようにするため、追跡 XML ファイルの名前を変更することをお勧めします。  
  
   ```  
   cd %ProgramFiles%\Microsoft BizTalk Server 2013\Tracking  
   bm.exe deploy-all -DefinitionFile:"%ProgramFiles%\Microsoft BizTalk 2030 Accelerator for RosettaNet\BAMTracking\<filename\>.xml"  
   ```  
  
   [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] データベースに格納されているため、BAM で追跡される情報には、メッセージの内容は含まれません。  
  
   ビジネス アクティビティ監視管理ユーティリティを使用すると、BAM 追跡の展開を管理できます。 このユーティリティの詳細については、「を使用して、ビジネス アクティビティ監視管理ユーティリティ」BizTalk Server のヘルプを参照してください。  
  
## <a name="activity-fields"></a>アクティビティ フィールド  
 アクティビティ定義ファイルには、次のようなメッセージ アクティビティ フィールドがあります。  
  
- ActivityName  
  
- カテゴリ  
  
- ContentKey  
  
- DestinationPartyName  
  
- ErrorDescription  
  
- HasError  
  
- InReplyToMessageID  
  
- IsReceived  
  
- MessageTrackingID  
  
- NoFPipInstance  
  
- PipCode  
  
- PipInstanceID  
  
- PiPVersion  
  
- SourcePartName  
  
- Timestamp  
  
  アクティビティ定義ファイルには、次のようなプロセス アクティビティ フィールドがあります。  
  
- EndTime  
  
- InitiatorPartyName  
  
- IsInitiatorRole  
  
- PipCode  
  
- PipInstanceID  
  
- PipName  
  
- PipVersion  
  
- ResponderPartyName  
  
- StartTime  
  
- 状態  
  
## <a name="see-also"></a>参照  
 [拡張追跡](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md)   
 [構成、証明書、データベース、セキュリティの管理](manage-configuration-certificates-databases-security.md)