---
title: リゾルバーとアダプターのプロバイダー フレームワークの拡張 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4d5e6f2-b3bc-46e2-b8f7-d7e271d4a8c0
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e53c9284ec85e86cbf3a79ca73d6a819049933f4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400334"
---
# <a name="extending-the-resolver-and-adapter-provider-framework"></a><span data-ttu-id="a1866-102">リゾルバーとアダプターのプロバイダー フレームワークの拡張</span><span class="sxs-lookup"><span data-stu-id="a1866-102">Extending the Resolver and Adapter Provider Framework</span></span>
<span data-ttu-id="a1866-103">リゾルバーとアダプターのプロバイダー フレームワークは、エンドポイントと変換の解決とルーティングのサポートを提供し、サービスのカスタム メタデータも提供します。</span><span class="sxs-lookup"><span data-stu-id="a1866-103">The Resolver and Adapter Provider Framework provides support for endpoint and transformation resolution and routing, and it can also provide custom metadata for services.</span></span> <span data-ttu-id="a1866-104">フレームワークを動的にエンドポイントを解決および送信アダプターのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="a1866-104">The framework can dynamically resolve endpoints and set outbound adapter properties.</span></span> <span data-ttu-id="a1866-105">競合回避モジュールの後にコンポーネント (たとえば、送信 URL を検索する Universal Description, Discovery, and Integration [UDDI] を使用して) エンドポイントの解決、アダプター プロバイダーのコンポーネントが登録されている Microsoft BizTalk Server アダプターの特定のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="a1866-105">After a resolver component resolves an endpoint (for example, using Universal Description, Discovery, and Integration [UDDI] to look up an outbound URL), an adapter provider component sets specific properties of registered Microsoft BizTalk Server adapters.</span></span>  
  
 <span data-ttu-id="a1866-106">これには、リゾルバーとアダプターのプロバイダー フレームワークを拡張する 3 つの主な領域があります。</span><span class="sxs-lookup"><span data-stu-id="a1866-106">There are three main areas where you can extend the Resolver and Adapter Provider Framework:</span></span>  
  
-   [<span data-ttu-id="a1866-107">カスタム リゾルバーを作成する</span><span class="sxs-lookup"><span data-stu-id="a1866-107">Creating a Custom Resolver</span></span>](../esb-toolkit/creating-a-custom-resolver.md)  
  
-   [<span data-ttu-id="a1866-108">Unity コンテナーでカスタム リゾルバーを作成する</span><span class="sxs-lookup"><span data-stu-id="a1866-108">Creating a Custom Resolver with a Unity Container</span></span>](../esb-toolkit/creating-a-custom-resolver-with-a-unity-container.md)  
  
-   [<span data-ttu-id="a1866-109">カスタム アダプター プロバイダーを作成する</span><span class="sxs-lookup"><span data-stu-id="a1866-109">Creating a Custom Adapter Provider</span></span>](../esb-toolkit/creating-a-custom-adapter-provider.md)