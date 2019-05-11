---
title: アラート キューのオプションと通知の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f78afbf9-6e27-4887-8424-f265fbd8448a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0938ceed9adcf117bcc54433eff1e9d7cd06ab8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302122"
---
# <a name="configuring-alert-queue-options-and-notifications"></a><span data-ttu-id="bd280-102">アラート キューのオプションと通知の構成</span><span class="sxs-lookup"><span data-stu-id="bd280-102">Configuring Alert Queue Options and Notifications</span></span>
<span data-ttu-id="bd280-103">ESB 管理ポータルでは、ポータルから、エラー メッセージが到着し、ESB の通知サービスを使用してキューにし、アラートにサブスクライブするユーザーにアラート通知を送信、アラートを生成するのに、ESB アラート サービスを使用します。</span><span class="sxs-lookup"><span data-stu-id="bd280-103">The ESB Management Portal uses the ESB Alert Service to generate alerts as fault messages arrive at the portal, and it uses the ESB Notification Service to queue and send alert notifications to users that subscribe to alerts.</span></span> <span data-ttu-id="bd280-104">ESB 管理ポータルでこれらのサービスによって使用される設定を編集することができます。</span><span class="sxs-lookup"><span data-stu-id="bd280-104">You can edit the settings used by these services in the ESB Management Portal.</span></span>  
  
### <a name="to-configure-the-settings-for-the-esb-alert-service"></a><span data-ttu-id="bd280-105">ESB アラート サービスの設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="bd280-105">To configure the settings for the ESB Alert Service</span></span>  
  
1.  <span data-ttu-id="bd280-106">(ポータル管理者の自動的にメンバー)、Microsoft BizTalk Server 管理者アカウント グループのメンバーであるアカウントを使用してポータルにログオンすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bd280-106">Ensure that you log on to the portal using an account that is a member of the Microsoft BizTalk Server Administrators account group (of which portal administrators are automatically a member).</span></span>  
  
2.  <span data-ttu-id="bd280-107">をポイント、**管理者**ポータルのメイン メニューで、タブをクリックして**フォールト設定**ポータルを開く[エラー設定ページ](../esb-toolkit/fault-settings-page.md)します。</span><span class="sxs-lookup"><span data-stu-id="bd280-107">Point to the **Admin** tab on the portal main menu, and then click **Fault Settings** to open the portal [Fault Settings Page](../esb-toolkit/fault-settings-page.md).</span></span>  
  
3.  <span data-ttu-id="bd280-108">**アラート キュー オプション**セクション、オンまたはオフ、 **Queue サービスのアラートを有効にする**を有効にするか、サービスを無効にする チェック ボックス。</span><span class="sxs-lookup"><span data-stu-id="bd280-108">In the **Alert Queue Options** section, select or clear the **Enable Alert Queue Service** check box to enable or disable the service.</span></span>  
  
4.  <span data-ttu-id="bd280-109">サービスを有効にした場合、要件に合わせて、残りのコントロール内の値を編集します。</span><span class="sxs-lookup"><span data-stu-id="bd280-109">If you enable the service, edit the values in the remaining controls to suit our requirements.</span></span> <span data-ttu-id="bd280-110">サービスは、LDAP (ライトウェイト ディレクトリ アクセス プロトコル) の適切な接続文字列を指定する必要がありますので、Microsoft Active Directory と対話します。</span><span class="sxs-lookup"><span data-stu-id="bd280-110">The service interacts with Microsoft Active Directory, so you must specify the appropriate LDAP (Lightweight Directory Access Protocol) connection string.</span></span> <span data-ttu-id="bd280-111">バッチ サイズのキューおよびポーリング間隔を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="bd280-111">You can also specify the queue batch size and polling interval.</span></span>  
  
5.  <span data-ttu-id="bd280-112">クリックして**保存**新しい設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="bd280-112">Click **Save** to save the new settings.</span></span>  
  
### <a name="to-configure-the-settings-for-the-esb-alert-email-notification-service"></a><span data-ttu-id="bd280-113">ESB アラート電子メール通知サービスの設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="bd280-113">To configure the settings for the ESB Alert Email Notification service</span></span>  
  
1.  <span data-ttu-id="bd280-114">(ポータル管理者の自動的にメンバー)、BizTalk Server 管理者アカウント グループのメンバーであるアカウントを使用してポータルにログオンすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bd280-114">Ensure that you log on to the portal using an account that is a member of the BizTalk Server Administrators account group (of which portal administrators are automatically a member).</span></span>  
  
2.  <span data-ttu-id="bd280-115">をポイント、**管理者**ポータルのメイン メニューで、タブをクリックして**フォールト設定**ポータルを開く[エラー設定ページ](../esb-toolkit/fault-settings-page.md)します。</span><span class="sxs-lookup"><span data-stu-id="bd280-115">Point to the **Admin** tab on the portal main menu, and then click **Fault Settings** to open the portal [Fault Settings Page](../esb-toolkit/fault-settings-page.md).</span></span>  
  
3.  <span data-ttu-id="bd280-116">**アラートの電子メール オプション**セクション、オンまたはオフ、**アラートの電子メール サービスを有効にする**チェック ボックスを有効または、サービスを無効にします。</span><span class="sxs-lookup"><span data-stu-id="bd280-116">In the **Alert Email Options** section, select or clear the **Enable Alert Email Service** check box to enable or disable the service.</span></span>  
  
4.  <span data-ttu-id="bd280-117">サービスを有効にした場合、要件に合わせて、残りのコントロール内の値を編集します。</span><span class="sxs-lookup"><span data-stu-id="bd280-117">If you enable the service, edit the values in the remaining controls to suit our requirements.</span></span> <span data-ttu-id="bd280-118">電子メール サーバー名と「差出人」アドレス指定、必要に応じて、ポーリング間隔とバッチ サイズを変更し、サービスが使用する拡張可能なスタイル シート言語変換 (XSLT) ファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="bd280-118">Specify the e-mail server name and the "from" address, change the polling interval and batch size as required, and specify the path to Extensible Stylesheet Language Transformations (XSLT) files that the service uses.</span></span>  
  
5.  <span data-ttu-id="bd280-119">クリックして**保存**新しい設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="bd280-119">Click **Save** to save the new settings.</span></span>