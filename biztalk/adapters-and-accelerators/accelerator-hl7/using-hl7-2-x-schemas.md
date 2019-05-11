---
title: HL7 2.X スキーマの使用 |Microsoft Docs
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
ms.openlocfilehash: a5ea42c0479d852e9b5ee74c2ee76e83f3555970
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65286353"
---
# <a name="using-hl7-2x-schemas"></a><span data-ttu-id="88c68-102">HL7 2.X スキーマの使用</span><span class="sxs-lookup"><span data-stu-id="88c68-102">Using HL7 2.X Schemas</span></span>
<span data-ttu-id="88c68-103">このセクションでは、Microsoft でサポートされている正常性レベル 7 (HL7) の標準の 2.X バージョンをについて説明します[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="88c68-103">This section discusses the 2.X versions of the Health Level Seven (HL7) standard supported by Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)].</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="88c68-104">HL7 標準に準拠するように BTAHL7 でインストールされているスキーマを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88c68-104">You may need to update the schemas installed with BTAHL7 to conform to the HL7 standard.</span></span> <span data-ttu-id="88c68-105">これを行うを参照してください。[データベース エラーの解決](../../adapters-and-accelerators/accelerator-hl7/resolving-database-errors.md)します。</span><span class="sxs-lookup"><span data-stu-id="88c68-105">To do so, see [Resolving Database Errors](../../adapters-and-accelerators/accelerator-hl7/resolving-database-errors.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="88c68-106">BTAHL7 エンジンは、あいまいなスキーマ構造を持つ HL7 スキーマに準拠しているメッセージ インスタンスを処理できません。</span><span class="sxs-lookup"><span data-stu-id="88c68-106">The BTAHL7 engine cannot process message instances conforming to HL7 schemas that have an ambiguous schema structure.</span></span> <span data-ttu-id="88c68-107">あいまいなスキーマの構造体は、HL7 標準が完全に定義されていない 1 つ。</span><span class="sxs-lookup"><span data-stu-id="88c68-107">An ambiguous schema structure is one that the HL7 standard has not completely defined.</span></span> <span data-ttu-id="88c68-108">このようなスキーマには、メッセージの種類を固定および SUR.</span><span class="sxs-lookup"><span data-stu-id="88c68-108">Such schemas include those for message types CSU and SUR.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="88c68-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="88c68-109">In This Section</span></span>  
  
-   [<span data-ttu-id="88c68-110">HL7 2.X バージョン</span><span class="sxs-lookup"><span data-stu-id="88c68-110">HL7 2.X Versions</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-versions.md)  
  
-   [<span data-ttu-id="88c68-111">HL7 2.X のサブフォルダーとイベント</span><span class="sxs-lookup"><span data-stu-id="88c68-111">HL7 2.X Subfolders and Events</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-subfolders-and-events.md)  
  
-   [<span data-ttu-id="88c68-112">HL7 2.X の共通スキーマ ファイル</span><span class="sxs-lookup"><span data-stu-id="88c68-112">HL7 2.X Common Schema Files</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md)  
  
-   [<span data-ttu-id="88c68-113">Z オブジェクトを使用した HL7 2.X スキーマの拡張</span><span class="sxs-lookup"><span data-stu-id="88c68-113">Extending HL7 2.X Schemas with Z Objects</span></span>](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)  
  
-   [<span data-ttu-id="88c68-114">データベース エラーの解決</span><span class="sxs-lookup"><span data-stu-id="88c68-114">Resolving Database Errors</span></span>](../../adapters-and-accelerators/accelerator-hl7/resolving-database-errors.md)  
  
-   [<span data-ttu-id="88c68-115">'X' および 'Y' Optionality</span><span class="sxs-lookup"><span data-stu-id="88c68-115">'X' and 'Y' Optionality</span></span>](../../adapters-and-accelerators/accelerator-hl7/x-and-y-optionality.md)  
  
-   [<span data-ttu-id="88c68-116">反復可能なフィールド セグメント</span><span class="sxs-lookup"><span data-stu-id="88c68-116">Repeatable Field Segments</span></span>](../../adapters-and-accelerators/accelerator-hl7/repeatable-field-segments.md)