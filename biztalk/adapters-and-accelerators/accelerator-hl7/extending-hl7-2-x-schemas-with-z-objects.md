---
title: Z オブジェクト HL7 2.X スキーマの拡張 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- 2.X schemas, Z objects
- Z objects, extending 2.X schemas
ms.assetid: 0980d919-eb81-4c65-b0f7-f17f7cfef6b3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 514df3e1676e08d33be3a9fb00c61e47925b7b6d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267849"
---
# <a name="extending-hl7-2x-schemas-with-z-objects"></a><span data-ttu-id="6f190-102">Z オブジェクト HL7 2.X スキーマの拡張</span><span class="sxs-lookup"><span data-stu-id="6f190-102">Extending HL7 2.X Schemas with Z Objects</span></span>
<span data-ttu-id="6f190-103">HL7 組織定義 HL7 2.X スキーマの場合を認識し、組織が定義したようにこれらのスキーマを使用して、すべての送信者と受信者が必要ですが、します。</span><span class="sxs-lookup"><span data-stu-id="6f190-103">The HL7 organization defines HL7 2.X schemas, and expects all senders and receivers to recognize and use these schemas as the organization defines them.</span></span> <span data-ttu-id="6f190-104">相互運用性により、スキーマに準拠しています。</span><span class="sxs-lookup"><span data-stu-id="6f190-104">Conforming to the schemas ensures for interoperability.</span></span> <span data-ttu-id="6f190-105">HL7 標準では、既存の HL7 をカスタマイズできるように、特定のローカル目的 2.X スキーマ。</span><span class="sxs-lookup"><span data-stu-id="6f190-105">However, the HL7 standard enables you to customize existing HL7 2.X schemas for your specific local purposes.</span></span> <span data-ttu-id="6f190-106">まったく新しいスキーマおよびオブジェクトを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="6f190-106">You can also define entirely new schemas and objects.</span></span> <span data-ttu-id="6f190-107">そのためにはどのような HL7 標準呼び出し Z オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="6f190-107">You do so with what the HL7 standard calls Z objects.</span></span>  
  
 <span data-ttu-id="6f190-108">HL7 標準では、Z のオブジェクトの値は定義しません。</span><span class="sxs-lookup"><span data-stu-id="6f190-108">The HL7 standard does not define the value of Z objects.</span></span> <span data-ttu-id="6f190-109">パブリッシュされた HL7 スキーマでは、それらは含まれません。</span><span class="sxs-lookup"><span data-stu-id="6f190-109">The published HL7 schemas do not include them.</span></span> <span data-ttu-id="6f190-110">それらをローカルで定義をローカルのすべてのパーティとの契約によりそれらを使用します。</span><span class="sxs-lookup"><span data-stu-id="6f190-110">You define them locally, and use them by agreement with all local parties.</span></span> <span data-ttu-id="6f190-111">HL7 の組織では、すべてのメッセージの種類、トリガー イベント、セグメント、データ型、およびこのローカルで使用する"Z"で始まるテーブルの名前を予約します。</span><span class="sxs-lookup"><span data-stu-id="6f190-111">The HL7 organization reserves all message type, trigger event, segment, data type, and table names beginning with "Z" for this local use.</span></span> <span data-ttu-id="6f190-112">ため、プレフィックスは、HL7 標準は、これらのサイト定義オブジェクト Z オブジェクトを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6f190-112">Because of the prefix, the HL7 standard calls these site-defined objects Z objects.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6f190-113">Z オブジェクトを既存の HL7 定義スキーマに追加すると、そのスキーマの複数のバージョンと最終的する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6f190-113">When you add a Z object to an existing HL7-defined schema, you may end up with multiple versions of that schema.</span></span> <span data-ttu-id="6f190-114">これらの複数のバージョンを処理する最善の方法が Namespace 機能を使用して、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="6f190-114">The best way to handle these multiple versions is to use the Namespace feature in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="6f190-115">この機能を見つけることができます、**検証**] タブの [ [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] (パーティ レベル) でエクスプ ローラーを構成します。</span><span class="sxs-lookup"><span data-stu-id="6f190-115">You can find this feature on the **Validation** tab in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer (at the party level).</span></span> <span data-ttu-id="6f190-116">また、そのプロジェクトを配置するスキーマ内で名前空間プロパティを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f190-116">You will also need to change the namespace property within the schema that you deploy for that project.</span></span>  
  
 <span data-ttu-id="6f190-117">作成またはオブジェクトの処理 Z、Z オブジェクトの HL7 組織が設定される規則を従う必要があります.</span><span class="sxs-lookup"><span data-stu-id="6f190-117">In creating or processing Z objects, you should follow the rules that the HL7 organization has established for Z objects..</span></span>  
  
 <span data-ttu-id="6f190-118">既存のスキーマを Z オブジェクトを追加または新しい Z メッセージ スキーマを作成するときに[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]スキーマを Z オブジェクトと共に HL7 でエンコードされたメッセージの処理に使用します。</span><span class="sxs-lookup"><span data-stu-id="6f190-118">When you add a Z object to an existing schema or create a new Z message schema, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] will use the schema with the Z object(s) to process the HL7-encoded message.</span></span> <span data-ttu-id="6f190-119">この種類の Z オブジェクトは、宣言された Z オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="6f190-119">This type of Z object is a declared Z object.</span></span> <span data-ttu-id="6f190-120">メッセージ スキーマに従って統合エンジンは処理されませんの宣言されていない Z セグメントを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="6f190-120">You can also use an undeclared Z segment, which the integration engine will not process according to the message schema.</span></span> <span data-ttu-id="6f190-121">この種類の Z セグメントの詳細については、次を参照してください。 [Z セグメントの宣言されていない処理](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)します。</span><span class="sxs-lookup"><span data-stu-id="6f190-121">For more information about this type of Z segment, see [Handling Undeclared Z Segments](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6f190-122">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6f190-122">In This Section</span></span>  
  
-   [<span data-ttu-id="6f190-123">宣言された Z セグメントの作成</span><span class="sxs-lookup"><span data-stu-id="6f190-123">Creating Declared Z Segments</span></span>](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md)  
  
-   [<span data-ttu-id="6f190-124">スキーマでのカスタム データ型の作成</span><span class="sxs-lookup"><span data-stu-id="6f190-124">Creating Custom Data Types in Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md)  
  
-   [<span data-ttu-id="6f190-125">スキーマでのカスタム テーブルの作成</span><span class="sxs-lookup"><span data-stu-id="6f190-125">Creating Custom Tables in Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md)  
  
-   [<span data-ttu-id="6f190-126">列挙の拡張</span><span class="sxs-lookup"><span data-stu-id="6f190-126">Extending Enumerations</span></span>](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)  
  
-   [<span data-ttu-id="6f190-127">Z オブジェクト経由のメッセージのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="6f190-127">Customizing Messages through Z Objects</span></span>](../../adapters-and-accelerators/accelerator-hl7/customizing-messages-through-z-objects.md)