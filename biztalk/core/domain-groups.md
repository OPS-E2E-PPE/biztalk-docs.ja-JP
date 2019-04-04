---
title: ドメイン グループ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9adc090e-e18c-46b6-b985-49b200d42966
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2944ce83df75ed724c9a7acafeee119b40cacafb
ms.sourcegitcommit: 7b64c823fa8d7fa8b10b163613311be69b861017
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39625870"
---
# <a name="domain-groups-in-biztalk"></a><span data-ttu-id="751eb-102">BizTalk 内のドメイン グループ</span><span class="sxs-lookup"><span data-stu-id="751eb-102">Domain Groups in BizTalk</span></span>
<span data-ttu-id="751eb-103">また、ドメイン グループ アカウントとドメイン ユーザー アカウントは、単一および複数の両方のコンピュータ構成でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="751eb-103">BizTalk Server supports domain group and user accounts in both single and multiple computer configurations.</span></span> <span data-ttu-id="751eb-104">複数コンピュータ構成の場合、このセクション、およびインストール ガイドの「マルチサーバー環境に関する注意点 (Considerations for Multiserver Environments)」で示す要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="751eb-104">For multiple computer configurations, you must observe the requirements provided in this section and in the Considerations for Multiserver Environments in the Installation Guide.</span></span> <span data-ttu-id="751eb-105">詳細については、、[インストールの概要](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="751eb-105">For more information, see the [installation overview](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="751eb-106">アンインストールの準備</span><span class="sxs-lookup"><span data-stu-id="751eb-106">Before you begin</span></span>
-   <span data-ttu-id="751eb-107">BizTalk Server の構成にドメイン グループを使用する場合は、BizTalk Server を構成する前に、グループを手動で作成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="751eb-107">If you use domain groups for your BizTalk Server configuration, you must manually create the groups before you configure BizTalk Server.</span></span> <span data-ttu-id="751eb-108">構成マネージャーでは、ドメイン グループを作成できません。</span><span class="sxs-lookup"><span data-stu-id="751eb-108">The Configuration Manager cannot create domain groups.</span></span>  
  
-   <span data-ttu-id="751eb-109">ドメイン グループやユーザー アカウントを作成した後でグループ所属団体に従って、適切なグループにユーザー アカウントを追加[Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="751eb-109">After creating domain groups and/or user accounts, add user accounts to the proper groups according to the group affiliations in [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="751eb-110">使用 **\<DomainName\>\\< ユーザー名\>** in Configuration Manager のドメイン アカウント情報を指定する場合。</span><span class="sxs-lookup"><span data-stu-id="751eb-110">Use **\<DomainName\>\\<UserName\>** when specifying domain account information in the Configuration Manager.</span></span>  
  
-   <span data-ttu-id="751eb-111">BizTalk Server では、すべてのクラスタリング シナリオに対応するドメイン アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="751eb-111">BizTalk Server requires domain accounts for all clustering scenarios.</span></span> <span data-ttu-id="751eb-112">クラスタ化された SQL Server やクラスタ化された SSO サーバー (マスタ シークレット サーバー) で、ローカル アカウントを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="751eb-112">You cannot use local accounts with clustered SQL Server or clustered SSO Server (master secret server).</span></span>  
  
-   <span data-ttu-id="751eb-113">BizTalk Server をインストールおよび構成する管理者は、SSO 管理者 (マスタ シークレット サーバーを構成する場合のみ)、ローカル管理者、sysadmin SQL Server ロール、OLAP 管理者といったグループのメンバである必要があります。</span><span class="sxs-lookup"><span data-stu-id="751eb-113">The administrator installing and configuring BizTalk Server must be a member of the following groups: SSO Administrators (only when configuring the master secret server); local Administrators; sysadmin SQL Server role; OLAP Administrators.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="751eb-114">SSO 管理者と SSO 関連管理者の構成中にドメイン グループを指定し、その操作を行うための十分な権限がある場合、ドメイン グループは自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="751eb-114">You can create the domain group automatically if you specify a domain group during configuration for the SSO Administrators and SSO Affiliate Administrators, and you have sufficient privileges.</span></span> <span data-ttu-id="751eb-115">十分な権限がない場合は、これらのドメイン グループが既に存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="751eb-115">If you do not have sufficient privileges, ensure that these groups already exist.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="751eb-116">参照</span><span class="sxs-lookup"><span data-stu-id="751eb-116">See Also</span></span>  
 <span data-ttu-id="751eb-117">[ローカル グループ](../core/local-groups.md) </span><span class="sxs-lookup"><span data-stu-id="751eb-117">[Local Groups](../core/local-groups.md) </span></span>  
 <span data-ttu-id="751eb-118">[インストールの概要](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md) </span><span class="sxs-lookup"><span data-stu-id="751eb-118">[Installation Overview](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md) </span></span>  
 [<span data-ttu-id="751eb-119">BizTalk Server の Windows グループ アカウントとユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="751eb-119">Windows Groups and User Accounts in BizTalk Server</span></span>](../core/windows-groups-and-user-accounts-in-biztalk-server.md)
