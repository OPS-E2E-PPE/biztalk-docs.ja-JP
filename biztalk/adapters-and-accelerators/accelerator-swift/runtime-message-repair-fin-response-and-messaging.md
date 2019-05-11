---
title: ランタイム、メッセージの修復、FIN 応答、およびメッセージング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, about architecture
- architecture
- BizTalk Accelerator for SWIFT, architecture
ms.assetid: c7f34517-6663-44a6-b6ea-6d55fdb08caf
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: beeb0169e70841b7f31e889cc51e296de49e45eb
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530215"
---
# <a name="runtime-message-repair-fin-response-and-messaging"></a><span data-ttu-id="6951c-102">ランタイム、メッセージの修復、FIN 応答、およびメッセージング</span><span class="sxs-lookup"><span data-stu-id="6951c-102">Runtime, message repair, FIN response, and messaging</span></span>

## <a name="overview"></a><span data-ttu-id="6951c-103">概要</span><span class="sxs-lookup"><span data-stu-id="6951c-103">Overview</span></span>
<span data-ttu-id="6951c-104">Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]をお客様に提供し、パートナーの実装を促進するのに役立ちます金融業界固有メッセージングおよび接続の機能が、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]金融機関のミドルウェアとして。</span><span class="sxs-lookup"><span data-stu-id="6951c-104">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] provides customers and partners with financial-industry-specific messaging and connectivity functionality, which helps accelerate implementation of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] as middleware for financial organizations.</span></span>  
  
 <span data-ttu-id="6951c-105">ベース ツールとランタイムの機能のオープン標準を利用して[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SWIFT などのメッセージの形式のサポートを実装するために A4SWIFT 削減バリア更新済みの SWIFT 標準の採用に採用して[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]として汎用的なミドルウェアの統合プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="6951c-105">By leveraging the open-standards based tools and runtime facilities of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] to implement support for message formats like SWIFT, A4SWIFT reduces the barrier to adoption of updated SWIFT standards by employing [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] as a general-purpose middleware integration platform.</span></span>  
  
 <span data-ttu-id="6951c-106">A4SWIFT と[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]エンタープライズ クラス サーバーをホストするアプリケーションの統合とワークフローを提供する全体的な保守とサポート コストを減らすことで、合計コスト (tco) を短縮しながらの市場の時間短縮金融サービス業界で実装します。</span><span class="sxs-lookup"><span data-stu-id="6951c-106">A4SWIFT and [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] reduce the time-to-market while also decreasing the total cost of ownership (TCO) by reducing the overall maintenance and support cost of delivering enterprise class servers for application hosting and integration as well as workflow implementation in the financial services industry.</span></span>  
  
 <span data-ttu-id="6951c-107">SWIFT メッセージングと SWIFT の接続と A4SWIFT の機能を大きく分類できます。</span><span class="sxs-lookup"><span data-stu-id="6951c-107">You can broadly categorize A4SWIFT functionality as SWIFT messaging and SWIFT connectivity.</span></span> <span data-ttu-id="6951c-108">SWIFT メッセージの解析と検証 (受信/送信バッチ処理を含む)、メッセージのエントリと修復を含む完全な A4SWIFT メッセージング (Microsoft との統合を含む[!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フロント エンド ユーザー ツールとして)、およびその他基幹業務 (LOB) アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="6951c-108">Full A4SWIFT messaging encompasses SWIFT message parsing and validation (including inbound/outbound batching), message entry and repair (including integration with Microsoft [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] as the front-end user tool), and other line-of-business (LOB) applications.</span></span>  
  
 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] <span data-ttu-id="6951c-109">XSD スキーマおよび財務 (FIN) メッセージのすべての 358 用のネットワーク ルールを含む、完全な検証を提供します。</span><span class="sxs-lookup"><span data-stu-id="6951c-109">provides XSD schemas and full validation, including network rules, for all 358 of the financial (FIN) messages.</span></span> <span data-ttu-id="6951c-110">入力方向の分割処理も提供します。</span><span class="sxs-lookup"><span data-stu-id="6951c-110">It also provides inbound debatching.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="6951c-111">次のステップ</span><span class="sxs-lookup"><span data-stu-id="6951c-111">Next steps</span></span>  
 <span data-ttu-id="6951c-112">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6951c-112">This section contains:</span></span>  
  
-   [<span data-ttu-id="6951c-113">Components</span><span class="sxs-lookup"><span data-stu-id="6951c-113">Components</span></span>](components.md)  
  
-   [<span data-ttu-id="6951c-114">BizTalk Accelerator for SWIFT ランタイム</span><span class="sxs-lookup"><span data-stu-id="6951c-114">BizTalk Accelerator for SWIFT Runtime</span></span>](biztalk-accelerator-for-swift-runtime.md)  
  
-   [<span data-ttu-id="6951c-115">Message Repair and New Submission</span><span class="sxs-lookup"><span data-stu-id="6951c-115">Message Repair and New Submission</span></span>](message-repair-and-new-submission.md)  
  
-   [<span data-ttu-id="6951c-116">FIN Response Reconciliation</span><span class="sxs-lookup"><span data-stu-id="6951c-116">FIN Response Reconciliation</span></span>](fin-response-reconciliation.md)  
  
-   [<span data-ttu-id="6951c-117">SWIFT メッセージ</span><span class="sxs-lookup"><span data-stu-id="6951c-117">SWIFT Messages</span></span>](swift-messages.md)

- [<span data-ttu-id="6951c-118">A4SWIFT_\* 昇格プロパティ</span><span class="sxs-lookup"><span data-stu-id="6951c-118">A4SWIFT_\* Promoted Properties</span></span>](a4swift-promoted-properties.md)