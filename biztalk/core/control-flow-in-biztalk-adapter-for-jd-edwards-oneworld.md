---
title: BizTalk adapter for JD Edwards OneWorld のフローの制御 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connection pooling
- control flows
- apartment threading
- apartment threading, business functions
ms.assetid: 1ec865d0-2257-453b-9230-1f3787ebac38
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f6514a62a90fd2088c494ab2cc7384ceb0b59a9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354527"
---
# <a name="control-flow-in-biztalk-adapter-for-jd-edwards-oneworld"></a><span data-ttu-id="50f14-102">BizTalk adapter for JD Edwards OneWorld の制御フロー</span><span class="sxs-lookup"><span data-stu-id="50f14-102">Control Flow in BizTalk Adapter for JD Edwards OneWorld</span></span>
<span data-ttu-id="50f14-103">このトピックでは、JD Edwards OneWorld の Microsoft BizTalk Adapter のデザイン時および実行時の制御フローについて説明します。</span><span class="sxs-lookup"><span data-stu-id="50f14-103">This topic discusses the design time and run-time control flows in Microsoft BizTalk Adapter for JD Edwards OneWorld.</span></span>  
  
## <a name="design-time-flow"></a><span data-ttu-id="50f14-104">デザイン時のフロー</span><span class="sxs-lookup"><span data-stu-id="50f14-104">Design-Time Flow</span></span>  
 <span data-ttu-id="50f14-105">アダプターでは、(トランスポートのプロパティ ダイアログ ボックスから、資格情報とシステム情報を使用) が開いたら、JD Edwards OneWorld アプリケーションのビジネス関数の 1 つまたは複数のインスタンスが作成され、プールされました。</span><span class="sxs-lookup"><span data-stu-id="50f14-105">When the adapter opens (using the credentials and system information from the Transport Properties dialog box), one or more instances of the JD Edwards OneWorld application business function are created and pooled.</span></span> <span data-ttu-id="50f14-106">アダプター ウィザードで、名前空間を参照するときは、ビジネス関数の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="50f14-106">When you browse the namespace in the Adapter Wizard, a list of business functions appear.</span></span> <span data-ttu-id="50f14-107">ビジネス関数をクリックすると、メソッドの署名と共にその論理メソッドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="50f14-107">Clicking a business function displays its logical methods along with the methods signatures.</span></span>  
  
## <a name="run-time-flow"></a><span data-ttu-id="50f14-108">実行時のフロー</span><span class="sxs-lookup"><span data-stu-id="50f14-108">Run-Time Flow</span></span>  
 <span data-ttu-id="50f14-109">JD Edwards OneWorld ビジネス関数のインスタンスが作成され、各スレッドのプールします。</span><span class="sxs-lookup"><span data-stu-id="50f14-109">Instances of the JD Edwards OneWorld business function are created and pooled for each thread.</span></span> <span data-ttu-id="50f14-110">JD Edwards OneWorld application ビジネス関数を使用して、メソッドのメタデータを読み取るメソッドの呼び出しがビジネス サービスに送信されると、ただし、メソッドのメタデータが既にキャッシュされている場合、ビジネス関数はキャッシュされた情報を使用し、適切なメソッドの呼び出しをします。</span><span class="sxs-lookup"><span data-stu-id="50f14-110">When a method call is submitted to a business service, the metadata for the method is read using the JD Edwards OneWorld application business function; however, if the metadata for the method has already been cached, the business function uses the cached information and then makes a call to the appropriate method.</span></span> <span data-ttu-id="50f14-111">実行時に、JD Edwards OneWorld インターフェイス レイヤーが動的に構築されます。</span><span class="sxs-lookup"><span data-stu-id="50f14-111">At run time, a JD Edwards OneWorld interface layer is dynamically constructed.</span></span> <span data-ttu-id="50f14-112">インターフェイス レイヤーを通じては BizTalk Adapter for JD Edwards OneWorld は、呼び出しとデータ変換をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="50f14-112">It is through the interface layer that BizTalk Adapter for JD Edwards OneWorld supports invocation and data conversions.</span></span>  
  
 <span data-ttu-id="50f14-113">BizTalk Adapter for JD Edwards OneWorld では、BizTalk Server がこれらのインターフェイスの説明と対話することができるように、JD Edwards OneWorld アプリケーションのメソッド シグネチャにおけるインターフェイスの説明をマップします。</span><span class="sxs-lookup"><span data-stu-id="50f14-113">BizTalk Adapter for JD Edwards OneWorld maps interface descriptions of the method signatures of the JD Edwards OneWorld application, allowing BizTalk Server to interact with these interface descriptions.</span></span>  
  
 <span data-ttu-id="50f14-114">アダプターは、次の 1 つ以上の形式でアプリケーションの機能を拡張して、JD Edwards OneWorld アプリケーションとやり取りする企業のアプリケーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="50f14-114">The adapter enables applications in the enterprise to interact with the JD Edwards OneWorld application by extending functionality from the application in the form of one or more of the following:</span></span>  
  
- <span data-ttu-id="50f14-115">ネイティブのデータ形式</span><span class="sxs-lookup"><span data-stu-id="50f14-115">Native data formats</span></span>  
  
- <span data-ttu-id="50f14-116">手順</span><span class="sxs-lookup"><span data-stu-id="50f14-116">Procedures</span></span>  
  
- <span data-ttu-id="50f14-117">メソッド</span><span class="sxs-lookup"><span data-stu-id="50f14-117">Methods</span></span>  
  
- <span data-ttu-id="50f14-118">メッセージ</span><span class="sxs-lookup"><span data-stu-id="50f14-118">Messages</span></span>  
  
- <span data-ttu-id="50f14-119">プロパティ</span><span class="sxs-lookup"><span data-stu-id="50f14-119">Properties</span></span>  
  
- <span data-ttu-id="50f14-120">アプリケーション インターフェイス</span><span class="sxs-lookup"><span data-stu-id="50f14-120">Application interfaces</span></span>  
  
  <span data-ttu-id="50f14-121">実行時に、BizTalk Adapter for JD Edwards OneWorld は、JD Edwards OneWorld と対話するクライアント アプリケーション用のアプリケーション インターフェイスの説明を作成します。</span><span class="sxs-lookup"><span data-stu-id="50f14-121">At run time, BizTalk Adapter for JD Edwards OneWorld builds a description of application interfaces for client applications that interact with JD Edwards OneWorld.</span></span> <span data-ttu-id="50f14-122">アダプターは、作成、削除、および必要に応じて、アプリケーションで計算を実行し、直接メソッドを呼び出すには、ビジネス オブジェクトを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="50f14-122">The adapter can create, delete, and invoke business objects as needed, to perform computations in the application and directly invoke methods.</span></span> <span data-ttu-id="50f14-123">JD Edwards OneWorld へのすべての呼び出しは、同期呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="50f14-123">All calls into JD Edwards OneWorld are synchronous calls.</span></span> <span data-ttu-id="50f14-124">アダプターは、BizTalk Server から XML メッセージを受信し、SOAP エンベロープにメッセージを囲む、SOAP メッセージからの呼び出しのデータを Java の型に変換します。</span><span class="sxs-lookup"><span data-stu-id="50f14-124">The adapter receives the XML messages from BizTalk Server, encloses the messages in a SOAP envelope, and transforms the data for the call from SOAP messages into Java types.</span></span>  
  
  <span data-ttu-id="50f14-125">次のようなプロセスのバックアップ、応答が送信されます。</span><span class="sxs-lookup"><span data-stu-id="50f14-125">The reply is sent back following a similar process:</span></span>  
  
1.  <span data-ttu-id="50f14-126">Java の型は、SOAP メッセージに変換されます。</span><span class="sxs-lookup"><span data-stu-id="50f14-126">The Java types are transformed into SOAP messages.</span></span>  
  
2.  <span data-ttu-id="50f14-127">SOAP メッセージは、XML メッセージに変換されます。</span><span class="sxs-lookup"><span data-stu-id="50f14-127">The SOAP messages are converted into XML messages.</span></span>  
  
3.  <span data-ttu-id="50f14-128">XML メッセージは、さらに処理するため、BizTalk Server に送信されます。</span><span class="sxs-lookup"><span data-stu-id="50f14-128">The XML messages are submitted to BizTalk Server for further processing.</span></span>  
  
### <a name="apartment-threading-of-business-functions"></a><span data-ttu-id="50f14-129">ビジネス関数のアパートメント スレッド</span><span class="sxs-lookup"><span data-stu-id="50f14-129">Apartment Threading of Business Functions</span></span>  
 <span data-ttu-id="50f14-130">JD Edwards OneWorld のビジネス機能と任意のインスタンスは、作成、または取得されたスレッドでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="50f14-130">A JD Edwards OneWorld business function, and any instance, can only be used on the thread where it is created or obtained.</span></span> <span data-ttu-id="50f14-131">これと呼ばれます*アパートメント スレッド*します。</span><span class="sxs-lookup"><span data-stu-id="50f14-131">This is known as *apartment threading*.</span></span> <span data-ttu-id="50f14-132">BizTalk Adapter for JD Edwards OneWorld の接続プール フレームワークは、利用可能な接続のプールを管理します。</span><span class="sxs-lookup"><span data-stu-id="50f14-132">The connection pooling framework of BizTalk Adapter for JD Edwards OneWorld manages a pool of available connections.</span></span>  
  
### <a name="connection-pooling"></a><span data-ttu-id="50f14-133">接続のプール</span><span class="sxs-lookup"><span data-stu-id="50f14-133">Connection Pooling</span></span>  
 <span data-ttu-id="50f14-134">接続プールと、サーバー システムへの接続を開いたままにして、各呼び出しの後に終了するのではなく再利用することによって呼び出しのパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="50f14-134">Connection pooling improves the performance of calls by keeping connections to the server systems open and reusing them instead of closing them after each call.</span></span> <span data-ttu-id="50f14-135">BizTalk Adapter for JD Edwards OneWorld では、特定のログオン Id 内で接続をプールにできますが、すべてのプールの接続の合計数な制御を維持します。</span><span class="sxs-lookup"><span data-stu-id="50f14-135">BizTalk Adapter for JD Edwards OneWorld enables you to pool connections within particular logon IDs, but still maintains critical control of the total number of connections across all pools.</span></span>  
  
 <span data-ttu-id="50f14-136">新しいビジネス関数のすべてのインスタンスが作成され、各操作後に、インスタンスが破棄されるスレッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="50f14-136">Any new business function instance uses the thread on which it is created, and the instance is destroyed after each operation.</span></span> <span data-ttu-id="50f14-137">すべての JD Edwards OneWorld ビジネス関数呼び出しはステートレスです。ただし、時に、アダプターによりビジネス関数が正しいスレッドで使用されることです。</span><span class="sxs-lookup"><span data-stu-id="50f14-137">All JD Edwards OneWorld calls to business functions are stateless; however, during the operation, the adapter ensures that the business function is used on the correct thread.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50f14-138">参照</span><span class="sxs-lookup"><span data-stu-id="50f14-138">See Also</span></span>  
 <span data-ttu-id="50f14-139">[アプリケーションの開発](../core/developing-applications3.md) </span><span class="sxs-lookup"><span data-stu-id="50f14-139">[Developing Applications](../core/developing-applications3.md) </span></span>  
 [<span data-ttu-id="50f14-140">計画および設計</span><span class="sxs-lookup"><span data-stu-id="50f14-140">Planning and Architecture</span></span>](../core/planning-and-architecture17.md)