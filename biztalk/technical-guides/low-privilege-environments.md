---
title: 低い特権の環境 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: abdc45d0-b63a-4b6c-80c4-1f8e87644cd9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 121655ecb70c084637f2fd481dc6bd2fce7a57cc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396291"
---
# <a name="low-privilege-environments"></a>低い特権の環境
複数のワークフローに含まれている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理パックには、特定のアクションを実行する管理者特権での権限が必要です。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理パックでは、低い特権の環境での基本的な監視機能を実行することができます。 2 つの管理ロール: BizTalk Server 管理者、および BizTalk Server Operator します。 BizTalk Server の管理者は、構成データおよび追跡データへのアクセスを高い特権を持つロールです。 BizTalk Server の管理者は、このような参加と成果物を開始、すべてのキー管理タスクを実行できます。 BizTalk Server Operator は、監視とトラブルシューティング操作にのみアクセス権を持つ特権の低いロールです。 詳細については、次を参照してください。[最小セキュリティ ユーザー権限](http://technet.microsoft.com/library/aa559845\(BTS.80\).aspx)します。  
  
 使用して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理パック。  
  
-   BizTalk Server Operator グループのメンバは、次の操作を実行できます。  
  
    -   BizTalk Server の監視のエラー、中断された messages\instances、構成の表示をクエリします。  
  
    -   BizTalk Server のインストールと成果物を監視します。  
  
    -   サービスの状態とメッセージ フローの表示。  
  
    -   開始または停止アプリケーションやオーケストレーションなどの成果物、送信ポートまたは送信ポート グループに参加している状態にあります。  
  
    -   受信場所の有効化または無効化。 変更は、次回のキャッシュ更新の後で有効になります。キャッシュの更新間隔は既定では 60 秒で、 BizTalk Server のグループ レベルで設定できます。  
  
-   BizTalk Server Operators グループのメンバは、次の操作を実行できません。  
  
    -   BizTalk Server の構成の変更。  
  
    -   個人情報 (PII) に分類されるメッセージ コンテキストのプロパティまたはメッセージ本文の表示。  
  
    -   実行中のシステムに対するサブスクリプションを削除や追加など、メッセージ ルーティングのコースを変更する操作。これには BizTalk Server ランタイムへのメッセージの公開も含まれます。  
  
> [!NOTE]  
>  BTSNTSvc.exe サービスを再起動するなどの管理パックによって提供されるすべての監視タスクを実行するには、BizTalk サーバーでローカルの Administrators グループのメンバーがあります。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [監視](../technical-guides/monitoring.md)  
  
-   [検出](../technical-guides/discoveries.md)