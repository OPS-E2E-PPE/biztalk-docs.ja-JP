---
title: ビジネス プロセス管理ソリューションで効率的に SSO を使用して |Microsoft Docs
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
ms.openlocfilehash: eda9b88ceb99e6487562ecc03f8f7009b09f533e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65321676"
---
# <a name="using-sso-efficiently-in-the-business-process-management-solution"></a><span data-ttu-id="63d96-102">ビジネス プロセス管理ソリューションで SSO の効率的な使用</span><span class="sxs-lookup"><span data-stu-id="63d96-102">Using SSO Efficiently in the Business Process Management Solution</span></span>
<span data-ttu-id="63d96-103">サービス指向ソリューションと同様には、ビジネス プロセス管理ソリューションは、注文処理ステージの数などの構成値を格納するのにエンタープライズ シングル サインオン (SSO) を使用します。</span><span class="sxs-lookup"><span data-stu-id="63d96-103">Like the Service Oriented solution, the Business Process Management solution uses Enterprise Single Sign-On (SSO) to store configuration values such as the number of order processing stages.</span></span> <span data-ttu-id="63d96-104">BizTalk がインストールされているときに存在するため、シークレット ストアを使用して、SSO が構成情報をキャッシュできるように、値はすぐに使用して、データベース接続文字列やパスワードなどの情報を保護できます。</span><span class="sxs-lookup"><span data-stu-id="63d96-104">It uses the secret store because it is present whenever BizTalk is installed, SSO caches the configuration information so that the values are readily available, and it can protect information such as database connection strings and passwords.</span></span> <span data-ttu-id="63d96-105">これらの理由からすべては、シングル サインオンでした。 バックエンド アプリケーションへの接続を管理するため使用されている場合でものシークレット ストアは構成情報のことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="63d96-105">For all of these reasons, the secret store is a good place for the configuration information even if Single Sign-On weren't being used for managing connections to the backend applications.</span></span>  
  
 <span data-ttu-id="63d96-106">待機時間を減らすためには、ソリューションは構成値のローカル キャッシュを使用します。</span><span class="sxs-lookup"><span data-stu-id="63d96-106">To reduce latency, the solution uses a local cache for the configuration values.</span></span> <span data-ttu-id="63d96-107">ソリューションは、5 分ごとにキャッシュを更新します。</span><span class="sxs-lookup"><span data-stu-id="63d96-107">The solution refreshes the cache every five minutes.</span></span>  
  
 <span data-ttu-id="63d96-108">このトピックでは、ソリューションで使用されるキャッシュ メカニズムについて説明します。</span><span class="sxs-lookup"><span data-stu-id="63d96-108">This topic describes the caching mechanism used by the solution.</span></span> <span data-ttu-id="63d96-109">このソリューションでは、SSO のキャッシュ サービス指向ソリューションよりも若干異なるアプローチを採用します。</span><span class="sxs-lookup"><span data-stu-id="63d96-109">This solution takes a slightly different approach to SSO caching than does the service oriented solution.</span></span> <span data-ttu-id="63d96-110">サービス指向のソリューションの説明には、SSO 値がキャッシュを参照してください[を使用して SSO の効率的なサービス指向ソリューションで](../core/using-sso-efficiently-in-the-service-oriented-solution.md)します。</span><span class="sxs-lookup"><span data-stu-id="63d96-110">For a description of how the service oriented solution caches SSO values, see [Using SSO Efficiently in the Service Oriented Solution](../core/using-sso-efficiently-in-the-service-oriented-solution.md).</span></span>  
  
## <a name="caching-configuration-values-locally"></a><span data-ttu-id="63d96-111">ローカル キャッシュの構成値</span><span class="sxs-lookup"><span data-stu-id="63d96-111">Caching Configuration Values Locally</span></span>  
 <span data-ttu-id="63d96-112">ビジネス プロセス管理ソリューションでは、SSO 値へのアクセスを提供するのにシングルトン オブジェクトのプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="63d96-112">The business process management solution uses properties on a singleton object to provide access to the SSO values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="63d96-113">シングルトン オブジェクトがオブジェクト インスタンスの 1 つだけ持つことができますを思い出してください。</span><span class="sxs-lookup"><span data-stu-id="63d96-113">Recall that a singleton object is an object that can have only one instance.</span></span> <span data-ttu-id="63d96-114">単一オブジェクトとで作成の詳細についてはC#を参照してください[ http://go.microsoft.com/fwlink/?LinkId=58806](http://go.microsoft.com/fwlink/?LinkId=58806)します。</span><span class="sxs-lookup"><span data-stu-id="63d96-114">For more information about singleton objects and creating them in C#, see [http://go.microsoft.com/fwlink/?LinkId=58806](http://go.microsoft.com/fwlink/?LinkId=58806).</span></span>  
  
 <span data-ttu-id="63d96-115">ソリューションでは、オーケストレーションは最初シングルトン オブジェクトを取得し、オブジェクトのプロパティから値を参照します。</span><span class="sxs-lookup"><span data-stu-id="63d96-115">In the solution, an orchestration first retrieves the singleton object and then references the values through the object's properties.</span></span> <span data-ttu-id="63d96-116">コードをここでは、 **OrderManager**オーケストレーション。</span><span class="sxs-lookup"><span data-stu-id="63d96-116">Here is code from the **OrderManager** orchestration:</span></span>  
  
```  
configData = Microsoft.Samples.BizTalk.SouthridgeVideo.Utilities  
                .SsoConfigHelper.Singleton;  
numStages = configData.TotalStages;  
```  
  
 <span data-ttu-id="63d96-117">オーケストレーションの呼び出し、**シングルトン**メソッドを**SsoConfigHelper**オブジェクトの 1 つのコピーへのアクセスを取得するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="63d96-117">The orchestration calls the **Singleton** method on the **SsoConfigHelper** object to get access to the one copy of the object.</span></span> <span data-ttu-id="63d96-118">手の形でオブジェクトが、オーケストレーションは処理ステージの数を取得**TotalStages**します。</span><span class="sxs-lookup"><span data-stu-id="63d96-118">With the object in hand, the orchestration retrieves the number of processing stages, **TotalStages**.</span></span>  
  
 <span data-ttu-id="63d96-119">ソリューションに依存する一般的なシングルトンを作成する方法: コンス トラクターをプライベートには、オブジェクト自体のインスタンスを作成し、秘密の変数に割り当てることと、メソッドまたはプロパティからその変数の値へのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="63d96-119">The solution follows a common method of creating a singleton: make the constructor private, have the object create an instance of itself and assign that to a private variable, and, through a method or property, provide access to the value of that variable.</span></span> <span data-ttu-id="63d96-120">**SsoConfigHelper**オブジェクトは、プロパティを使用して**シングルトン**、それ自体の 1 つのコピーへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="63d96-120">The **SsoConfigHelper** object uses a property, **Singleton**, to provide access to the single copy of itself.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="63d96-121">**SsoConfigHelper**オブジェクトは、SSO のキャッシュから初期値を取得し、更新メカニズムを設定する静的コンス トラクターを使用します。</span><span class="sxs-lookup"><span data-stu-id="63d96-121">The **SsoConfigHelper** object uses a static constructor to get the initial values from the SSO cache and to set up the refresh mechanism.</span></span> <span data-ttu-id="63d96-122">静的コンス トラクターが呼び出されることはできません、ため、シングルトン設計が保持されます。</span><span class="sxs-lookup"><span data-stu-id="63d96-122">Because a static constructor cannot be called, it preserves the singleton design.</span></span> <span data-ttu-id="63d96-123">静的コンス トラクターの詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=59142](http://go.microsoft.com/fwlink/?LinkId=59142)します。</span><span class="sxs-lookup"><span data-stu-id="63d96-123">For more information about static constructors, see [http://go.microsoft.com/fwlink/?LinkId=59142](http://go.microsoft.com/fwlink/?LinkId=59142).</span></span>  
  
 <span data-ttu-id="63d96-124">直接的または間接的にするかどうか、オーケストレーションで参照するすべてのオブジェクトをシリアル化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63d96-124">All objects that an orchestration references, whether directly or indirectly, must be serializable.</span></span> <span data-ttu-id="63d96-125">詳細については、「シリアル化」を参照してください[永続性とオーケストレーション エンジン](../core/persistence-and-the-orchestration-engine.md)します。</span><span class="sxs-lookup"><span data-stu-id="63d96-125">For more information, see "Serialization" in [Persistence and the Orchestration Engine](../core/persistence-and-the-orchestration-engine.md).</span></span> <span data-ttu-id="63d96-126">ただし、 **SsoConfigHelper**オブジェクトが、それでもオーケストレーション必要オブジェクトの 1 つ、現在のインスタンスを使用すると、エンジンでオーケストレーションを退避する場合、必ずしも serializable。</span><span class="sxs-lookup"><span data-stu-id="63d96-126">Although the **SsoConfigHelper** object is necessarily serializable, if the engine dehydrates the orchestration, when the orchestration rehydrates it will still use the single, current instance of the object.</span></span> <span data-ttu-id="63d96-127">シリアル化と BizTalk Server 変数の詳細については、次を参照してください。[オーケストレーション変数の型](../core/orchestration-variable-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="63d96-127">For more information about serialization and BizTalk Server variables, see [Orchestration Variable Types](../core/orchestration-variable-types.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="63d96-128">サービス指向ソリューション内のオブジェクトのすべてのパブリック メソッドは静的です。</span><span class="sxs-lookup"><span data-stu-id="63d96-128">All public methods on the object in the service oriented solution are static.</span></span> <span data-ttu-id="63d96-129">したがって、オーケストレーションは、インスタンスを割り当てる変数にする必要はありませんし、クラスをシリアル化する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="63d96-129">Thus the orchestration does not need to assign an instance to a variable, and there is no need for the class to be serialized.</span></span>  
  
 <span data-ttu-id="63d96-130">**SsoConfigHelper**オブジェクトでは、同じメカニズムを使用して取得し、サービス指向ソリューションのように構成値を更新します。</span><span class="sxs-lookup"><span data-stu-id="63d96-130">The **SsoConfigHelper** object uses the same mechanisms to retrieve and refresh configuration values as does the service oriented solution.</span></span> <span data-ttu-id="63d96-131">同じパターンのロックが使用されます。</span><span class="sxs-lookup"><span data-stu-id="63d96-131">The same pattern of locking is also used.</span></span> <span data-ttu-id="63d96-132">これらのメカニズムの詳細については、次を参照してください。[を使用して SSO の効率的なサービス指向ソリューションで](../core/using-sso-efficiently-in-the-service-oriented-solution.md)のソース コードと**SsoConfigHelper**します。</span><span class="sxs-lookup"><span data-stu-id="63d96-132">For more information about these mechanisms, see [Using SSO Efficiently in the Service Oriented Solution](../core/using-sso-efficiently-in-the-service-oriented-solution.md) and the source code for **SsoConfigHelper**.</span></span>  
  
 <span data-ttu-id="63d96-133">ビジネス プロセス管理ソリューションを実装するサービス指向ソリューションでのキャッシュでシングル サインオン実行と同様に、 **IPropertyBag**からインターフェイス、 **Microsoft.BizTalk.SSOClient.Interop**値を格納する名前空間。</span><span class="sxs-lookup"><span data-stu-id="63d96-133">Like the Single Sign-On caching performed in the service oriented solution, the business process management solution implements the **IPropertyBag** interface from the **Microsoft.BizTalk.SSOClient.Interop** namespace to store the values.</span></span> <span data-ttu-id="63d96-134">ビジネス プロセス管理ソリューションを使用して、 **HybridDictionary**オブジェクトではなく**NameValueCollection**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="63d96-134">The business process management solution uses a **HybridDictionary** object rather than a **NameValueCollection** object.</span></span>  
  
 <span data-ttu-id="63d96-135">ビジネス プロセス管理ソリューションでは、サービス指向ソリューションとは異なり、構成データに対応するプロパティを持つオブジェクトを公開します。</span><span class="sxs-lookup"><span data-stu-id="63d96-135">Unlike the Service Oriented solution, the Business Process Management solution exposes an object with properties that correspond to the configuration data.</span></span> <span data-ttu-id="63d96-136">これには、オーケストレーションからメッセージの種類の違いを処理することができないようにします。</span><span class="sxs-lookup"><span data-stu-id="63d96-136">This prevents the orchestration from having to deal with differences in message types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63d96-137">参照</span><span class="sxs-lookup"><span data-stu-id="63d96-137">See Also</span></span>  
 [<span data-ttu-id="63d96-138">ビジネス プロセス管理ソリューションの実装の重要なポイント</span><span class="sxs-lookup"><span data-stu-id="63d96-138">Implementation Highlights of the Business Process Management Solution</span></span>](../core/implementation-highlights-of-the-business-process-management-solution.md)