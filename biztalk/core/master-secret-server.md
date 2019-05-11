---
title: マスター シークレット サーバー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Master Secret server, about Master Secret server
- Master Secret server, SSO
- SSO, encryption key
- Master Secret server, encryption key
- SSO, Master Secret server
ms.assetid: 93685a19-6c27-45db-bfc1-957574362687
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1cc7cfdd23db46f574bf57ccc97ef5959391d0b
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531111"
---
# <a name="master-secret-server"></a><span data-ttu-id="ed3ba-102">マスタ シークレット サーバー</span><span class="sxs-lookup"><span data-stu-id="ed3ba-102">Master Secret Server</span></span>
<span data-ttu-id="ed3ba-103">マスター シークレット サーバーとは、マスター シークレット (暗号化キー) を格納するエンタープライズ シングル サインオン (SSO) サーバーです。</span><span class="sxs-lookup"><span data-stu-id="ed3ba-103">The master secret server is the Enterprise Single Sign-On (SSO) server that stores the master secret (encryption key).</span></span> <span data-ttu-id="ed3ba-104">マスター シークレット サーバーでは、SSO 管理者の要求時に、マスター シークレットが生成されます。</span><span class="sxs-lookup"><span data-stu-id="ed3ba-104">The master secret server generates the master secret when an SSO administrator requests it.</span></span> <span data-ttu-id="ed3ba-105">マスター シークレット サーバーは、レジストリに暗号化されたマスタ シークレットを格納します。</span><span class="sxs-lookup"><span data-stu-id="ed3ba-105">The master secret server stores the encrypted master secret in the registry.</span></span> <span data-ttu-id="ed3ba-106">シングル サインオン管理者だけは、マスター シークレットにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ed3ba-106">Only Single Sign-On administrators can access the master secret.</span></span>  
  
 <span data-ttu-id="ed3ba-107">他のシングル サインオン サーバーでは、マスター シークレットが変更されたかどうかを 30 秒間隔を確認します。</span><span class="sxs-lookup"><span data-stu-id="ed3ba-107">The other Single Sign-On servers check every 30 seconds to see whether the master secret has changed.</span></span> <span data-ttu-id="ed3ba-108">安全に; 読み取り、それが変更された場合それ以外の場合、マスター シークレットが既にキャッシュ メモリの使用を続けます。</span><span class="sxs-lookup"><span data-stu-id="ed3ba-108">If it has changed, they read it securely; otherwise, they continue to use the master secret they already have cached in memory.</span></span> <span data-ttu-id="ed3ba-109">SSO サービスでは、マスター シークレットを使用して暗号化およびユーザーの資格情報の暗号化を解除します。</span><span class="sxs-lookup"><span data-stu-id="ed3ba-109">The SSO service uses the master secret to encrypt and decrypt the user credentials.</span></span>  
  
 <span data-ttu-id="ed3ba-110">まで、SSO 管理者がマスタ シークレット サーバーを構成し、マスター シークレットが生成されます、SSO システムを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="ed3ba-110">You cannot use the SSO system until an SSO administrator configures the master secret server and generates the master secret.</span></span> <span data-ttu-id="ed3ba-111">マスター シークレット サーバーは、構成中にマスター シークレットを生成します。</span><span class="sxs-lookup"><span data-stu-id="ed3ba-111">The master secret server generates the master secret during configuration.</span></span> <span data-ttu-id="ed3ba-112">SSO 管理者だけでは、マスター シークレットを生成できます。</span><span class="sxs-lookup"><span data-stu-id="ed3ba-112">Only SSO administrators can generate the master secret.</span></span> <span data-ttu-id="ed3ba-113">SSO 管理者は、アプリケーションで SSO サービスを使用前に、マスター シークレット サーバーと SSO データベースを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed3ba-113">An SSO administrator must configure the master secret server and the SSO database before an application can use the SSO service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ed3ba-114">マスター シークレットを生成した後バックアップし、セキュリティで保護された場所に保管することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ed3ba-114">After you generate the master secret, it is strongly recommended that you back it up and store it in a secure location.</span></span>  
  
 <span data-ttu-id="ed3ba-115">SSO 管理者は、マスター シークレットを再生成する必要がある、たとえば、SSO 管理者がマスタ シークレットを定期的に、変更する必要がある場合、マスタ シークレット サーバーを格納両方新旧のマスター シークレットします。</span><span class="sxs-lookup"><span data-stu-id="ed3ba-115">When an SSO administrator needs to regenerate the master secret, for example, if the SSO administrator wants to change the master secret periodically, the master secret server stores both the old and new master secret.</span></span> <span data-ttu-id="ed3ba-116">マスタ シークレット サーバーが、すべてのマッピングが、古いマスタ シークレットを使用して復号化し、新しいマスター シークレットを使用してそれらを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="ed3ba-116">The master secret server then goes through all the mappings, decrypts them using the old master secret, and encrypts them again using the new master secret.</span></span>  
  
 <span data-ttu-id="ed3ba-117">マスター シークレット サーバーが失敗した場合は、既に実行されているすべてのランタイム操作を実行するには引き続きが SSO サーバーでは、新しい資格情報を暗号化できません。</span><span class="sxs-lookup"><span data-stu-id="ed3ba-117">If the master secret server fails, all runtime operations already running will continue to run, but SSO servers will not be able to encrypt new credentials.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ed3ba-118">SSO システムに 1 つだけのマスター シークレット サーバーがあります。</span><span class="sxs-lookup"><span data-stu-id="ed3ba-118">There can be only one master secret server in your SSO system.</span></span> <span data-ttu-id="ed3ba-119">そのため、マスタ シークレット サーバーのクラスターを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ed3ba-119">Therefore, it is strongly recommended you cluster the master secret server.</span></span> <span data-ttu-id="ed3ba-120">詳細については、次を参照してください。[マスター シークレット サーバーをクラスター化する方法](../core/how-to-cluster-the-master-secret-server1.md)します。</span><span class="sxs-lookup"><span data-stu-id="ed3ba-120">For more information, see [How to Cluster the Master Secret Server](../core/how-to-cluster-the-master-secret-server1.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed3ba-121">参照</span><span class="sxs-lookup"><span data-stu-id="ed3ba-121">See Also</span></span>  
 [<span data-ttu-id="ed3ba-122">SSO の使用</span><span class="sxs-lookup"><span data-stu-id="ed3ba-122">Using SSO</span></span>](../core/using-sso.md)