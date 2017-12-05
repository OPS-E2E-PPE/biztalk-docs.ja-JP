---
title: "動的なメッセージの種類の探索用のカスタム ヘッダーのスキーマの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, dynamic resolution
- schemas, message types
- schemas, custom headers
- header schemas
ms.assetid: 0c936c57-b533-47ca-9258-576b021fd016
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c87ba83961b9daac07028a994d7c01add0c11a73
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="creating-custom-header-schemas-for-dynamic-message-type-discovery"></a><span data-ttu-id="79e00-102">動的なメッセージの種類の探索用のカスタム ヘッダーのスキーマの作成</span><span class="sxs-lookup"><span data-stu-id="79e00-102">Creating Custom Header Schemas for Dynamic Message Type Discovery</span></span>
<span data-ttu-id="79e00-103">ほとんどのシナリオでは、SWIFT、逆アセンブラーの SWIFT ヘッダー スキーマ構成プロパティの既定の SWIFT ヘッダー スキーマ (Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema) を指定してください。</span><span class="sxs-lookup"><span data-stu-id="79e00-103">In most scenarios, you should specify the default SWIFT header schema (Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema) for the SWIFT Header Schema configuration property of the SWIFT disassembler.</span></span> <span data-ttu-id="79e00-104">SWIFT の逆アセンブラーでは、既定の SWIFT ヘッダー スキーマを使用して、SWIFT の標準仕様に準拠しているメッセージ ヘッダーを解析しが、必要な昇格されたプロパティを動的スキーマの解決 (と「デュアル型」のサブ型解決を容易にします。SWIFT メッセージなど、MT574_IRSLST MT574_W8BENO)。</span><span class="sxs-lookup"><span data-stu-id="79e00-104">The SWIFT disassembler uses the default SWIFT header schema to parse message headers that conform to the SWIFT standard specification, and has the necessary promoted properties to facilitate dynamic schema resolution (and sub-type resolution for "dual type" SWIFT messages like MT574_IRSLST and MT574_W8BENO).</span></span> <span data-ttu-id="79e00-105">既定の SWIFT ヘッダー スキーマおよび SWIFT の逆アセンブラーがスキーマの解決を実行する方法を理解する詳細については、次を参照してください。[動的メッセージ型の検出とスキーマの解決](../../adapters-and-accelerators/accelerator-swift/dynamic-message-type-discovery-and-schema-resolution.md)です。</span><span class="sxs-lookup"><span data-stu-id="79e00-105">For more information about the default SWIFT header schema and to understand how the SWIFT disassembler performs schema resolution, see [Dynamic Message Type Discovery and Schema Resolution](../../adapters-and-accelerators/accelerator-swift/dynamic-message-type-discovery-and-schema-resolution.md).</span></span>  
  
 <span data-ttu-id="79e00-106">メッセージに SWIFT 非標準ヘッダー データが含まれているその他のシナリオのヘッダーの解析および動的なメッセージの種類の探索カスタム ヘッダー スキーマを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="79e00-106">For other scenarios where messages contain non-SWIFT standard header data, you can use a custom header schema for header parsing and dynamic message type discovery.</span></span> <span data-ttu-id="79e00-107">作成し、動的スキーマの解決のカスタム ヘッダー スキーマを使用するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="79e00-107">To create and use a custom header schema for dynamic schema resolution, do the following:</span></span>  
  
1.  <span data-ttu-id="79e00-108">SWIFT の逆アセンブラーが構造的にデータの形式が求められるヘッダーの解析に使用できるカスタム スキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="79e00-108">Create a custom schema that the SWIFT disassembler can use to structurally parse the expected header data format.</span></span>  
  
2.  <span data-ttu-id="79e00-109">メッセージの種類を示す値を保持するスキーマのどのフィールドを識別します。</span><span class="sxs-lookup"><span data-stu-id="79e00-109">Identify which fields in the schema will hold the value(s) indicating message type.</span></span>  
  
3.  <span data-ttu-id="79e00-110">"プロパティ スキーマの一覧に"カスタム ヘッダー スキーマ A4SWIFT プロパティ スキーマ (Microsoft.Solutions.A4SWIFT.Property.PropertySchema) を追加し、次を使用してメッセージの種類を示す適切なフィールドを昇格[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]プロパティ。</span><span class="sxs-lookup"><span data-stu-id="79e00-110">Add the A4SWIFT Property Schema (Microsoft.Solutions.A4SWIFT.Property.PropertySchema) to the "Property schemas list" of the custom header schema and promote the appropriate fields that indicate message type using the following [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] properties:</span></span>  
  
    -   <span data-ttu-id="79e00-111">**A4SWIFT_MessageType**</span><span class="sxs-lookup"><span data-stu-id="79e00-111">**A4SWIFT_MessageType**</span></span>  
  
    -   <span data-ttu-id="79e00-112">**A4SWIFT_MessageType2** (省略可能な場合**A4SWIFT_MessageTypes**を使用)</span><span class="sxs-lookup"><span data-stu-id="79e00-112">**A4SWIFT_MessageType2** (optional if **A4SWIFT_MessageTypes** is used)</span></span>  
  
    -   <span data-ttu-id="79e00-113">**A4SWIFT_SecondaryMessageType** (省略可能)</span><span class="sxs-lookup"><span data-stu-id="79e00-113">**A4SWIFT_SecondaryMessageType** (optional)</span></span>  
  
4.  <span data-ttu-id="79e00-114">構築し、カスタム ヘッダー スキーマを展開します。</span><span class="sxs-lookup"><span data-stu-id="79e00-114">Build and deploy the custom header schema.</span></span>  
  
5.  <span data-ttu-id="79e00-115">カスタム ヘッダーのスキーマに SWIFT の逆アセンブラー (の受信パイプライン プロジェクト) の SWIFT ヘッダー スキーマ構成プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="79e00-115">Set the SWIFT Header Schema configuration property of the SWIFT disassembler (in your receive pipeline project) to the custom header schema.</span></span>  
  
 <span data-ttu-id="79e00-116">これらおよびその他の昇格させたプロパティの詳細については、次を参照してください。 [A4SWIFT_ * 昇格されたプロパティ](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="79e00-116">For more information about these and other promoted properties, see [A4SWIFT_* Promoted Properties](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md).</span></span> <span data-ttu-id="79e00-117">BizTalk エディターを使用して作成およびスキーマを編集、プロパティ スキーマを使用してプロパティを昇格させるとビルドおよびスキーマ プロジェクトを配置する方法の詳細については、BizTalk Server ヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="79e00-117">For more information about using BizTalk Editor to create and edit schemas, promote properties using a property schema, and build and deploy schema projects, see BizTalk Server Help.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79e00-118">参照</span><span class="sxs-lookup"><span data-stu-id="79e00-118">See Also</span></span>  
 [<span data-ttu-id="79e00-119">SWIFT 逆アセンブラーおよびアセンブラーの操作</span><span class="sxs-lookup"><span data-stu-id="79e00-119">Working with the SWIFT Disassembler and Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)