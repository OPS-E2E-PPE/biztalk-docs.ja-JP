---
title: "実行時、メッセージの修復、FIN 応答とメッセージング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- architecture, about architecture
- architecture
- BizTalk Accelerator for SWIFT, architecture
ms.assetid: c7f34517-6663-44a6-b6ea-6d55fdb08caf
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 539d6f6d7a2b84262750f8b3c6da3c16a67f0de9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="runtime-message-repair-fin-response-and-messaging"></a><span data-ttu-id="56013-102">実行時、メッセージの修復、FIN 応答、およびメッセージング</span><span class="sxs-lookup"><span data-stu-id="56013-102">Runtime, message repair, FIN response, and messaging</span></span>

## <a name="overview"></a><span data-ttu-id="56013-103">概要</span><span class="sxs-lookup"><span data-stu-id="56013-103">Overview</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="56013-104">[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]お客様に提供し、パートナーの実装を促進するのに役立ちます財務業界固有メッセージングおよび接続の機能が、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]金融機関のミドルウェアとします。</span><span class="sxs-lookup"><span data-stu-id="56013-104"> [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] provides customers and partners with financial-industry-specific messaging and connectivity functionality, which helps accelerate implementation of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] as middleware for financial organizations.</span></span>  
  
 <span data-ttu-id="56013-105">オープン標準を活用することによりベースのツールとランタイムの施設が設備[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SWIFT などのメッセージ形式のサポートを実装するには、A4SWIFT を縮小バリアの更新の迅速な標準の導入を採用することによって[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]として、汎用的なミドルウェアの統合プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="56013-105">By leveraging the open-standards based tools and runtime facilities of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] to implement support for message formats like SWIFT, A4SWIFT reduces the barrier to adoption of updated SWIFT standards by employing [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] as a general-purpose middleware integration platform.</span></span>  
  
 <span data-ttu-id="56013-106">A4SWIFT と[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]もエンタープライズ クラスのサーバーをホストするアプリケーションとの統合だけでなくワークフローの配信の全体的なメンテナンスおよびサポート コストを削減保有 (コスト TCO) の総コストを削減しながらの市場に時間が短縮金融サービス業界の実装です。</span><span class="sxs-lookup"><span data-stu-id="56013-106">A4SWIFT and [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] reduce the time-to-market while also decreasing the total cost of ownership (TCO) by reducing the overall maintenance and support cost of delivering enterprise class servers for application hosting and integration as well as workflow implementation in the financial services industry.</span></span>  
  
 <span data-ttu-id="56013-107">A4SWIFT 機能メッセージング SWIFT および SWIFT 接続として大きく分類できます。</span><span class="sxs-lookup"><span data-stu-id="56013-107">You can broadly categorize A4SWIFT functionality as SWIFT messaging and SWIFT connectivity.</span></span> <span data-ttu-id="56013-108">SWIFT メッセージの解析と検証 (受信/送信バッチ処理を含む)、メッセージのエントリと修復を含む完全 A4SWIFT メッセージング (との統合を含む[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フロント エンド ユーザー ツールとして)、およびその他の基幹業務 (LOB) アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="56013-108">Full A4SWIFT messaging encompasses SWIFT message parsing and validation (including inbound/outbound batching), message entry and repair (including integration with [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] as the front-end user tool), and other line-of-business (LOB) applications.</span></span>  
  
 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]<span data-ttu-id="56013-109">XSD スキーマ、および財務 (FIN) メッセージのすべての 358 用のネットワーク ルールを含む、完全な検証を提供します。</span><span class="sxs-lookup"><span data-stu-id="56013-109"> provides XSD schemas and full validation, including network rules, for all 358 of the financial (FIN) messages.</span></span> <span data-ttu-id="56013-110">受信バッチ解除する処理も提供します。</span><span class="sxs-lookup"><span data-stu-id="56013-110">It also provides inbound debatching.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="56013-111">次の手順</span><span class="sxs-lookup"><span data-stu-id="56013-111">Next steps</span></span>  
 <span data-ttu-id="56013-112">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="56013-112">This section contains:</span></span>  
  
-   [<span data-ttu-id="56013-113">Components</span><span class="sxs-lookup"><span data-stu-id="56013-113">Components</span></span>](components.md)  
  
-   [<span data-ttu-id="56013-114">BizTalk Accelerator for SWIFT のランタイム</span><span class="sxs-lookup"><span data-stu-id="56013-114">BizTalk Accelerator for SWIFT Runtime</span></span>](biztalk-accelerator-for-swift-runtime.md)  
  
-   [<span data-ttu-id="56013-115">Message Repair and New Submission</span><span class="sxs-lookup"><span data-stu-id="56013-115">Message Repair and New Submission</span></span>](message-repair-and-new-submission.md)  
  
-   [<span data-ttu-id="56013-116">FIN 対応調整</span><span class="sxs-lookup"><span data-stu-id="56013-116">FIN Response Reconciliation</span></span>](fin-response-reconciliation.md)  
  
-   [<span data-ttu-id="56013-117">SWIFT メッセージ</span><span class="sxs-lookup"><span data-stu-id="56013-117">SWIFT Messages</span></span>](swift-messages.md)

- [<span data-ttu-id="56013-118">A4SWIFT_ * 昇格させたプロパティ</span><span class="sxs-lookup"><span data-stu-id="56013-118">A4SWIFT_* Promoted Properties</span></span>](a4swift-promoted-properties.md)