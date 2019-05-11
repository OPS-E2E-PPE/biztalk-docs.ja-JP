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
# <a name="configuring-and-viewing-audit-logs"></a><span data-ttu-id="16b06-102">構成し、監査ログの表示</span><span class="sxs-lookup"><span data-stu-id="16b06-102">Configuring and Viewing Audit Logs</span></span>
<span data-ttu-id="16b06-103">ESB 管理ポータルでは、使用状況を監視し、問題を追跡するためのアクションの監査ログを保持します。</span><span class="sxs-lookup"><span data-stu-id="16b06-103">The ESB Management Portal maintains an audit log of actions that help you to monitor usage and track problems.</span></span> <span data-ttu-id="16b06-104">管理者は、ポータルが監査ログに書き込むイベントの種類を指定できます。</span><span class="sxs-lookup"><span data-stu-id="16b06-104">Administrators can specify which events the portal will write to the audit log.</span></span>  
  
### <a name="to-view-the-audit-logs-for-the-portal"></a><span data-ttu-id="16b06-105">ポータルの監査ログを表示するには</span><span class="sxs-lookup"><span data-stu-id="16b06-105">To view the audit logs for the portal</span></span>  
  
1.  <span data-ttu-id="16b06-106">ポイントして、**管理者**ポータルのメイン メニューで、タブをクリックして**監査ログの管理**を開く、[監査ログ ページ](../esb-toolkit/audit-log-page.md)。</span><span class="sxs-lookup"><span data-stu-id="16b06-106">Point to the **Admin** tab on the portal main menu, and then click **Manage Audit Log** to open the [Audit Log Page](../esb-toolkit/audit-log-page.md).</span></span>  
  
2.  <span data-ttu-id="16b06-107">を再送信されたメッセージの元のメッセージの再送信の詳細を表示するには、監査ログ – メッセージ ビューアー ページを開くには、一覧でメッセージの識別子をクリックします。</span><span class="sxs-lookup"><span data-stu-id="16b06-107">To see the resubmission details and the original message for resubmitted messages, click the identifier of a message in the list to open the Audit Log – Message Viewer page.</span></span>  
  
### <a name="to-configure-the-auditing-settings-for-the-portal"></a><span data-ttu-id="16b06-108">ポータルの監査設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="16b06-108">To configure the auditing settings for the portal</span></span>  
  
1.  <span data-ttu-id="16b06-109">(ポータル管理者の自動的にメンバー)、BizTalk Server 管理者アカウント グループのメンバーであるアカウントを使用してポータルにログオンすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="16b06-109">Ensure that you log on to the portal using an account that is a member of the BizTalk Server Administrators account group (of which portal administrators are automatically a member).</span></span>  
  
2.  <span data-ttu-id="16b06-110">をポイント、**管理者**ポータルのメイン メニューで、タブをクリックして**フォールト設定**ポータルを開く[エラー設定ページ](../esb-toolkit/fault-settings-page.md)します。</span><span class="sxs-lookup"><span data-stu-id="16b06-110">Point to the **Admin** tab on the portal main menu, and then click **Fault Settings** to open the portal [Fault Settings Page](../esb-toolkit/fault-settings-page.md).</span></span>  
  
3.  <span data-ttu-id="16b06-111">監査オプションを変更するには、チェック ボックスをオン、 **AuditOptions**セクションの各イベントを監査します。</span><span class="sxs-lookup"><span data-stu-id="16b06-111">To change the auditing options, select the check boxes in the **AuditOptions** section for each event you want to audit.</span></span> <span data-ttu-id="16b06-112">使用可能なイベントは、エラーを再送信するときに、変更された設定の保存、編集、およびエラーの後に障害を正常に再送信が。</span><span class="sxs-lookup"><span data-stu-id="16b06-112">The available events are the saving of modified settings, successful resubmission of a fault after editing, and failure when resubmitting a fault.</span></span>