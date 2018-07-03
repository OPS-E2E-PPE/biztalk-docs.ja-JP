---
title: 'モジュール 6: ビジネス ルールの展開 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tutorial, deploying business rules
- deploying, business rules
- business rules
ms.assetid: e8fb8993-3450-4795-80fd-ff28bff8fe97
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 389d8038b5a216f90d85399eeefaebde86284c71
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972843"
---
# <a name="module-6-deploying-the-business-rules"></a><span data-ttu-id="1db82-102">モジュール 6: ビジネス ルールの展開</span><span class="sxs-lookup"><span data-stu-id="1db82-102">Module 6: Deploying the Business Rules</span></span>
<span data-ttu-id="1db82-103">このモジュールで、インストール ログを確認、および、ビジネス ルール作成ツールを使用してデプロイを確認します。 ビジネス ルールを展開します。</span><span class="sxs-lookup"><span data-stu-id="1db82-103">In this module, you deploy the business rules, confirm your installation log, and confirm your deployment using the Business Rule Composer tool.</span></span>  
  
 <span data-ttu-id="1db82-104">ビジネス ルールを使用することを確認するマイクロソフト[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]メッセージは、世界銀行間金融電気通信 (SWIFT) 標準の社会で定義されている書式指定、フィールドの仕様、およびネットワークの検証規則に準拠します。</span><span class="sxs-lookup"><span data-stu-id="1db82-104">You use business rules to ensure that Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] messages adhere to format specifications, field specifications, and network validated rules as defined in the Society for Worldwide Interbank Financial Telecommunication (SWIFT) standards.</span></span> <span data-ttu-id="1db82-105">書式指定が全体としてのメッセージの構造に関連し、フィールドの指定が、メッセージ内の各フィールドについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="1db82-105">Format specifications pertain to the structure of the message as a whole and field specifications detail each field in the message.</span></span> <span data-ttu-id="1db82-106">ネットワーク検証規則は、クロス フィールド検証に適用され、本質的に複雑な。</span><span class="sxs-lookup"><span data-stu-id="1db82-106">Network validated rules apply to cross-field validations and are complex in nature.</span></span>  
  
 <span data-ttu-id="1db82-107">A4SWIFT では、各メッセージの XSD スキーマの仕様を提供します。</span><span class="sxs-lookup"><span data-stu-id="1db82-107">A4SWIFT provides XSD schema specifications for each message.</span></span> <span data-ttu-id="1db82-108">A4SWIFT (逆アセンブラー) を逆アセンブラーとアセンブラー (ASM) は、スキーマを使用して解析またはシリアル化し、ネイティブのフラット ファイル メッセージを検証します。</span><span class="sxs-lookup"><span data-stu-id="1db82-108">The A4SWIFT disassembler (DASM) and assembler (ASM) use the schema to parse or serialize and validate native flat-file messages.</span></span> <span data-ttu-id="1db82-109">検証は、書式指定と、スキーマをエンコードするフィールドの指定に制限されます。</span><span class="sxs-lookup"><span data-stu-id="1db82-109">Validations are limited to format specifications and field specifications that the schema encodes.</span></span> <span data-ttu-id="1db82-110">ただし、いくつかの形式をエンコードし、スキーマ内で関連する規則をフィールドことはできません。</span><span class="sxs-lookup"><span data-stu-id="1db82-110">However, you cannot encode some formats and field related rules within the schema.</span></span>  
  
 <span data-ttu-id="1db82-111">A4SWIFT には、以下の SWIFT 標準リリース ガイド (SRG) ビジネス ルールのセットも含まれています。</span><span class="sxs-lookup"><span data-stu-id="1db82-111">A4SWIFT also includes a set of business rules that follow the SWIFT Standards Release Guides (SRG).</span></span> <span data-ttu-id="1db82-112">BizTalk Server ビジネス ルール エンジン (BRE) は、A4SWIFT ポリシーを呼び出すし、A4SWIFT のビジネス ルールを適用します。</span><span class="sxs-lookup"><span data-stu-id="1db82-112">The BizTalk Server Business Rule Engine (BRE) calls the A4SWIFT policies and enforces the A4SWIFT business rules.</span></span>  
  
 <span data-ttu-id="1db82-113">これらのビジネス ルールは、形式とフィールド、およびスキーマの自然な能力を超えているネットワーク検証ルールに関連する複雑な検証のためです。</span><span class="sxs-lookup"><span data-stu-id="1db82-113">These business rules are included due to the complex validations relating to format and fields, and network-validated rules that are beyond the natural capability of the schema.</span></span> <span data-ttu-id="1db82-114">SWIFT 逆アセンブラーまたは ASM コンポーネントの受信または送信パイプライン内では、BRE を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="1db82-114">The SWIFT DASM or ASM components within a receive or send pipeline call the BRE.</span></span>  
  
 <span data-ttu-id="1db82-115">変更することでオンまたはオフの検証を有効にする、 **BREValidation**パイプライン内での逆アセンブラーのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="1db82-115">You turn the validations on or off by changing the **BREValidation** property for the DASM within your pipeline.</span></span>  
  
 <span data-ttu-id="1db82-116">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1db82-116">This section contains:</span></span>  
  
-   [<span data-ttu-id="1db82-117">レッスン 1: 関連するビジネス ルールを展開する</span><span class="sxs-lookup"><span data-stu-id="1db82-117">Lesson 1: Deploying the Related Business Rules</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-1-deploying-the-related-business-rules.md)  
  
-   [<span data-ttu-id="1db82-118">レッスン 2: ビジネス ルール作成ツールを使用して展開を確認する</span><span class="sxs-lookup"><span data-stu-id="1db82-118">Lesson 2: Confirming the Deployment Using the Business Rule Composer Tool</span></span>](../../adapters-and-accelerators/accelerator-swift/lesson-2-confirming-the-deployment-using-the-business-rule-composer-tool.md)