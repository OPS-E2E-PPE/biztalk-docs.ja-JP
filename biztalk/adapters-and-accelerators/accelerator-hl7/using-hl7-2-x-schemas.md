---
title: HL7 2.X スキーマを使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- 2.X schemas
- HL7, 2.X schemas
- schemas, 2.X schemas
ms.assetid: 7f2d7dd4-76f1-463e-b579-9839a74b9631
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 934ca60bb3d89e08c9e803813f3548f196c3d56d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206778"
---
# <a name="using-hl7-2x-schemas"></a><span data-ttu-id="c9a70-102">HL7 2.X スキーマの使用</span><span class="sxs-lookup"><span data-stu-id="c9a70-102">Using HL7 2.X Schemas</span></span>
<span data-ttu-id="c9a70-103">このセクションで説明 2.X バージョンでサポートされている正常性レベル 7 (HL7) 標準の[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="c9a70-103">This section discusses the 2.X versions of the Health Level Seven (HL7) standard supported by [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)].</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c9a70-104">HL7 標準に準拠する BTAHL7 でインストールされているスキーマを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9a70-104">You may need to update the schemas installed with BTAHL7 to conform to the HL7 standard.</span></span> <span data-ttu-id="c9a70-105">これを行うには、次を参照してください。[データベース エラーの解決](../../adapters-and-accelerators/accelerator-hl7/resolving-database-errors.md)です。</span><span class="sxs-lookup"><span data-stu-id="c9a70-105">To do so, see [Resolving Database Errors](../../adapters-and-accelerators/accelerator-hl7/resolving-database-errors.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9a70-106">BTAHL7 エンジンは、あいまいなスキーマ構造を持つ HL7 スキーマに準拠しているメッセージ インスタンスを処理できません。</span><span class="sxs-lookup"><span data-stu-id="c9a70-106">The BTAHL7 engine cannot process message instances conforming to HL7 schemas that have an ambiguous schema structure.</span></span> <span data-ttu-id="c9a70-107">あいまいなスキーマ構造は、HL7 標準が完全に定義されていない 1 つです。</span><span class="sxs-lookup"><span data-stu-id="c9a70-107">An ambiguous schema structure is one that the HL7 standard has not completely defined.</span></span> <span data-ttu-id="c9a70-108">このようなスキーマには、その CSU と SUR. メッセージ型が含まれます</span><span class="sxs-lookup"><span data-stu-id="c9a70-108">Such schemas include those for message types CSU and SUR.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c9a70-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c9a70-109">In This Section</span></span>  
  
-   [<span data-ttu-id="c9a70-110">HL7 2.X バージョン</span><span class="sxs-lookup"><span data-stu-id="c9a70-110">HL7 2.X Versions</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-versions.md)  
  
-   [<span data-ttu-id="c9a70-111">HL7 2.X サブフォルダーとイベント</span><span class="sxs-lookup"><span data-stu-id="c9a70-111">HL7 2.X Subfolders and Events</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md)  
  
-   [<span data-ttu-id="c9a70-112">HL7 2.X の共通スキーマ ファイル</span><span class="sxs-lookup"><span data-stu-id="c9a70-112">HL7 2.X Common Schema Files</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md)  
  
-   [<span data-ttu-id="c9a70-113">Z オブジェクトと HL7 2.X スキーマを拡張します。</span><span class="sxs-lookup"><span data-stu-id="c9a70-113">Extending HL7 2.X Schemas with Z Objects</span></span>](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)  
  
-   [<span data-ttu-id="c9a70-114">データベース エラーの解決</span><span class="sxs-lookup"><span data-stu-id="c9a70-114">Resolving Database Errors</span></span>](../../adapters-and-accelerators/accelerator-hl7/resolving-database-errors.md)  
  
-   [<span data-ttu-id="c9a70-115">'X'、'Y' Optionality</span><span class="sxs-lookup"><span data-stu-id="c9a70-115">'X' and 'Y' Optionality</span></span>](../../adapters-and-accelerators/accelerator-hl7/x-and-y-optionality.md)  
  
-   [<span data-ttu-id="c9a70-116">反復可能なフィールド セグメント</span><span class="sxs-lookup"><span data-stu-id="c9a70-116">Repeatable Field Segments</span></span>](../../adapters-and-accelerators/accelerator-hl7/repeatable-field-segments.md)