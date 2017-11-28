---
title: "第 6 章: ビジネス ルールの展開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tutorial, deploying business rules
- deploying, business rules
- business rules
ms.assetid: e8fb8993-3450-4795-80fd-ff28bff8fe97
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e890456b7ff3e467a0f513a261d12a52f92689f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="module-6-deploying-the-business-rules"></a><span data-ttu-id="e09bb-102">第 6 章: ビジネス ルールの展開</span><span class="sxs-lookup"><span data-stu-id="e09bb-102">Module 6: Deploying the Business Rules</span></span>
<span data-ttu-id="e09bb-103">このモジュールで、インストール ログを確認、および、ビジネス ルール作成ツールを使用してデプロイを確認するビジネス ルールを展開します。</span><span class="sxs-lookup"><span data-stu-id="e09bb-103">In this module, you deploy the business rules, confirm your installation log, and confirm your deployment using the Business Rule Composer tool.</span></span>  
  
 <span data-ttu-id="e09bb-104">ビジネス ルールを使用していることを確認する[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] Worldwide 銀行間財務通信 (SWIFT) 標準の Society で定義されている書式指定、フィールドの仕様、およびネットワーク検証規則に従う必要メッセージ。</span><span class="sxs-lookup"><span data-stu-id="e09bb-104">You use business rules to ensure that [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] messages adhere to format specifications, field specifications, and network validated rules as defined in the Society for Worldwide Interbank Financial Telecommunication (SWIFT) standards.</span></span> <span data-ttu-id="e09bb-105">書式指定が全体としてメッセージの構造に関連し、フィールドの仕様が、メッセージ内の各フィールドについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="e09bb-105">Format specifications pertain to the structure of the message as a whole and field specifications detail each field in the message.</span></span> <span data-ttu-id="e09bb-106">ネットワーク検証ルールは、クロス フィールド検証に適用され、本質的に複雑です。</span><span class="sxs-lookup"><span data-stu-id="e09bb-106">Network validated rules apply to cross-field validations and are complex in nature.</span></span>  
  
 <span data-ttu-id="e09bb-107">A4SWIFT は、各メッセージの XSD スキーマの仕様を提供します。</span><span class="sxs-lookup"><span data-stu-id="e09bb-107">A4SWIFT provides XSD schema specifications for each message.</span></span> <span data-ttu-id="e09bb-108">A4SWIFT の逆アセンブラー (DASM) およびアセンブラー (ASM) は、スキーマを使用して解析またはシリアル化し、ネイティブのフラット ファイル メッセージを検証します。</span><span class="sxs-lookup"><span data-stu-id="e09bb-108">The A4SWIFT disassembler (DASM) and assembler (ASM) use the schema to parse or serialize and validate native flat-file messages.</span></span> <span data-ttu-id="e09bb-109">検証は、書式指定とスキーマをエンコードするフィールドの仕様に制限されます。</span><span class="sxs-lookup"><span data-stu-id="e09bb-109">Validations are limited to format specifications and field specifications that the schema encodes.</span></span> <span data-ttu-id="e09bb-110">ただし、いくつかの形式をエンコードし、スキーマ内の関連の規則をフィールドすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e09bb-110">However, you cannot encode some formats and field related rules within the schema.</span></span>  
  
 <span data-ttu-id="e09bb-111">A4SWIFT には、以下の SWIFT 標準リリース ガイド (SRG) ビジネス ルールのセットも含まれています。</span><span class="sxs-lookup"><span data-stu-id="e09bb-111">A4SWIFT also includes a set of business rules that follow the SWIFT Standards Release Guides (SRG).</span></span> <span data-ttu-id="e09bb-112">BizTalk Server ビジネス ルール エンジン (BRE) は、A4SWIFT ポリシーを呼び出すし、A4SWIFT ビジネス規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="e09bb-112">The BizTalk Server Business Rule Engine (BRE) calls the A4SWIFT policies and enforces the A4SWIFT business rules.</span></span>  
  
 <span data-ttu-id="e09bb-113">これらのビジネス ルールが形式とフィールド、およびスキーマの自然な能力を超えているネットワーク検証規則に関連する複雑な検証のために含まれます。</span><span class="sxs-lookup"><span data-stu-id="e09bb-113">These business rules are included due to the complex validations relating to format and fields, and network-validated rules that are beyond the natural capability of the schema.</span></span> <span data-ttu-id="e09bb-114">SWIFT DASM または ASM コンポーネントの受信または送信パイプライン内では、BRE を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e09bb-114">The SWIFT DASM or ASM components within a receive or send pipeline call the BRE.</span></span>  
  
 <span data-ttu-id="e09bb-115">変更することで、オンまたはオフ、検証を有効にする、 **BREValidation**パイプラインの内部で逆アセンブラーのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="e09bb-115">You turn the validations on or off by changing the **BREValidation** property for the DASM within your pipeline.</span></span>  
  
 <span data-ttu-id="e09bb-116">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e09bb-116">This section contains:</span></span>  
  
-   [<span data-ttu-id="e09bb-117">レッスン 1: 関連するビジネス ルールの展開</span><span class="sxs-lookup"><span data-stu-id="e09bb-117">Lesson 1: Deploying the Related Business Rules</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-1-deploying-the-related-business-rules.md)  
  
-   [<span data-ttu-id="e09bb-118">レッスン 2: ビジネス ルール作成ツールを使用して、展開を確認します。</span><span class="sxs-lookup"><span data-stu-id="e09bb-118">Lesson 2: Confirming the Deployment Using the Business Rule Composer Tool</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-2-confirming-the-deployment-using-the-business-rule-composer-tool.md)