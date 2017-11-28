---
title: "BizTalk adapter for JD Edwards OneWorld のフロー制御 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- connection pooling
- control flows
- apartment threading
- apartment threading, business functions
ms.assetid: 1ec865d0-2257-453b-9230-1f3787ebac38
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fc5a8be6516b61c4049242952967ce939513e9c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="control-flow-in-biztalk-adapter-for-jd-edwards-oneworld"></a><span data-ttu-id="c9728-102">BizTalk Adapter for JD Edwards OneWorld の制御フロー</span><span class="sxs-lookup"><span data-stu-id="c9728-102">Control Flow in BizTalk Adapter for JD Edwards OneWorld</span></span>
<span data-ttu-id="c9728-103">このトピックでは、Microsoft BizTalk Adapter for JD Edwards OneWorld のデザイン時および実行時の制御フローについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c9728-103">This topic discusses the design time and run-time control flows in Microsoft BizTalk Adapter for JD Edwards OneWorld.</span></span>  
  
## <a name="design-time-flow"></a><span data-ttu-id="c9728-104">デザイン時のフロー</span><span class="sxs-lookup"><span data-stu-id="c9728-104">Design-Time Flow</span></span>  
 <span data-ttu-id="c9728-105">([トランスポートのプロパティ] ダイアログ ボックスの資格情報およびシステム情報を使用して) アダプターが開くときに、JD Edwards OneWorld アプリケーションのビジネス関数のインスタンスが 1 つ以上作成およびプールされます。</span><span class="sxs-lookup"><span data-stu-id="c9728-105">When the adapter opens (using the credentials and system information from the Transport Properties dialog box), one or more instances of the JD Edwards OneWorld application business function are created and pooled.</span></span> <span data-ttu-id="c9728-106">アダプター ウィザードで名前空間を参照すると、ビジネス関数の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9728-106">When you browse the namespace in the Adapter Wizard, a list of business functions appear.</span></span> <span data-ttu-id="c9728-107">ビジネス関数をクリックすると、論理メソッドがメソッドの署名と共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9728-107">Clicking a business function displays its logical methods along with the methods signatures.</span></span>  
  
## <a name="run-time-flow"></a><span data-ttu-id="c9728-108">実行時のフロー</span><span class="sxs-lookup"><span data-stu-id="c9728-108">Run-Time Flow</span></span>  
 <span data-ttu-id="c9728-109">JD Edwards OneWorld のビジネス関数のインスタンスが、各スレッドに対して作成およびプールされます。</span><span class="sxs-lookup"><span data-stu-id="c9728-109">Instances of the JD Edwards OneWorld business function are created and pooled for each thread.</span></span> <span data-ttu-id="c9728-110">メソッドの呼び出しがビジネス サービスに対して送信されると、JD Edwards OneWorld アプリケーションのビジネス関数を使用して、そのメソッドのメタデータが読み出されます。ただし、そのメソッドのメタデータが既にキャッシュされている場合、ビジネス関数はキャッシュされた情報を使用し、適切なメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c9728-110">When a method call is submitted to a business service, the metadata for the method is read using the JD Edwards OneWorld application business function; however, if the metadata for the method has already been cached, the business function uses the cached information and then makes a call to the appropriate method.</span></span> <span data-ttu-id="c9728-111">実行時には、JD Edwards OneWorld インターフェイス レイヤーが動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="c9728-111">At run time, a JD Edwards OneWorld interface layer is dynamically constructed.</span></span> <span data-ttu-id="c9728-112">BizTalk Adapter for JD Edwards OneWorld は、インターフェイス レイヤーを通じて呼び出しとデータ変換をサポートします。</span><span class="sxs-lookup"><span data-stu-id="c9728-112">It is through the interface layer that BizTalk Adapter for JD Edwards OneWorld supports invocation and data conversions.</span></span>  
  
 <span data-ttu-id="c9728-113">BizTalk Adapter for JD Edwards OneWorld は、JD Edwards OneWorld アプリケーションのメソッド シグネチャにおけるインターフェイスの説明をマップし、BizTalk Server がこれらのインターフェイスの説明と対話できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c9728-113">BizTalk Adapter for JD Edwards OneWorld maps interface descriptions of the method signatures of the JD Edwards OneWorld application, allowing BizTalk Server to interact with these interface descriptions.</span></span>  
  
 <span data-ttu-id="c9728-114">アダプターは、次の 1 つ以上の形式でアプリケーションの機能を拡張することにより、社内のアプリケーションが JD Edwards OneWorld アプリケーションと対話できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c9728-114">The adapter enables applications in the enterprise to interact with the JD Edwards OneWorld application by extending functionality from the application in the form of one or more of the following:</span></span>  
  
-   <span data-ttu-id="c9728-115">ネイティブなデータ形式</span><span class="sxs-lookup"><span data-stu-id="c9728-115">Native data formats</span></span>  
  
-   <span data-ttu-id="c9728-116">手順</span><span class="sxs-lookup"><span data-stu-id="c9728-116">Procedures</span></span>  
  
-   <span data-ttu-id="c9728-117">メソッド</span><span class="sxs-lookup"><span data-stu-id="c9728-117">Methods</span></span>  
  
-   <span data-ttu-id="c9728-118">メッセージ</span><span class="sxs-lookup"><span data-stu-id="c9728-118">Messages</span></span>  
  
-   <span data-ttu-id="c9728-119">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="c9728-119">Properties</span></span>  
  
-   <span data-ttu-id="c9728-120">アプリケーション インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c9728-120">Application interfaces</span></span>  
  
 <span data-ttu-id="c9728-121">BizTalk Adapter for JD Edwards OneWorld は、実行時に、JD Edwards OneWorld と対話するクライアント アプリケーションのアプリケーション インターフェイスの説明を作成します。</span><span class="sxs-lookup"><span data-stu-id="c9728-121">At run time, BizTalk Adapter for JD Edwards OneWorld builds a description of application interfaces for client applications that interact with JD Edwards OneWorld.</span></span> <span data-ttu-id="c9728-122">アダプターは、必要に応じてビジネス オブジェクトを作成、削除、および呼び出し、アプリケーションで計算を実行して直接メソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="c9728-122">The adapter can create, delete, and invoke business objects as needed, to perform computations in the application and directly invoke methods.</span></span> <span data-ttu-id="c9728-123">JD Edwards OneWorld へのすべての呼び出しは同期呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="c9728-123">All calls into JD Edwards OneWorld are synchronous calls.</span></span> <span data-ttu-id="c9728-124">アダプターは、BizTalk Server から XML メッセージを受信し、SOAP エンベロープにメッセージを埋め込み、SOAP メッセージから呼び出しのデータを Java タイプに変換します。</span><span class="sxs-lookup"><span data-stu-id="c9728-124">The adapter receives the XML messages from BizTalk Server, encloses the messages in a SOAP envelope, and transforms the data for the call from SOAP messages into Java types.</span></span>  
  
 <span data-ttu-id="c9728-125">この返信は、次のような同様の処理に従って送信されます。</span><span class="sxs-lookup"><span data-stu-id="c9728-125">The reply is sent back following a similar process:</span></span>  
  
1.  <span data-ttu-id="c9728-126">Java タイプが SOAP メッセージに変換されます。</span><span class="sxs-lookup"><span data-stu-id="c9728-126">The Java types are transformed into SOAP messages.</span></span>  
  
2.  <span data-ttu-id="c9728-127">SOAP メッセージが XML メッセージに変換されます。</span><span class="sxs-lookup"><span data-stu-id="c9728-127">The SOAP messages are converted into XML messages.</span></span>  
  
3.  <span data-ttu-id="c9728-128">XML メッセージが BizTalk Server に送信され、さらに処理されます。</span><span class="sxs-lookup"><span data-stu-id="c9728-128">The XML messages are submitted to BizTalk Server for further processing.</span></span>  
  
### <a name="apartment-threading-of-business-functions"></a><span data-ttu-id="c9728-129">ビジネス関数のアパートメント スレッド</span><span class="sxs-lookup"><span data-stu-id="c9728-129">Apartment Threading of Business Functions</span></span>  
 <span data-ttu-id="c9728-130">JD Edwards OneWorld のビジネス関数と任意のインスタンスは、その作成元または取得元のスレッドのみで使用できます。</span><span class="sxs-lookup"><span data-stu-id="c9728-130">A JD Edwards OneWorld business function, and any instance, can only be used on the thread where it is created or obtained.</span></span> <span data-ttu-id="c9728-131">これは呼ば*アパートメント スレッド*です。</span><span class="sxs-lookup"><span data-stu-id="c9728-131">This is known as *apartment threading*.</span></span> <span data-ttu-id="c9728-132">BizTalk Adapter for JD Edwards OneWorld の接続プール フレームワークは、使用できる接続のプールを管理します。</span><span class="sxs-lookup"><span data-stu-id="c9728-132">The connection pooling framework of BizTalk Adapter for JD Edwards OneWorld manages a pool of available connections.</span></span>  
  
### <a name="connection-pooling"></a><span data-ttu-id="c9728-133">接続のプール</span><span class="sxs-lookup"><span data-stu-id="c9728-133">Connection Pooling</span></span>  
 <span data-ttu-id="c9728-134">接続プールは、サーバー システムへの接続を開いたままにし、呼び出し後に毎回閉じるのではなく再利用することにより、呼び出しのパフォーマンスを向上させます。</span><span class="sxs-lookup"><span data-stu-id="c9728-134">Connection pooling improves the performance of calls by keeping connections to the server systems open and reusing them instead of closing them after each call.</span></span> <span data-ttu-id="c9728-135">BizTalk Adapter for JD Edwards OneWorld を使用すると、特定のログオン ID 内で接続をプールする一方で、すべてのプールにわたる合計接続数の厳密な制御を維持できます。</span><span class="sxs-lookup"><span data-stu-id="c9728-135">BizTalk Adapter for JD Edwards OneWorld enables you to pool connections within particular logon IDs, but still maintains critical control of the total number of connections across all pools.</span></span>  
  
 <span data-ttu-id="c9728-136">新しいビジネス関数のインスタンスは作成元のスレッドを使用します。また、インスタンスは操作後に毎回破棄されます。</span><span class="sxs-lookup"><span data-stu-id="c9728-136">Any new business function instance uses the thread on which it is created, and the instance is destroyed after each operation.</span></span> <span data-ttu-id="c9728-137">JD Edwards OneWorld のビジネス関数の呼び出しは、すべてステートレスです。ただし、アダプターにより、操作中は正しいスレッドでビジネス関数が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c9728-137">All JD Edwards OneWorld calls to business functions are stateless; however, during the operation, the adapter ensures that the business function is used on the correct thread.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9728-138">参照</span><span class="sxs-lookup"><span data-stu-id="c9728-138">See Also</span></span>  
 <span data-ttu-id="c9728-139">[アプリケーションの開発](../core/developing-applications3.md) </span><span class="sxs-lookup"><span data-stu-id="c9728-139">[Developing Applications](../core/developing-applications3.md) </span></span>  
 [<span data-ttu-id="c9728-140">計画とアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="c9728-140">Planning and Architecture</span></span>](../core/planning-and-architecture17.md)