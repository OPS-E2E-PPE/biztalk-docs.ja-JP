---
title: "警告キュー オプションおよび通知の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f78afbf9-6e27-4887-8424-f265fbd8448a
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 914af88b989c73444e16acedf43b9a236897859d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-alert-queue-options-and-notifications"></a><span data-ttu-id="3c0f5-102">警告キュー オプションの構成と通知</span><span class="sxs-lookup"><span data-stu-id="3c0f5-102">Configuring Alert Queue Options and Notifications</span></span>
<span data-ttu-id="3c0f5-103">ESB の管理ポータルでは、アラートを生成するようにキューに置き、アラートにサブスクライブするユーザーに、アラート通知を送信、ESB Notification Service を使用して、ポータルにエラー メッセージが到着 ESB Alert サービスを使用します。</span><span class="sxs-lookup"><span data-stu-id="3c0f5-103">The ESB Management Portal uses the ESB Alert Service to generate alerts as fault messages arrive at the portal, and it uses the ESB Notification Service to queue and send alert notifications to users that subscribe to alerts.</span></span> <span data-ttu-id="3c0f5-104">ESB の管理ポータルでこれらのサービスで使用する設定を編集することができます。</span><span class="sxs-lookup"><span data-stu-id="3c0f5-104">You can edit the settings used by these services in the ESB Management Portal.</span></span>  
  
### <a name="to-configure-the-settings-for-the-esb-alert-service"></a><span data-ttu-id="3c0f5-105">ESB アラート サービスの設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="3c0f5-105">To configure the settings for the ESB Alert Service</span></span>  
  
1.  <span data-ttu-id="3c0f5-106">(そのうちポータル管理者は自動的にメンバー)、Microsoft BizTalk Server 管理者アカウント グループのメンバーであるアカウントを使用してポータルにログオンすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3c0f5-106">Ensure that you log on to the portal using an account that is a member of the Microsoft BizTalk Server Administrators account group (of which portal administrators are automatically a member).</span></span>  
  
2.  <span data-ttu-id="3c0f5-107">をポイント、 **Admin**ポータルのメイン メニュー タブをクリックして**フォールト設定**を開くには、ポータル[フォールトの設定 ページ](../esb-toolkit/fault-settings-page.md)です。</span><span class="sxs-lookup"><span data-stu-id="3c0f5-107">Point to the **Admin** tab on the portal main menu, and then click **Fault Settings** to open the portal [Fault Settings Page](../esb-toolkit/fault-settings-page.md).</span></span>  
  
3.  <span data-ttu-id="3c0f5-108">**キューのアラート オプション**セクションで、オンまたはオフ、**キュー サービスのアラートを有効にする**有効にするにまたはサービスを無効にする チェック ボックスです。</span><span class="sxs-lookup"><span data-stu-id="3c0f5-108">In the **Alert Queue Options** section, select or clear the **Enable Alert Queue Service** check box to enable or disable the service.</span></span>  
  
4.  <span data-ttu-id="3c0f5-109">サービスを有効にした場合は、この要件に合わせて他のコントロールの値を編集します。</span><span class="sxs-lookup"><span data-stu-id="3c0f5-109">If you enable the service, edit the values in the remaining controls to suit our requirements.</span></span> <span data-ttu-id="3c0f5-110">サービスは、適切な LDAP (ライトウェイト ディレクトリ アクセス プロトコル) 接続文字列を指定する必要がありますので、Microsoft Active Directory と対話します。</span><span class="sxs-lookup"><span data-stu-id="3c0f5-110">The service interacts with Microsoft Active Directory, so you must specify the appropriate LDAP (Lightweight Directory Access Protocol) connection string.</span></span> <span data-ttu-id="3c0f5-111">キュー バッチ サイズとポーリング間隔を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="3c0f5-111">You can also specify the queue batch size and polling interval.</span></span>  
  
5.  <span data-ttu-id="3c0f5-112">をクリックして**保存**新しい設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="3c0f5-112">Click **Save** to save the new settings.</span></span>  
  
### <a name="to-configure-the-settings-for-the-esb-alert-email-notification-service"></a><span data-ttu-id="3c0f5-113">ESB アラートの電子メール通知サービスの設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="3c0f5-113">To configure the settings for the ESB Alert Email Notification service</span></span>  
  
1.  <span data-ttu-id="3c0f5-114">(そのうちポータル管理者は自動的にメンバー)、BizTalk Server 管理者アカウント グループのメンバーであるアカウントを使用してポータルにログオンすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3c0f5-114">Ensure that you log on to the portal using an account that is a member of the BizTalk Server Administrators account group (of which portal administrators are automatically a member).</span></span>  
  
2.  <span data-ttu-id="3c0f5-115">をポイント、 **Admin**ポータルのメイン メニュー タブをクリックして**フォールト設定**を開くには、ポータル[フォールトの設定 ページ](../esb-toolkit/fault-settings-page.md)です。</span><span class="sxs-lookup"><span data-stu-id="3c0f5-115">Point to the **Admin** tab on the portal main menu, and then click **Fault Settings** to open the portal [Fault Settings Page](../esb-toolkit/fault-settings-page.md).</span></span>  
  
3.  <span data-ttu-id="3c0f5-116">**アラートの電子メール オプション**セクションで、オンまたはオフ、**アラートの電子メール サービスを有効にする**有効にするにまたはサービスを無効にする チェック ボックスです。</span><span class="sxs-lookup"><span data-stu-id="3c0f5-116">In the **Alert Email Options** section, select or clear the **Enable Alert Email Service** check box to enable or disable the service.</span></span>  
  
4.  <span data-ttu-id="3c0f5-117">サービスを有効にした場合は、この要件に合わせて他のコントロールの値を編集します。</span><span class="sxs-lookup"><span data-stu-id="3c0f5-117">If you enable the service, edit the values in the remaining controls to suit our requirements.</span></span> <span data-ttu-id="3c0f5-118">電子メール サーバー名と「差出人」アドレスを指定、必要に応じて、ポーリング間隔とバッチ サイズを変更し、サービスで使用される XSLT Extensible Stylesheet Language Transformations () ファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="3c0f5-118">Specify the e-mail server name and the "from" address, change the polling interval and batch size as required, and specify the path to Extensible Stylesheet Language Transformations (XSLT) files that the service uses.</span></span>  
  
5.  <span data-ttu-id="3c0f5-119">をクリックして**保存**新しい設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="3c0f5-119">Click **Save** to save the new settings.</span></span>