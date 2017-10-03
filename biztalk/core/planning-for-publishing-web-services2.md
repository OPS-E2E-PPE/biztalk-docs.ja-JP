---
title: "Web Services2 を公開するための計画 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web services, planning
- virtual directories, updating
- BizTalk Server Web Services Publishing Wizard
ms.assetid: 69107557-48e2-4f15-ba42-9fad476a8294
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d0b9d593a3309f7b4477f2fa735f7e265b614c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="planning-for-publishing-web-services"></a><span data-ttu-id="6da06-102">Web サービスを公開するための計画</span><span class="sxs-lookup"><span data-stu-id="6da06-102">Planning for Publishing Web Services</span></span>
<span data-ttu-id="6da06-103">Web サービスは、オーケストレーション内からアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6da06-103">You can access Web services from your orchestrations.</span></span> <span data-ttu-id="6da06-104">BizTalk Web サービス公開ウィザードを使用して、Web サービスを公開することもできます。</span><span class="sxs-lookup"><span data-stu-id="6da06-104">You can also use the BizTalk Web Services Publishing Wizard to publish your Web service.</span></span>  
  
 <span data-ttu-id="6da06-105">次の表は、Web サービスを計画するときに検討する必要がある項目を示しています。</span><span class="sxs-lookup"><span data-stu-id="6da06-105">The following table lists some of the questions that you need to answer in planning for Web services.</span></span>  
  
|<span data-ttu-id="6da06-106">計画段階の考慮事項</span><span class="sxs-lookup"><span data-stu-id="6da06-106">Planning question</span></span>|<span data-ttu-id="6da06-107">推奨</span><span class="sxs-lookup"><span data-stu-id="6da06-107">Recommendation</span></span>|  
|-----------------------|--------------------|  
|<span data-ttu-id="6da06-108">BizTalk Server プロジェクトがビルドされているか</span><span class="sxs-lookup"><span data-stu-id="6da06-108">Have you built your BizTalk Server project?</span></span>|<span data-ttu-id="6da06-109">BizTalk Web サービス公開ウィザードを実行する前に、BizTalk Server プロジェクトをビルドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6da06-109">You must build your BizTalk Server project prior to running the BizTalk Web Services Publishing Wizard.</span></span>|  
|<span data-ttu-id="6da06-110">システムで Web サービスの実行が有効になっているか</span><span class="sxs-lookup"><span data-stu-id="6da06-110">Have you enabled your system to run Web services?</span></span>|<span data-ttu-id="6da06-111">BizTalk Web サービス公開ウィザードを実行する前に、コンピュータで Web サービスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6da06-111">You must enable Web services on your computer before running the BizTalk Web Services Publishing Wizard.</span></span> <span data-ttu-id="6da06-112">Web サービスには、システムを有効にする方法の詳細については、次を参照してください。 [Web サービスを有効にすると](../core/enabling-web-services.md)です。</span><span class="sxs-lookup"><span data-stu-id="6da06-112">For more information about enabling your system for Web services, see [Enabling Web Services](../core/enabling-web-services.md).</span></span>|  
|<span data-ttu-id="6da06-113">有効な XML 文字および要素のみがスキーマに含まれているか</span><span class="sxs-lookup"><span data-stu-id="6da06-113">Have you verified that your schema contains only valid XML characters and elements?</span></span>|<span data-ttu-id="6da06-114">Web サービスは、中国語、日本語、韓国語 (CJK) 統合漢字拡張 A 文字をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="6da06-114">Web services do not support Chinese, Japanese, or Korean (CJK) Unified Ideograph Extension A characters.</span></span> <span data-ttu-id="6da06-115">一部の XML スキーマ (XSD) 要素にも、この制限があります。</span><span class="sxs-lookup"><span data-stu-id="6da06-115">There are also restrictions on certain XML Schema (XSD) elements.</span></span> <span data-ttu-id="6da06-116">有効な XML 文字とサポートされている要素および要素に関する考慮事項に関する詳細については、次を参照してください。[に関する考慮事項と Web サービスの公開](../core/considerations-when-publishing-web-services.md)です。</span><span class="sxs-lookup"><span data-stu-id="6da06-116">For more information about valid XML characters and supported elements and considerations for elements, see [Considerations When Publishing Web Services](../core/considerations-when-publishing-web-services.md).</span></span>|  
|<span data-ttu-id="6da06-117">BizTalk Server プロジェクトのメッセージの種類でユーザー定義の .NET クラスを使用しているか</span><span class="sxs-lookup"><span data-stu-id="6da06-117">Do any of the message types in your BizTalk Server project use user-defined .NET classes?</span></span>|<span data-ttu-id="6da06-118">メッセージの種類で参照しているユーザー定義の .NET クラスを含むアセンブリを、グローバル アセンブリ キャッシュ (GAC) にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6da06-118">You must install assemblies containing user-defined .NET classes that message types reference in the global assembly cache (GAC).</span></span>|  
|<span data-ttu-id="6da06-119">Web クライアントがの指定された資格情報を使用して、 **WindowsUser**コンテキスト プロパティですか?</span><span class="sxs-lookup"><span data-stu-id="6da06-119">Do your Web clients use the supplied credentials for the **WindowsUser** context property?</span></span>|<span data-ttu-id="6da06-120">公開された Web サービスの使用を消費する Web クライアントから提供された資格情報、 **WindowsUser**コンテキスト プロパティです。</span><span class="sxs-lookup"><span data-stu-id="6da06-120">The credentials supplied by the Web clients consuming a published Web service use the **WindowsUser** context property.</span></span> <span data-ttu-id="6da06-121">パーティの解決では、このプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="6da06-121">Party Resolution uses this property.</span></span> <span data-ttu-id="6da06-122">使用してパーティを設定した場合、 **WindowsUser**コンテキスト プロパティと、Web クライアントは、そのパーティに一致する資格情報で Web サービスを利用する、BizTalk Server が、対応する定義済みのパーティから送信されたメッセージを識別します。</span><span class="sxs-lookup"><span data-stu-id="6da06-122">If you set up a Party using the **WindowsUser** context property and the Web client consumes the Web service with credentials that match the Party, BizTalk Server identifies the message as coming from the corresponding predefined party.</span></span> <span data-ttu-id="6da06-123">パーティの解決パイプライン コンポーネントの詳細については、次を参照してください。[パーティの解決パイプライン コンポーネント](../core/party-resolution-pipeline-component.md)です。</span><span class="sxs-lookup"><span data-stu-id="6da06-123">For more information about party resolution with pipeline components, see [Party Resolution Pipeline Component](../core/party-resolution-pipeline-component.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6da06-124">参照</span><span class="sxs-lookup"><span data-stu-id="6da06-124">See Also</span></span>  
 [<span data-ttu-id="6da06-125">Web サービスの公開</span><span class="sxs-lookup"><span data-stu-id="6da06-125">Publishing Web Services</span></span>](../core/publishing-web-services.md)