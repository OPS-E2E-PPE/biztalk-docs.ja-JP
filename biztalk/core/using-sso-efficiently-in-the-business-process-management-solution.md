---
title: ビジネス プロセス管理ソリューションで SSO の効率的な使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, process management solutions
- SSO, configuration values
- caching, configuration values [SSO]
- SSO, caching
- process management solution tutorial, SSO
ms.assetid: 39fbc42d-caa4-4003-a13b-5cde578eb5e1
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99575e54b887124bfa4c33fc5257cd057ea818fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288522"
---
# <a name="using-sso-efficiently-in-the-business-process-management-solution"></a><span data-ttu-id="14c07-102">ビジネス プロセス管理ソリューションで SSO の効率的な使用</span><span class="sxs-lookup"><span data-stu-id="14c07-102">Using SSO Efficiently in the Business Process Management Solution</span></span>
<span data-ttu-id="14c07-103">サービス指向ソリューションと同様に、ビジネス プロセス管理ソリューションは、エンタープライズ シングル サインオン (SSO) を使用して、注文処理ステージの数などの構成値を保存します。</span><span class="sxs-lookup"><span data-stu-id="14c07-103">Like the Service Oriented solution, the Business Process Management solution uses Enterprise Single Sign-On (SSO) to store configuration values such as the number of order processing stages.</span></span> <span data-ttu-id="14c07-104">BizTalk がインストールされると存在するため、シークレット ストアを使用します。SSO は、値をすぐに使用できるように構成情報をキャッシュするので、データベース接続文字列やパスワードなどの情報を保護できます。</span><span class="sxs-lookup"><span data-stu-id="14c07-104">It uses the secret store because it is present whenever BizTalk is installed, SSO caches the configuration information so that the values are readily available, and it can protect information such as database connection strings and passwords.</span></span> <span data-ttu-id="14c07-105">これらのすべての理由により、SSO がバックエンド アプリケーションの接続管理に使用されていなくても、シークレット ストアは構成情報を保存する適切な場所です。</span><span class="sxs-lookup"><span data-stu-id="14c07-105">For all of these reasons, the secret store is a good place for the configuration information even if Single Sign-On weren't being used for managing connections to the backend applications.</span></span>  
  
 <span data-ttu-id="14c07-106">待機時間を減らすために、このソリューションでは構成値のローカル キャッシュが使用されます。</span><span class="sxs-lookup"><span data-stu-id="14c07-106">To reduce latency, the solution uses a local cache for the configuration values.</span></span> <span data-ttu-id="14c07-107">キャッシュは 5 分おきに更新されます。</span><span class="sxs-lookup"><span data-stu-id="14c07-107">The solution refreshes the cache every five minutes.</span></span>  
  
 <span data-ttu-id="14c07-108">このトピックでは、このソリューションで使用されるキャッシュ メカニズムについて説明します。</span><span class="sxs-lookup"><span data-stu-id="14c07-108">This topic describes the caching mechanism used by the solution.</span></span> <span data-ttu-id="14c07-109">このソリューションは、SSO キャッシュへのアプローチがサービス指向ソリューションと少し異なります。</span><span class="sxs-lookup"><span data-stu-id="14c07-109">This solution takes a slightly different approach to SSO caching than does the service oriented solution.</span></span> <span data-ttu-id="14c07-110">サービス指向のソリューションの説明では、SSO 値はキャッシュを参照してください[を使用して SSO の効率的なサービス指向ソリューションで](../core/using-sso-efficiently-in-the-service-oriented-solution.md)です。</span><span class="sxs-lookup"><span data-stu-id="14c07-110">For a description of how the service oriented solution caches SSO values, see [Using SSO Efficiently in the Service Oriented Solution](../core/using-sso-efficiently-in-the-service-oriented-solution.md).</span></span>  
  
## <a name="caching-configuration-values-locally"></a><span data-ttu-id="14c07-111">構成値のローカル キャッシュ</span><span class="sxs-lookup"><span data-stu-id="14c07-111">Caching Configuration Values Locally</span></span>  
 <span data-ttu-id="14c07-112">ビジネス プロセス管理ソリューションは、単一オブジェクトのプロパティを使用して、SSO 値にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="14c07-112">The business process management solution uses properties on a singleton object to provide access to the SSO values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="14c07-113">単一オブジェクトは 1 つのインスタンスだけを持つオブジェクトなので注意してください。</span><span class="sxs-lookup"><span data-stu-id="14c07-113">Recall that a singleton object is an object that can have only one instance.</span></span> <span data-ttu-id="14c07-114">単一オブジェクトと c# での作成に関する詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=58806](http://go.microsoft.com/fwlink/?LinkId=58806)です。</span><span class="sxs-lookup"><span data-stu-id="14c07-114">For more information about singleton objects and creating them in C#, see [http://go.microsoft.com/fwlink/?LinkId=58806](http://go.microsoft.com/fwlink/?LinkId=58806).</span></span>  
  
 <span data-ttu-id="14c07-115">ソリューションでは、オーケストレーションは最初シングルトン オブジェクトを取得し、オブジェクトのプロパティを使用して、値を参照します。</span><span class="sxs-lookup"><span data-stu-id="14c07-115">In the solution, an orchestration first retrieves the singleton object and then references the values through the object's properties.</span></span> <span data-ttu-id="14c07-116">コードをここでは、 **OrderManager**オーケストレーション。</span><span class="sxs-lookup"><span data-stu-id="14c07-116">Here is code from the **OrderManager** orchestration:</span></span>  
  
```  
configData = Microsoft.Samples.BizTalk.SouthridgeVideo.Utilities  
                .SsoConfigHelper.Singleton;  
numStages = configData.TotalStages;  
```  
  
 <span data-ttu-id="14c07-117">オーケストレーションを呼び出して、**シングルトン**メソッドを**SsoConfigHelper**オブジェクトの 1 つのコピーへのアクセスを取得するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="14c07-117">The orchestration calls the **Singleton** method on the **SsoConfigHelper** object to get access to the one copy of the object.</span></span> <span data-ttu-id="14c07-118">手の形でオブジェクトが、オーケストレーションが処理ステージの数を取得**TotalStages**です。</span><span class="sxs-lookup"><span data-stu-id="14c07-118">With the object in hand, the orchestration retrieves the number of processing stages, **TotalStages**.</span></span>  
  
 <span data-ttu-id="14c07-119">ソリューションに依存して、単一の作成の一般的な方法: コンス トラクターをプライベートにする、オブジェクトがそれ自体のインスタンスを作成して、プライベート変数に割り当てることと、メソッドまたはプロパティでは、その変数の値へのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="14c07-119">The solution follows a common method of creating a singleton: make the constructor private, have the object create an instance of itself and assign that to a private variable, and, through a method or property, provide access to the value of that variable.</span></span> <span data-ttu-id="14c07-120">**SsoConfigHelper**オブジェクト、プロパティを使用して**シングルトン**、それ自体の 1 つのコピーにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="14c07-120">The **SsoConfigHelper** object uses a property, **Singleton**, to provide access to the single copy of itself.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="14c07-121">**SsoConfigHelper**更新メカニズムを設定して、SSO のキャッシュから初期値を取得するオブジェクトで静的コンス トラクターを使用します。</span><span class="sxs-lookup"><span data-stu-id="14c07-121">The **SsoConfigHelper** object uses a static constructor to get the initial values from the SSO cache and to set up the refresh mechanism.</span></span> <span data-ttu-id="14c07-122">静的コンストラクタは呼び出せないので、単一オブジェクトのしくみは保持されます。</span><span class="sxs-lookup"><span data-stu-id="14c07-122">Because a static constructor cannot be called, it preserves the singleton design.</span></span> <span data-ttu-id="14c07-123">静的コンス トラクターの詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=59142](http://go.microsoft.com/fwlink/?LinkId=59142)です。</span><span class="sxs-lookup"><span data-stu-id="14c07-123">For more information about static constructors, see [http://go.microsoft.com/fwlink/?LinkId=59142](http://go.microsoft.com/fwlink/?LinkId=59142).</span></span>  
  
 <span data-ttu-id="14c07-124">直接か間接かに関係なく、オーケストレーションで参照するすべてのオブジェクトは、シリアル化可能にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="14c07-124">All objects that an orchestration references, whether directly or indirectly, must be serializable.</span></span> <span data-ttu-id="14c07-125">詳細については、「シリアル化」を参照してください[永続性と、オーケストレーション エンジン](../core/persistence-and-the-orchestration-engine.md)です。</span><span class="sxs-lookup"><span data-stu-id="14c07-125">For more information, see "Serialization" in [Persistence and the Orchestration Engine](../core/persistence-and-the-orchestration-engine.md).</span></span> <span data-ttu-id="14c07-126">ただし、 **SsoConfigHelper**オブジェクトが必ずしもシリアル化できる場合は、オーケストレーションで復元オブジェクトの 1 つ、現在のインスタンスを使用すると、エンジンでオーケストレーションを退避します。</span><span class="sxs-lookup"><span data-stu-id="14c07-126">Although the **SsoConfigHelper** object is necessarily serializable, if the engine dehydrates the orchestration, when the orchestration rehydrates it will still use the single, current instance of the object.</span></span> <span data-ttu-id="14c07-127">シリアル化および BizTalk Server 変数の詳細については、次を参照してください。[オーケストレーション変数の型](../core/orchestration-variable-types.md)です。</span><span class="sxs-lookup"><span data-stu-id="14c07-127">For more information about serialization and BizTalk Server variables, see [Orchestration Variable Types](../core/orchestration-variable-types.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="14c07-128">サービス指向ソリューションのオブジェクトのすべてのパブリック メソッドは、静的です。</span><span class="sxs-lookup"><span data-stu-id="14c07-128">All public methods on the object in the service oriented solution are static.</span></span> <span data-ttu-id="14c07-129">このため、このオーケストレーションはインスタンスを変数に割り当てる必要はなく、クラスをシリアル化する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="14c07-129">Thus the orchestration does not need to assign an instance to a variable, and there is no need for the class to be serialized.</span></span>  
  
 <span data-ttu-id="14c07-130">**SsoConfigHelper**オブジェクトでは、同じメカニズムを使用して取得し、サービス指向ソリューションのように構成値を更新します。</span><span class="sxs-lookup"><span data-stu-id="14c07-130">The **SsoConfigHelper** object uses the same mechanisms to retrieve and refresh configuration values as does the service oriented solution.</span></span> <span data-ttu-id="14c07-131">同じパターンのロックも使用されます。</span><span class="sxs-lookup"><span data-stu-id="14c07-131">The same pattern of locking is also used.</span></span> <span data-ttu-id="14c07-132">これらのメカニズムの詳細については、次を参照してください。[を使用して SSO の効率的なサービス指向ソリューションで](../core/using-sso-efficiently-in-the-service-oriented-solution.md)とソース コードの**SsoConfigHelper**です。</span><span class="sxs-lookup"><span data-stu-id="14c07-132">For more information about these mechanisms, see [Using SSO Efficiently in the Service Oriented Solution](../core/using-sso-efficiently-in-the-service-oriented-solution.md) and the source code for **SsoConfigHelper**.</span></span>  
  
 <span data-ttu-id="14c07-133">キャッシュでのシングル サインオンは、サービス指向ソリューションの実行と同じように、ビジネス プロセス管理ソリューションを実装する、 **IPropertyBag**からインターフェイス、 **Microsoft.BizTalk.SSOClient.Interop**値を格納する名前空間。</span><span class="sxs-lookup"><span data-stu-id="14c07-133">Like the Single Sign-On caching performed in the service oriented solution, the business process management solution implements the **IPropertyBag** interface from the **Microsoft.BizTalk.SSOClient.Interop** namespace to store the values.</span></span> <span data-ttu-id="14c07-134">ビジネス プロセス管理ソリューションを使用して、 **HybridDictionary**オブジェクトではなく、 **NameValueCollection**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="14c07-134">The business process management solution uses a **HybridDictionary** object rather than a **NameValueCollection** object.</span></span>  
  
 <span data-ttu-id="14c07-135">サービス指向ソリューションとは異なり、ビジネス プロセス管理ソリューションは、構成データに対応するプロパティを持つオブジェクトを公開します。</span><span class="sxs-lookup"><span data-stu-id="14c07-135">Unlike the Service Oriented solution, the Business Process Management solution exposes an object with properties that correspond to the configuration data.</span></span> <span data-ttu-id="14c07-136">これにより、オーケストレーションは、メッセージの種類の違いを処理する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="14c07-136">This prevents the orchestration from having to deal with differences in message types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14c07-137">参照</span><span class="sxs-lookup"><span data-stu-id="14c07-137">See Also</span></span>  
 [<span data-ttu-id="14c07-138">ビジネス プロセス管理ソリューションの実装の要点</span><span class="sxs-lookup"><span data-stu-id="14c07-138">Implementation Highlights of the Business Process Management Solution</span></span>](../core/implementation-highlights-of-the-business-process-management-solution.md)