---
title: "送信先システムを復元した後ログインの問題を解決する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e9232ca3-dadb-4b3c-8ec4-4e307c32d2e5
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e691e690552f6decb3eed5f55dd17295c21a4efd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="resolving-login-issues-after-restoring-the-destination-system"></a><span data-ttu-id="ca387-102">送信先システムを復元した後ログインの問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="ca387-102">Resolving Login Issues After Restoring the Destination System</span></span>
<span data-ttu-id="ca387-103">ソース システムの構成によっては配置時に、「不明」なユーザーを解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca387-103">Depending on how the source system was configured during deployment, "orphaned" users may need to be resolved.</span></span> <span data-ttu-id="ca387-104">孤立したデータベース ユーザーは、対応するセキュリティを持たないユーザーのログイン[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ca387-104">An orphaned database user is a user who does not have a corresponding security login in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span> <span data-ttu-id="ca387-105">システム オンラインを使用して、取り込む前にこれらのユーザーの対応するログインを作成、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] SQL Management Studio (で**セキュリティ**、**ログイン**)。</span><span class="sxs-lookup"><span data-stu-id="ca387-105">Create corresponding logins for these users before bringing the system online using the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] SQL Management Studio (in **Security**, **Logins**).</span></span> <span data-ttu-id="ca387-106">任意の時点では、これらのログインを作成することができますが、それらを作成することをお勧めとき[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ログ配布を構成します。</span><span class="sxs-lookup"><span data-stu-id="ca387-106">You can create these logins at any point, but we recommend that you create them when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping is configured.</span></span>  
  
 <span data-ttu-id="ca387-107">作成されたログインが Windows アカウントとグループに対応する際に使用される[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と手動で作成され、いずれかで使用する任意のログインに、ソース システム上に構成された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-ロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="ca387-107">The logins that are created should correspond to the Windows accounts and groups that were used when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] was configured on the source system and to any logins that were manually created and used in any [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-created role.</span></span> <span data-ttu-id="ca387-108">ローカル Windows アカウントにこれらのログインが対応してまたはグループ、アカウントおよびグループ必要がありますまず前に作成するログインを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="ca387-108">If these logins correspond to local Windows accounts or groups, the accounts and groups must first be created before the login can be added.</span></span> <span data-ttu-id="ca387-109">BizTalk server のコンピューター名が変更されていない場合は、ローカル アカウントやグループのログインに関連付けられているユーザーを解決します。</span><span class="sxs-lookup"><span data-stu-id="ca387-109">If the computer name for the BizTalk server is not changed, then resolve the users associated with the logins for the local accounts and groups.</span></span>  
  
 <span data-ttu-id="ca387-110">構成するときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ログ配布、Microsoft サポート技術情報の記事 918992 の手順に従って[SQL Server 2005 のインスタンスと SQL Server 2008 の間で、ログインおよびパスワードを転送する方法](http://go.microsoft.com/fwlink/?LinkId=157143)(http://go.microsoft.com/fwlink/ しますか。LinkId = 157143) 移行先サーバーに必要なログインを追加するスクリプトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ca387-110">When configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping, follow the steps in Microsoft Knowledge Base Article 918992 [How to transfer the logins and the passwords between instances of SQL Server 2005 and SQL Server 2008](http://go.microsoft.com/fwlink/?LinkId=157143) (http://go.microsoft.com/fwlink/?LinkId=157143) to create a script that will add the necessary logins to the destination server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca387-111">参照</span><span class="sxs-lookup"><span data-stu-id="ca387-111">See Also</span></span>  
 [<span data-ttu-id="ca387-112">ログ配布のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="ca387-112">Troubleshooting Log Shipping</span></span>](../technical-guides/troubleshooting-log-shipping.md)