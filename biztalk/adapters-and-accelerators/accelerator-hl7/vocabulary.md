---
title: ボキャブラリ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, vocabulary
- vocabularies
ms.assetid: c5df05dd-4af8-4e48-8509-e692b04adf3c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c77247054914097131103fe33d86fc78551d8cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206658"
---
# <a name="vocabulary"></a><span data-ttu-id="7476e-102">ボキャブラリ</span><span class="sxs-lookup"><span data-stu-id="7476e-102">Vocabulary</span></span>
<span data-ttu-id="7476e-103">HL7 バージョン 2 は、コード化された要素のボキャブラリのいくつかのサポートを提供しますが、ほとんどの場合、ローカル システムのコーディングから描画コードを送信する構造体を提供します。</span><span class="sxs-lookup"><span data-stu-id="7476e-103">HL7 Version 2 provides some support for vocabularies for coded elements, but for the most part, provides a structure that transmits codes drawn from local coding systems.</span></span>  
  
 <span data-ttu-id="7476e-104">HL7 バージョン 2 では、セグメント テーブルは、すべてのコード化されたフィールドをリンクします。</span><span class="sxs-lookup"><span data-stu-id="7476e-104">In HL7 Version 2, a segment table links all coded fields.</span></span> <span data-ttu-id="7476e-105">セグメント テーブルには、フィールドを使用するテーブルの識別子が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7476e-105">The segment table includes the identifier of the table that the field uses.</span></span> <span data-ttu-id="7476e-106">テーブルの 3 種類があります: HL7、定義、外部で定義されたユーザー定義します。</span><span class="sxs-lookup"><span data-stu-id="7476e-106">There are three types of tables: HL7 defined, externally defined, and user-defined.</span></span> <span data-ttu-id="7476e-107">場合によってでは、標準は、ユーザー定義テーブルの値の例を提供します。</span><span class="sxs-lookup"><span data-stu-id="7476e-107">In some cases, the standard supplies example values for a user-defined table.</span></span> <span data-ttu-id="7476e-108">HL7 標準がラベルが、これらを扱う必要があります。</span><span class="sxs-lookup"><span data-stu-id="7476e-108">You should treat these as the HL7 standard has labeled them.</span></span>  
  
 <span data-ttu-id="7476e-109">新しいバージョンは、HL7 が定義されているテーブルからコードを削除することはできませんが、新しいコードを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="7476e-109">In new versions, you cannot remove codes from HL7 defined tables, but you can add new codes.</span></span> <span data-ttu-id="7476e-110">ユーザー定義テーブルを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="7476e-110">You can change user-defined tables at will.</span></span>  
  
 <span data-ttu-id="7476e-111">次の関数の[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) これらの要件をサポートします。</span><span class="sxs-lookup"><span data-stu-id="7476e-111">The following functions of [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) support these requirements:</span></span>  
  
-   <span data-ttu-id="7476e-112">HL7 が定義されているテーブルのすべての操作を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="7476e-112">You can use all of the HL7 defined tables.</span></span>  
  
-   <span data-ttu-id="7476e-113">インポートすることができ、社外での使用が ICD9 LOINC などのコード セットを定義します。</span><span class="sxs-lookup"><span data-stu-id="7476e-113">You can import and use externally defined code sets such as ICD9 and LOINC.</span></span>  
  
-   <span data-ttu-id="7476e-114">ユーザー定義テーブルの値を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="7476e-114">You can provide the values for user-defined tables.</span></span>  
  
-   <span data-ttu-id="7476e-115">システムが異なるコードのセットをサポートする場合には、相互運用するためのさまざまなコード セットを許可するマッピングを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="7476e-115">In cases where systems are supporting different sets of codes, you can set up mappings that allow disparate code sets to interoperate.</span></span> <span data-ttu-id="7476e-116">必要に応じて、中間のマッピングと共に移動する 1 つのユーザー定義テーブルの複数のインスタンスを定義できます。</span><span class="sxs-lookup"><span data-stu-id="7476e-116">If necessary, you can define multiple instances of a single user-defined table to go along with the intermediary mapping.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7476e-117">参照</span><span class="sxs-lookup"><span data-stu-id="7476e-117">See Also</span></span>  
 <span data-ttu-id="7476e-118">[HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="7476e-118">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="7476e-119">[メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="7476e-119">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="7476e-120">HL7 2.X スキーマの使用</span><span class="sxs-lookup"><span data-stu-id="7476e-120">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)