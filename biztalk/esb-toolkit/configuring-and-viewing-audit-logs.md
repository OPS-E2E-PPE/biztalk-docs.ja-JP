---
title: 監査ログを構成および表示 |Microsoft ドキュメント
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
ms.openlocfilehash: 03c88e0a67a393b7ddc35ee8865d99d0299d41f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289842"
---
# <a name="configuring-and-viewing-audit-logs"></a>構成して、監査ログの表示
ESB の管理ポータルでは、使用状況を監視し、問題を追跡するためのアクションの監査ログを保持します。 管理者は、監査ログへの書き込みは、ポータルのどのイベントを指定できます。  
  
### <a name="to-view-the-audit-logs-for-the-portal"></a>ポータルの監査ログを表示するには  
  
1.  をポイント、 **Admin**ポータルのメイン メニュー タブをクリックして**監査ログの管理**を開くには、[監査ログ ページ](../esb-toolkit/audit-log-page.md)です。  
  
2.  再送信の詳細と再送信されたメッセージの元のメッセージを表示するには、監査ログ – メッセージ ビューアー ページを開く、リスト内のメッセージの識別子をクリックします。  
  
### <a name="to-configure-the-auditing-settings-for-the-portal"></a>ポータルの監査設定を構成するには  
  
1.  (そのうちポータル管理者は自動的にメンバー)、BizTalk Server 管理者アカウント グループのメンバーであるアカウントを使用してポータルにログオンすることを確認します。  
  
2.  をポイント、 **Admin**ポータルのメイン メニュー タブをクリックして**フォールト設定**を開くには、ポータル[フォールトの設定 ページ](../esb-toolkit/fault-settings-page.md)です。  
  
3.  監査オプションを変更するにあるチェック ボックスを選択、 **AuditOptions**セクションの各イベントを監査します。 使用可能なイベントは、エラーを再送信するときに、変更した設定の保存、編集、およびエラーの後に障害を正常に再送信です。