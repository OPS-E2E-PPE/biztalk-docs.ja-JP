---
title: "低い特権の環境 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: abdc45d0-b63a-4b6c-80c4-1f8e87644cd9
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d43f363bd96dd8e3109a8ce21b9565fb43e5f9bf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="low-privilege-environments"></a>低い特権の環境
複数のワークフローに含まれている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理パックは、特定のアクションを実行する高度な権限を必要とします。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理パックでは、低特権の環境で基本的な監視機能を実行することができます。 2 つの管理ロール: BizTalk Server 管理者と BizTalk Server Operator です。 BizTalk Server 管理者は権限レベルの高いロールで、構成データおよび追跡データにアクセスできます。 BizTalk Server 管理者は、このような参加と成果物を開始、すべてのキー管理タスクを実行できます。 BizTalk Server Operator は、監視とトラブルシューティング操作にのみアクセス権を持つ特権の低いロールです。 詳細については、次を参照してください。[最低限のセキュリティ ユーザー権限](http://technet.microsoft.com/library/aa559845\(BTS.80\).aspx)です。  
  
 使用して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理パック。  
  
-   BizTalk Server Operator グループのメンバは、次の操作を実行できます。  
  
    -   エラー、中断された messages\instances、構成の表示には、BizTalk Server を監視します。  
  
    -   BizTalk Server のインストールと成果物を監視します。  
  
    -   サービスの状態とメッセージ フローの表示。  
  
    -   開始またはアプリケーションやオーケストレーションなどの成果物を停止、送信ポートまたは送信ポート グループ参加している状態にあります。  
  
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