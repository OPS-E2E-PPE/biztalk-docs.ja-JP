---
title: エンタープライズ シングル サインオン (SSO) |Microsoft ドキュメント
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
ms.openlocfilehash: 2f6cbc5f514d13cd8457cd9417be5ea5b78408e6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240154"
---
# <a name="enterprise-single-sign-on-sso"></a><span data-ttu-id="bbbdb-102">エンタープライズ シングル サインオン (SSO)</span><span class="sxs-lookup"><span data-stu-id="bbbdb-102">Enterprise Single Sign-On (SSO)</span></span>
<span data-ttu-id="bbbdb-103">エンタープライズ シングル サインオン (SSO) には、ローカルおよびネットワークの境界 (ドメインの境界を含む) の間で暗号化されたユーザー資格情報を格納および転送するサービスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="bbbdb-103">Enterprise Single Sign-On (SSO) provides services to store and transmit encrypted user credentials across local and network boundaries, including domain boundaries.</span></span> <span data-ttu-id="bbbdb-104">SSO では SSO データベースに資格情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="bbbdb-104">SSO stores the credentials in the SSO database.</span></span> <span data-ttu-id="bbbdb-105">SSO には汎用のシングル サインオン ソリューションが用意されているので、ミドルウェア アプリケーションとカスタム アダプターが SSO を活用して環境間でのユーザー資格情報の格納および転送を安全に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="bbbdb-105">Because SSO provides a generic single sign-on solution, middleware applications and custom adapters can leverage SSO to securely store and transmit user credentials across the environment.</span></span> <span data-ttu-id="bbbdb-106">エンド ユーザーは、アプリケーションごとに個別の資格情報を覚えておく必要がありません。</span><span class="sxs-lookup"><span data-stu-id="bbbdb-106">End users do not have to remember different credentials for different applications.</span></span>  
  
 <span data-ttu-id="bbbdb-107">シングル サインオン システムは、SSO データベース (1 つ)、マスター シークレット サーバー (1 つ)、およびシングル サインオン サーバー (複数可) で構成されます。</span><span class="sxs-lookup"><span data-stu-id="bbbdb-107">The Single Sign-On system consists of an SSO database, a master secret server, and one or more Single Sign-On servers.</span></span>  
  
 <span data-ttu-id="bbbdb-108">SSO システムに含まれる*関連アプリケーション*管理者を定義します。</span><span class="sxs-lookup"><span data-stu-id="bbbdb-108">The SSO system contains *affiliate applications* that an administrator defines.</span></span> <span data-ttu-id="bbbdb-109">*関連アプリケーション*システムまたはサブシステム ホスト、バックエンド システム、基幹業務アプリケーションなどを表す論理エンティティを接続するエンタープライズ シングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="bbbdb-109">An *affiliate application* is a logical entity that represents a system or sub-system such as a host, back-end system, or line of business application to which you are connecting using Enterprise Single Sign-On.</span></span> <span data-ttu-id="bbbdb-110">各関連アプリケーションには複数のユーザー マッピングがあります。たとえば、Active Directory 内のユーザーの資格情報とそれに対応する RACF 資格情報のマッピングがあります。</span><span class="sxs-lookup"><span data-stu-id="bbbdb-110">Each affiliate application has multiple user mappings; for example, it has the mappings between the credentials for a user in Active Directory and their corresponding RACF credentials.</span></span>  
  
 <span data-ttu-id="bbbdb-111">SSO データベースは、SQL Server データベースです。関連アプリケーションに関する情報と、すべての関連アプリケーションへの暗号化されたすべてのユーザー資格情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="bbbdb-111">The SSO database is the SQL Server database that stores the information about the affiliate applications, as well as all of the encrypted user credentials to all the affiliate applications.</span></span>  
  
 <span data-ttu-id="bbbdb-112">*マスター シークレット サーバー*マスター シークレットを格納するエンタープライズ シングル サインオン サーバーです。</span><span class="sxs-lookup"><span data-stu-id="bbbdb-112">The *master secret server* is the Enterprise Single Sign-On server that stores the master secret.</span></span> <span data-ttu-id="bbbdb-113">システム内のその他すべてのシングル サインオン サーバーでは、マスター シークレット サーバーからマスター シークレットを取得します。</span><span class="sxs-lookup"><span data-stu-id="bbbdb-113">All other Single Sign-On servers in the system get the master secret from the master secret server.</span></span>  
  
 <span data-ttu-id="bbbdb-114">また、SSO システムには 1 台以上の SSO サーバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bbbdb-114">The SSO system also contains one or more SSO Servers.</span></span> <span data-ttu-id="bbbdb-115">SSO サーバーでは、Microsoft Windows 資格情報とバックエンド資格情報のマッピングが行われ、SSO データベース内の資格情報が検索されます。</span><span class="sxs-lookup"><span data-stu-id="bbbdb-115">These servers do the mapping between the Microsoft Windows and back-end credentials, and look up the credentials in the SSO database.</span></span> <span data-ttu-id="bbbdb-116">管理者はそれらの資格情報を使用して SSO システムを管理します。</span><span class="sxs-lookup"><span data-stu-id="bbbdb-116">Administrators use them to maintain the SSO system.</span></span>  
  
 <span data-ttu-id="bbbdb-117">エンタープライズ シングル サインオンで完全な場所ではより、次を参照してください。 [Understanding SSO](../core/understanding-sso.md)です。</span><span class="sxs-lookup"><span data-stu-id="bbbdb-117">For more a complete look at Enterprise Single Sign-On, see [Understanding SSO](../core/understanding-sso.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbbdb-118">参照</span><span class="sxs-lookup"><span data-stu-id="bbbdb-118">See Also</span></span>  
 [<span data-ttu-id="bbbdb-119">ランタイム アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="bbbdb-119">Runtime Architecture</span></span>](../core/runtime-architecture.md)