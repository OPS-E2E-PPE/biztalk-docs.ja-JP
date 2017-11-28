---
title: "マスター シークレット サーバー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Master Secret server, about Master Secret server
- Master Secret server, SSO
- SSO, encryption key
- Master Secret server, encryption key
- SSO, Master Secret server
ms.assetid: 93685a19-6c27-45db-bfc1-957574362687
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d02d5608546e86801bfc4a2281c42f902594e79
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="master-secret-server"></a><span data-ttu-id="2295d-102">マスタ シークレット サーバー</span><span class="sxs-lookup"><span data-stu-id="2295d-102">Master Secret Server</span></span>
<span data-ttu-id="2295d-103">マスタ シークレット サーバーは、マスタ シークレット (暗号化キー) を格納する、エンタープライズ シングル サインオン (SSO) サーバーです。</span><span class="sxs-lookup"><span data-stu-id="2295d-103">The master secret server is the Enterprise Single Sign-On (SSO) server that stores the master secret (encryption key).</span></span> <span data-ttu-id="2295d-104">マスタ シークレット サーバーでは、SSO 管理者からの要求に応じてマスタ シークレットを生成します。</span><span class="sxs-lookup"><span data-stu-id="2295d-104">The master secret server generates the master secret when an SSO administrator requests it.</span></span> <span data-ttu-id="2295d-105">また、暗号化されたマスタ シークレットをレジストリに格納します。</span><span class="sxs-lookup"><span data-stu-id="2295d-105">The master secret server stores the encrypted master secret in the registry.</span></span> <span data-ttu-id="2295d-106">マスタ シークレットにアクセスできるのは、シングル サインオン管理者だけです。</span><span class="sxs-lookup"><span data-stu-id="2295d-106">Only Single Sign-On administrators can access the master secret.</span></span>  
  
 <span data-ttu-id="2295d-107">その他のシングル サインオン サーバーでは、マスタ シークレットが変更されたかどうかを 30 分ごとに確認します。</span><span class="sxs-lookup"><span data-stu-id="2295d-107">The other Single Sign-On servers check every 30 seconds to see whether the master secret has changed.</span></span> <span data-ttu-id="2295d-108">変更されている場合、そのマスタ シークレットをセキュリティで保護して読み取ります。変更されていない場合は、既にメモリにキャッシュされているマスタ シークレットを引き続き使用します。</span><span class="sxs-lookup"><span data-stu-id="2295d-108">If it has changed, they read it securely; otherwise, they continue to use the master secret they already have cached in memory.</span></span> <span data-ttu-id="2295d-109">SSO サービスでは、マスタ シークレットを使用してユーザーの資格情報を暗号化および復号化します。</span><span class="sxs-lookup"><span data-stu-id="2295d-109">The SSO service uses the master secret to encrypt and decrypt the user credentials.</span></span>  
  
 <span data-ttu-id="2295d-110">SSO システムは、SSO 管理者がマスタ シークレット サーバーを構成し、マスタ シークレットを生成するまで使用できません。</span><span class="sxs-lookup"><span data-stu-id="2295d-110">You cannot use the SSO system until an SSO administrator configures the master secret server and generates the master secret.</span></span> <span data-ttu-id="2295d-111">マスタ シークレット サーバーでは、構成中にマスタ シークレットを生成します。</span><span class="sxs-lookup"><span data-stu-id="2295d-111">The master secret server generates the master secret during configuration.</span></span> <span data-ttu-id="2295d-112">マスタ シークレットを生成できるのは、SSO 管理者だけです。</span><span class="sxs-lookup"><span data-stu-id="2295d-112">Only SSO administrators can generate the master secret.</span></span> <span data-ttu-id="2295d-113">SSO 管理者は、アプリケーションで SSO サービスを使用する前に、マスタ シークレット サーバーと SSO データベースを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2295d-113">An SSO administrator must configure the master secret server and the SSO database before an application can use the SSO service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2295d-114">マスタ シークレットを生成したら、そのマスタ シークレットをバックアップし、セキュリティで保護された場所に格納しておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2295d-114">After you generate the master secret, it is strongly recommended that you back it up and store it in a secure location.</span></span>  
  
 <span data-ttu-id="2295d-115">SSO 管理者がマスタ シークレットを定期的に変更する場合など、SSO 管理者がマスタ シークレットを再生成する必要がある場合、マスタ シークレット サーバーには、新旧両方のマスタ シークレットが格納されます。</span><span class="sxs-lookup"><span data-stu-id="2295d-115">When an SSO administrator needs to regenerate the master secret, for example, if the SSO administrator wants to change the master secret periodically, the master secret server stores both the old and new master secret.</span></span> <span data-ttu-id="2295d-116">次に、マスタ シークレット サーバーでは、すべてのマッピングに対して、古いマスタ シークレットを使用して復号化を行い、新しいマスタ シークレットを使用して暗号化を行います。</span><span class="sxs-lookup"><span data-stu-id="2295d-116">The master secret server then goes through all the mappings, decrypts them using the old master secret, and encrypts them again using the new master secret.</span></span>  
  
 <span data-ttu-id="2295d-117">マスタ シークレット サーバーが失敗した場合、既に実行されているすべてのランタイム操作は引き続き実行されますが、SSO サーバーでは新しい資格情報を暗号化できません。</span><span class="sxs-lookup"><span data-stu-id="2295d-117">If the master secret server fails, all runtime operations already running will continue to run, but SSO servers will not be able to encrypt new credentials.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2295d-118">SSO システムに配置できるマスター シークレット サーバーは 1 台のみです。</span><span class="sxs-lookup"><span data-stu-id="2295d-118">There can be only one master secret server in your SSO system.</span></span> <span data-ttu-id="2295d-119">このため、マスタ シークレット サーバーをクラスタ化することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2295d-119">Therefore, it is strongly recommended you cluster the master secret server.</span></span> <span data-ttu-id="2295d-120">詳細については、次を参照してください。[マスター シークレット サーバーをクラスター化する方法](../core/how-to-cluster-the-master-secret-server1.md)です。</span><span class="sxs-lookup"><span data-stu-id="2295d-120">For more information, see [How to Cluster the Master Secret Server](../core/how-to-cluster-the-master-secret-server1.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2295d-121">参照</span><span class="sxs-lookup"><span data-stu-id="2295d-121">See Also</span></span>  
 [<span data-ttu-id="2295d-122">SSO の使用</span><span class="sxs-lookup"><span data-stu-id="2295d-122">Using SSO</span></span>](../core/using-sso.md)