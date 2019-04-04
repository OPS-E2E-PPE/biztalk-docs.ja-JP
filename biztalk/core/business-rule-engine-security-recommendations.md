---
title: ビジネス ルール エンジンのセキュリティに関する推奨事項 |Microsoft Docs
ms.custom: ''
ms.date: 09/27/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, business rules
- Business Rules Framework, security
- business rules, security
ms.assetid: d5df1cd0-112a-4c72-b95d-cbcd1bc6a2c3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ca5506d8ed9acab63e32a4ec86b057a4b775b63
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752754"
---
# <a name="business-rule-engine-security-recommendations"></a><span data-ttu-id="c365b-102">ビジネス ルール エンジンのセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="c365b-102">Business Rule Engine Security Recommendations</span></span>
<span data-ttu-id="c365b-103">ビジネス ルール エンジンは、ビジネス ルール フレームワークのランタイム コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="c365b-103">The Business Rule Engine is the runtime component of the Business Rule Framework.</span></span> <span data-ttu-id="c365b-104">ビジネス ルール フレームワークを使用すると、非常に判読しやすく意味論的にも充実した宣言型のルールを、任意のビジネス オブジェクト (.NET コンポーネント)、XML ドキュメント、またはデータベース テーブルに接続することができます。</span><span class="sxs-lookup"><span data-stu-id="c365b-104">With the Business Rule Framework, you can connect highly readable, declarative, semantically rich rules to any business objects (.NET components), XML documents, or database tables.</span></span> <span data-ttu-id="c365b-105">ビジネス ルール フレームワークの詳細については、[を使用してビジネス ルールの作成と](../core/creating-and-using-business-rules.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c365b-105">For more information about the Business Rule Framework, see [Creating and Using Business Rules](../core/creating-and-using-business-rules.md).</span></span> <span data-ttu-id="c365b-106">ビジネス ルール エンジンの詳細については、[ルール エンジン](../core/rule-engine.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c365b-106">For more information about the Business Rule Engine, see [Rule Engine](../core/rule-engine.md).</span></span>  
  
 <span data-ttu-id="c365b-107">ビジネス ルール エンジンに対応する Windows ユーザー グループはなく、あるのは個別のアカウントのみです。</span><span class="sxs-lookup"><span data-stu-id="c365b-107">There are no Windows user groups for the Business Rule Engine, only individual accounts.</span></span> <span data-ttu-id="c365b-108">BizTalk Server では、2 種類の SQL Server ロールを使用して、ビジネス ルール エンジンへのアクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="c365b-108">BizTalk Server restricts access to the Business Rule Engine resources by using two SQL Server roles:</span></span>  
  
 <span data-ttu-id="c365b-109">RE_Admin_Users SQL Server ロールは、ビジネス ルール エンジンでルールの展開などの管理タスクを実行する必要があるユーザーのためのロールです。</span><span class="sxs-lookup"><span data-stu-id="c365b-109">The RE_Admin_Users SQL Server role is for users that need to perform administrative tasks in the Business Rule Engine, such as deploying rules.</span></span> <span data-ttu-id="c365b-110">RE_Admin_Users SQL Server ロールのメンバーには、BizTalk Server 管理者が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c365b-110">Members of the RE_Admin_Users SQL Server role include BizTalk administrators.</span></span>  
  
 <span data-ttu-id="c365b-111">RE_Host_Users グループは、ビジネス ルール エンジンを使用するその他すべてのユーザーのためのロールで、管理ユーザー権限を必要としないルールの読み取りや実行などのタスクを行うユーザーに適しています。</span><span class="sxs-lookup"><span data-stu-id="c365b-111">The RE_Host_Users group is for all other users of the Business Rule Engine that do not require administrative user rights, and perform tasks such as reading and executing rules.</span></span> <span data-ttu-id="c365b-112">RE_Host_Users ロールのメンバーには、BizTalk_Host_Users ロールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c365b-112">Members of the RE_Host_Users role include the BizTalk_Host_Users role.</span></span> <span data-ttu-id="c365b-113">SQL Server ロールを使用することで、BizTalk Server のアクセス許可とは別に、ビジネス ルール エンジンのアクセス許可を実装することができます。</span><span class="sxs-lookup"><span data-stu-id="c365b-113">You can use the SQL Server roles to implement permissions to the Business Rule Engine independent from the BizTalk Server permissions.</span></span> <span data-ttu-id="c365b-114">ビジネス ルール エンジンを使用するために必要な最小限のアクセス許可の詳細については、[最小セキュリティ ユーザー権限](../core/minimum-security-user-rights.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c365b-114">For more information about the minimum permission needed to use the Business Rule Engine, see [Minimum Security User Rights](../core/minimum-security-user-rights.md).</span></span> <span data-ttu-id="c365b-115">ビジネス ルール エンジンをセキュリティで保護して環境に展開するには、次のガイドラインに従うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c365b-115">It is recommended you follow these guidelines for securing and deploying the Business Rule Engine in your environment.</span></span>  
  
-   <span data-ttu-id="c365b-116">BizTalk Server は、更新サービスのインストール時のアカウントにサービスとしてログオンする権限を与え、そのアカウントをビジネス ルール エンジン データベースの RE_Host_Users SQL Server ロールに追加します。</span><span class="sxs-lookup"><span data-stu-id="c365b-116">BizTalk Server gives the account you used to install the update service logon as service rights and adds it to the RE_Host_Users SQL Server role on the Business Rule Engine database.</span></span> <span data-ttu-id="c365b-117">インストール時のアカウントが更新サービスの実行に使用するアカウントと同一でない場合は、RE_Host_Users SQL Server ロールからインストール アカウントを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c365b-117">If the account you use for installation is not the same you are going to use for running the update service, you must remove the installation account from the RE_Host_Users SQL Server role.</span></span>  

-   <span data-ttu-id="c365b-118">別の BizTalk ホスト サービス アカウントとして同じアカウントを使用しない場合も BizTalkMgmtDb、BizTalkMsgBoxDb で BTS_HOST_USERS をルール エンジンのサービス アカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="c365b-118">If you don't use the same account as another BizTalk host service account, also add the RuleEngine service account to BTS_HOST_USERS in BizTalkMgmtDb and BizTalkMsgBoxDb.</span></span>

-   <span data-ttu-id="c365b-119">更新サービス コンポーネントを使用する場合は、BizTalk ランタイム コンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c365b-119">If you use the Update service component, you must install it on all BizTalk runtime computers.</span></span> <span data-ttu-id="c365b-120">ルール エンジン データベースからルールを取得するために、更新サービスはサービスの呼び出し元の権限を借用します。</span><span class="sxs-lookup"><span data-stu-id="c365b-120">In order to retrieve a rule from the Rule Engine database, the update service impersonates the caller of the service.</span></span>  
  
-   <span data-ttu-id="c365b-121">既定では、ルール エンジンのアイテムに対するアクセス権のレベルはすべての BizTalk ホストで同一になっています。</span><span class="sxs-lookup"><span data-stu-id="c365b-121">By default, all BizTalk Hosts have the same level of access to rules engine artifacts.</span></span> <span data-ttu-id="c365b-122">セキュリティに関してホスト単位での区別はありません。</span><span class="sxs-lookup"><span data-stu-id="c365b-122">There is not per-host segregation of security.</span></span> <span data-ttu-id="c365b-123">ルール エンジンの API を使用することで、ポリシー単位のセキュリティを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="c365b-123">You can configure per-policy security by using the rule engine APIs.</span></span> <span data-ttu-id="c365b-124">ポリシーごとのセキュリティを構成する方法の詳細については、[ビジネス ルール フレームワークのセキュリティ](../core/business-rules-framework-security.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c365b-124">For more information about how to configure per-policy security, see [Business Rules Framework Security](../core/business-rules-framework-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c365b-125">参照</span><span class="sxs-lookup"><span data-stu-id="c365b-125">See Also</span></span>  
 [<span data-ttu-id="c365b-126">処理サーバーのポート</span><span class="sxs-lookup"><span data-stu-id="c365b-126">Ports for the Processing Servers</span></span>](../core/ports-for-the-processing-servers.md)
