---
title: 競合回避モジュールとアダプターのプロバイダー フレームワークの拡張 |Microsoft ドキュメント
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
ms.openlocfilehash: b6ab5caf03d113e313e00a74c11641058e86b886
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294082"
---
# <a name="extending-the-resolver-and-adapter-provider-framework"></a><span data-ttu-id="fa64a-102">競合回避モジュールとアダプターのプロバイダー フレームワークの拡張</span><span class="sxs-lookup"><span data-stu-id="fa64a-102">Extending the Resolver and Adapter Provider Framework</span></span>
<span data-ttu-id="fa64a-103">アダプター プロバイダーのフレームワークとの競合回避モジュールは、エンドポイントと変換の解像度と、ルーティングのサポートを提供し、サービスのカスタム メタデータも提供します。</span><span class="sxs-lookup"><span data-stu-id="fa64a-103">The Resolver and Adapter Provider Framework provides support for endpoint and transformation resolution and routing, and it can also provide custom metadata for services.</span></span> <span data-ttu-id="fa64a-104">フレームワークを動的にエンドポイントを解決および送信アダプターのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="fa64a-104">The framework can dynamically resolve endpoints and set outbound adapter properties.</span></span> <span data-ttu-id="fa64a-105">競合回避モジュールの後にコンポーネント (たとえば、送信 URL を検索する Universal Description, Discovery, and Integration [UDDI] を使用して) エンドポイントを解決する、アダプター プロバイダーのコンポーネントが登録されている Microsoft BizTalk Server アダプターの特定のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="fa64a-105">After a resolver component resolves an endpoint (for example, using Universal Description, Discovery, and Integration [UDDI] to look up an outbound URL), an adapter provider component sets specific properties of registered Microsoft BizTalk Server adapters.</span></span>  
  
 <span data-ttu-id="fa64a-106">これには、競合回避モジュールとアダプターのプロバイダー フレームワークを拡張する 3 つの主な領域があります。</span><span class="sxs-lookup"><span data-stu-id="fa64a-106">There are three main areas where you can extend the Resolver and Adapter Provider Framework:</span></span>  
  
-   [<span data-ttu-id="fa64a-107">カスタム競合回避モジュールを作成します。</span><span class="sxs-lookup"><span data-stu-id="fa64a-107">Creating a Custom Resolver</span></span>](../esb-toolkit/creating-a-custom-resolver.md)  
  
-   [<span data-ttu-id="fa64a-108">Unity コンテナーとカスタム競合回避モジュールを作成します。</span><span class="sxs-lookup"><span data-stu-id="fa64a-108">Creating a Custom Resolver with a Unity Container</span></span>](../esb-toolkit/creating-a-custom-resolver-with-a-unity-container.md)  
  
-   [<span data-ttu-id="fa64a-109">カスタム アダプター プロバイダーの作成</span><span class="sxs-lookup"><span data-stu-id="fa64a-109">Creating a Custom Adapter Provider</span></span>](../esb-toolkit/creating-a-custom-adapter-provider.md)