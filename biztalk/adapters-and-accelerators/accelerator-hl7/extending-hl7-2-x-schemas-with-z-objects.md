---
title: "Z オブジェクトと HL7 2.X スキーマを拡張 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 2.X schemas, Z objects
- Z objects, extending 2.X schemas
ms.assetid: 0980d919-eb81-4c65-b0f7-f17f7cfef6b3
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a27ef2bea3e13904f04449a5b77d05672c2b2d94
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="extending-hl7-2x-schemas-with-z-objects"></a><span data-ttu-id="84d52-102">Z オブジェクトと HL7 2.X スキーマを拡張します。</span><span class="sxs-lookup"><span data-stu-id="84d52-102">Extending HL7 2.X Schemas with Z Objects</span></span>
<span data-ttu-id="84d52-103">HL7 組織定義 HL7 2.X スキーマを認識し、組織を定義すると、これらのスキーマを使用して、すべての送信者と受信者を想定します。</span><span class="sxs-lookup"><span data-stu-id="84d52-103">The HL7 organization defines HL7 2.X schemas, and expects all senders and receivers to recognize and use these schemas as the organization defines them.</span></span> <span data-ttu-id="84d52-104">相互運用性により、スキーマに準拠しています。</span><span class="sxs-lookup"><span data-stu-id="84d52-104">Conforming to the schemas ensures for interoperability.</span></span> <span data-ttu-id="84d52-105">HL7 標準では、既存の HL7 をカスタマイズすることできます、特定のローカルの目的の 2.X スキーマです。</span><span class="sxs-lookup"><span data-stu-id="84d52-105">However, the HL7 standard enables you to customize existing HL7 2.X schemas for your specific local purposes.</span></span> <span data-ttu-id="84d52-106">まったく新しいスキーマとオブジェクトを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="84d52-106">You can also define entirely new schemas and objects.</span></span> <span data-ttu-id="84d52-107">ためにはどのような HL7 標準呼び出し Z オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="84d52-107">You do so with what the HL7 standard calls Z objects.</span></span>  
  
 <span data-ttu-id="84d52-108">標準 HL7 では、Z のオブジェクトの値は定義しません。</span><span class="sxs-lookup"><span data-stu-id="84d52-108">The HL7 standard does not define the value of Z objects.</span></span> <span data-ttu-id="84d52-109">パブリッシュされた HL7 スキーマでは、それらは含まれません。</span><span class="sxs-lookup"><span data-stu-id="84d52-109">The published HL7 schemas do not include them.</span></span> <span data-ttu-id="84d52-110">それらをローカルに定義し、ローカルのすべてのパーティとの契約して使用します。</span><span class="sxs-lookup"><span data-stu-id="84d52-110">You define them locally, and use them by agreement with all local parties.</span></span> <span data-ttu-id="84d52-111">HL7 組織では、すべてのメッセージの種類、イベントのトリガー、セグメント、データ型、およびこのローカルに使用する"Z"で始まるテーブル名を予約します。</span><span class="sxs-lookup"><span data-stu-id="84d52-111">The HL7 organization reserves all message type, trigger event, segment, data type, and table names beginning with "Z" for this local use.</span></span> <span data-ttu-id="84d52-112">により、そのプレフィックスは、HL7 標準は、これらのサイト定義オブジェクト Z オブジェクトを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="84d52-112">Because of the prefix, the HL7 standard calls these site-defined objects Z objects.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="84d52-113">既存の HL7 定義スキーマに Z オブジェクトを追加するときになる場合がありますそのスキーマの複数のバージョン。</span><span class="sxs-lookup"><span data-stu-id="84d52-113">When you add a Z object to an existing HL7-defined schema, you may end up with multiple versions of that schema.</span></span> <span data-ttu-id="84d52-114">これらの複数バージョンを処理する最善の方法は Namespace 機能を使用する[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="84d52-114">The best way to handle these multiple versions is to use the Namespace feature in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="84d52-115">この機能を見つけることができます、**検証**] タブの [ [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] (パーティ レベルでエクスプ ローラーを構成します。</span><span class="sxs-lookup"><span data-stu-id="84d52-115">You can find this feature on the **Validation** tab in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer (at the party level).</span></span> <span data-ttu-id="84d52-116">そのプロジェクトを配置するスキーマ内で名前空間プロパティを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84d52-116">You will also need to change the namespace property within the schema that you deploy for that project.</span></span>  
  
 <span data-ttu-id="84d52-117">作成または処理 Z オブジェクトでは、Z オブジェクト用 HL7 組織に設定が規則に従う必要があります.</span><span class="sxs-lookup"><span data-stu-id="84d52-117">In creating or processing Z objects, you should follow the rules that the HL7 organization has established for Z objects..</span></span>  
  
 <span data-ttu-id="84d52-118">既存のスキーマに Z オブジェクトを追加または新しい Z メッセージ スキーマを作成するときに[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]Z オブジェクトと HL7 でエンコードされたメッセージを処理するスキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="84d52-118">When you add a Z object to an existing schema or create a new Z message schema, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] will use the schema with the Z object(s) to process the HL7-encoded message.</span></span> <span data-ttu-id="84d52-119">この種類の Z オブジェクトは、宣言されている Z オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="84d52-119">This type of Z object is a declared Z object.</span></span> <span data-ttu-id="84d52-120">メッセージ スキーマに従って統合エンジンは処理されませんの宣言されていない Z セグメントを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="84d52-120">You can also use an undeclared Z segment, which the integration engine will not process according to the message schema.</span></span> <span data-ttu-id="84d52-121">この種類の Z セグメントに関する詳細については、次を参照してください。[宣言されていない Z セグメントの処理](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)です。</span><span class="sxs-lookup"><span data-stu-id="84d52-121">For more information about this type of Z segment, see [Handling Undeclared Z Segments](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="84d52-122">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="84d52-122">In This Section</span></span>  
  
-   [<span data-ttu-id="84d52-123">宣言されている Z セグメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="84d52-123">Creating Declared Z Segments</span></span>](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md)  
  
-   [<span data-ttu-id="84d52-124">スキーマでカスタム データ型を作成します。</span><span class="sxs-lookup"><span data-stu-id="84d52-124">Creating Custom Data Types in Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md)  
  
-   [<span data-ttu-id="84d52-125">スキーマのカスタム テーブルの作成</span><span class="sxs-lookup"><span data-stu-id="84d52-125">Creating Custom Tables in Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md)  
  
-   [<span data-ttu-id="84d52-126">列挙型を拡張します。</span><span class="sxs-lookup"><span data-stu-id="84d52-126">Extending Enumerations</span></span>](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)  
  
-   [<span data-ttu-id="84d52-127">Z オブジェクト経由でメッセージをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="84d52-127">Customizing Messages through Z Objects</span></span>](../../adapters-and-accelerators/accelerator-hl7/customizing-messages-through-z-objects.md)