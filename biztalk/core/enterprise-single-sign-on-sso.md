---
title: エンタープライズ シングル サインオン (SSO) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, about SSO
- SSO
ms.assetid: beab96f7-f026-4ae1-8462-a165ad76bbec
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1dee56153e9eca7112ac0323bbfd604c3d062e86
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349286"
---
# <a name="enterprise-single-sign-on-sso"></a><span data-ttu-id="7a537-102">エンタープライズ シングル サインオン (SSO)</span><span class="sxs-lookup"><span data-stu-id="7a537-102">Enterprise Single Sign-On (SSO)</span></span>
<span data-ttu-id="7a537-103">エンタープライズ シングル サインオン (SSO) では、暗号化されたユーザー資格情報をローカルおよびドメインの境界など、ネットワークの境界を格納および転送するサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="7a537-103">Enterprise Single Sign-On (SSO) provides services to store and transmit encrypted user credentials across local and network boundaries, including domain boundaries.</span></span> <span data-ttu-id="7a537-104">SSO は、SSO データベースの資格情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="7a537-104">SSO stores the credentials in the SSO database.</span></span> <span data-ttu-id="7a537-105">SSO は、汎用的な 1 つのシングル サインオン ソリューションを提供するためのミドルウェア アプリケーションとカスタム アダプターは安全に格納し、環境全体でユーザーの資格情報を送信する SSO を活用できます。</span><span class="sxs-lookup"><span data-stu-id="7a537-105">Because SSO provides a generic single sign-on solution, middleware applications and custom adapters can leverage SSO to securely store and transmit user credentials across the environment.</span></span> <span data-ttu-id="7a537-106">エンドユーザーは、さまざまなアプリケーションのさまざまな資格情報を記憶する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7a537-106">End users do not have to remember different credentials for different applications.</span></span>  
  
 <span data-ttu-id="7a537-107">シングル サインオン システムは、SSO データベースをマスター シークレット サーバー、および 1 つ以上のシングル サインオン サーバーで構成されます。</span><span class="sxs-lookup"><span data-stu-id="7a537-107">The Single Sign-On system consists of an SSO database, a master secret server, and one or more Single Sign-On servers.</span></span>  
  
 <span data-ttu-id="7a537-108">SSO システムに含まれる*関連アプリケーション*管理者を定義します。</span><span class="sxs-lookup"><span data-stu-id="7a537-108">The SSO system contains *affiliate applications* that an administrator defines.</span></span> <span data-ttu-id="7a537-109">*関連アプリケーション*システムまたはサブシステムなど、ホスト、バックエンド システム、または基幹業務アプリケーションを表す論理エンティティを接続するエンタープライズ シングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="7a537-109">An *affiliate application* is a logical entity that represents a system or sub-system such as a host, back-end system, or line of business application to which you are connecting using Enterprise Single Sign-On.</span></span> <span data-ttu-id="7a537-110">各関連アプリケーションが複数のユーザー マッピングたとえば、Active Directory でユーザーの資格情報と、対応する RACF 資格情報の間のマッピングがあります。</span><span class="sxs-lookup"><span data-stu-id="7a537-110">Each affiliate application has multiple user mappings; for example, it has the mappings between the credentials for a user in Active Directory and their corresponding RACF credentials.</span></span>  
  
 <span data-ttu-id="7a537-111">SSO データベースは、SQL Server データベースとすべてのすべての関連アプリケーションに暗号化されたユーザー資格情報、関連アプリケーションに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="7a537-111">The SSO database is the SQL Server database that stores the information about the affiliate applications, as well as all of the encrypted user credentials to all the affiliate applications.</span></span>  
  
 <span data-ttu-id="7a537-112">*マスター シークレット サーバー*はマスター シークレットを格納するエンタープライズ シングル サインオン サーバーです。</span><span class="sxs-lookup"><span data-stu-id="7a537-112">The *master secret server* is the Enterprise Single Sign-On server that stores the master secret.</span></span> <span data-ttu-id="7a537-113">すべての他のシングル サインオン サーバー システムでは、マスター シークレット サーバーからマスター シークレットを取得します。</span><span class="sxs-lookup"><span data-stu-id="7a537-113">All other Single Sign-On servers in the system get the master secret from the master secret server.</span></span>  
  
 <span data-ttu-id="7a537-114">SSO システムには、1 つまたは複数の SSO サーバーも含まれています。</span><span class="sxs-lookup"><span data-stu-id="7a537-114">The SSO system also contains one or more SSO Servers.</span></span> <span data-ttu-id="7a537-115">これらのサーバーでは、Microsoft Windows とバックエンド資格情報の間のマッピングを行うし、SSO データベース内の資格情報を検索します。</span><span class="sxs-lookup"><span data-stu-id="7a537-115">These servers do the mapping between the Microsoft Windows and back-end credentials, and look up the credentials in the SSO database.</span></span> <span data-ttu-id="7a537-116">管理者では、それらを使用して、SSO システムを管理します。</span><span class="sxs-lookup"><span data-stu-id="7a537-116">Administrators use them to maintain the SSO system.</span></span>  
  
 <span data-ttu-id="7a537-117">エンタープライズ シングル サインオンで完全な検索ではさらに次を参照してください。[理解 SSO](../core/understanding-sso.md)します。</span><span class="sxs-lookup"><span data-stu-id="7a537-117">For more a complete look at Enterprise Single Sign-On, see [Understanding SSO](../core/understanding-sso.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a537-118">参照</span><span class="sxs-lookup"><span data-stu-id="7a537-118">See Also</span></span>  
 [<span data-ttu-id="7a537-119">ランタイム アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="7a537-119">Runtime Architecture</span></span>](../core/runtime-architecture.md)