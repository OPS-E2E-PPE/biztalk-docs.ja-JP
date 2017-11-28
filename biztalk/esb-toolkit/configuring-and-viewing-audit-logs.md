---
title: "監査ログを構成および表示 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c725bf04-d59f-42c1-b327-b4268421689c
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03c88e0a67a393b7ddc35ee8865d99d0299d41f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-and-viewing-audit-logs"></a><span data-ttu-id="26b8f-102">構成して、監査ログの表示</span><span class="sxs-lookup"><span data-stu-id="26b8f-102">Configuring and Viewing Audit Logs</span></span>
<span data-ttu-id="26b8f-103">ESB の管理ポータルでは、使用状況を監視し、問題を追跡するためのアクションの監査ログを保持します。</span><span class="sxs-lookup"><span data-stu-id="26b8f-103">The ESB Management Portal maintains an audit log of actions that help you to monitor usage and track problems.</span></span> <span data-ttu-id="26b8f-104">管理者は、監査ログへの書き込みは、ポータルのどのイベントを指定できます。</span><span class="sxs-lookup"><span data-stu-id="26b8f-104">Administrators can specify which events the portal will write to the audit log.</span></span>  
  
### <a name="to-view-the-audit-logs-for-the-portal"></a><span data-ttu-id="26b8f-105">ポータルの監査ログを表示するには</span><span class="sxs-lookup"><span data-stu-id="26b8f-105">To view the audit logs for the portal</span></span>  
  
1.  <span data-ttu-id="26b8f-106">をポイント、 **Admin**ポータルのメイン メニュー タブをクリックして**監査ログの管理**を開くには、[監査ログ ページ](../esb-toolkit/audit-log-page.md)です。</span><span class="sxs-lookup"><span data-stu-id="26b8f-106">Point to the **Admin** tab on the portal main menu, and then click **Manage Audit Log** to open the [Audit Log Page](../esb-toolkit/audit-log-page.md).</span></span>  
  
2.  <span data-ttu-id="26b8f-107">再送信の詳細と再送信されたメッセージの元のメッセージを表示するには、監査ログ – メッセージ ビューアー ページを開く、リスト内のメッセージの識別子をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26b8f-107">To see the resubmission details and the original message for resubmitted messages, click the identifier of a message in the list to open the Audit Log – Message Viewer page.</span></span>  
  
### <a name="to-configure-the-auditing-settings-for-the-portal"></a><span data-ttu-id="26b8f-108">ポータルの監査設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="26b8f-108">To configure the auditing settings for the portal</span></span>  
  
1.  <span data-ttu-id="26b8f-109">(そのうちポータル管理者は自動的にメンバー)、BizTalk Server 管理者アカウント グループのメンバーであるアカウントを使用してポータルにログオンすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="26b8f-109">Ensure that you log on to the portal using an account that is a member of the BizTalk Server Administrators account group (of which portal administrators are automatically a member).</span></span>  
  
2.  <span data-ttu-id="26b8f-110">をポイント、 **Admin**ポータルのメイン メニュー タブをクリックして**フォールト設定**を開くには、ポータル[フォールトの設定 ページ](../esb-toolkit/fault-settings-page.md)です。</span><span class="sxs-lookup"><span data-stu-id="26b8f-110">Point to the **Admin** tab on the portal main menu, and then click **Fault Settings** to open the portal [Fault Settings Page](../esb-toolkit/fault-settings-page.md).</span></span>  
  
3.  <span data-ttu-id="26b8f-111">監査オプションを変更するにあるチェック ボックスを選択、 **AuditOptions**セクションの各イベントを監査します。</span><span class="sxs-lookup"><span data-stu-id="26b8f-111">To change the auditing options, select the check boxes in the **AuditOptions** section for each event you want to audit.</span></span> <span data-ttu-id="26b8f-112">使用可能なイベントは、エラーを再送信するときに、変更した設定の保存、編集、およびエラーの後に障害を正常に再送信です。</span><span class="sxs-lookup"><span data-stu-id="26b8f-112">The available events are the saving of modified settings, successful resubmission of a fault after editing, and failure when resubmitting a fault.</span></span>