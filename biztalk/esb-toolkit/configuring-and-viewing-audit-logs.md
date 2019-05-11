---
title: 監査ログを構成し、表示 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c725bf04-d59f-42c1-b327-b4268421689c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dad02f6c54d1535c3580093d8c981b0e29731f8c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302116"
---
# <a name="configuring-and-viewing-audit-logs"></a>構成し、監査ログの表示
ESB 管理ポータルでは、使用状況を監視し、問題を追跡するためのアクションの監査ログを保持します。 管理者は、ポータルが監査ログに書き込むイベントの種類を指定できます。  
  
### <a name="to-view-the-audit-logs-for-the-portal"></a>ポータルの監査ログを表示するには  
  
1.  ポイントして、**管理者**ポータルのメイン メニューで、タブをクリックして**監査ログの管理**を開く、[監査ログ ページ](../esb-toolkit/audit-log-page.md)。  
  
2.  を再送信されたメッセージの元のメッセージの再送信の詳細を表示するには、監査ログ – メッセージ ビューアー ページを開くには、一覧でメッセージの識別子をクリックします。  
  
### <a name="to-configure-the-auditing-settings-for-the-portal"></a>ポータルの監査設定を構成するには  
  
1.  (ポータル管理者の自動的にメンバー)、BizTalk Server 管理者アカウント グループのメンバーであるアカウントを使用してポータルにログオンすることを確認します。  
  
2.  をポイント、**管理者**ポータルのメイン メニューで、タブをクリックして**フォールト設定**ポータルを開く[エラー設定ページ](../esb-toolkit/fault-settings-page.md)します。  
  
3.  監査オプションを変更するには、チェック ボックスをオン、 **AuditOptions**セクションの各イベントを監査します。 使用可能なイベントは、エラーを再送信するときに、変更された設定の保存、編集、およびエラーの後に障害を正常に再送信が。