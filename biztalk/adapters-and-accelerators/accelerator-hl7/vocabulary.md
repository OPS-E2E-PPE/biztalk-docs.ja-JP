---
title: ボキャブラリ |Microsoft Docs
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
ms.openlocfilehash: 31e72b51e327581c0a17f18582b0511218b556a7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979035"
---
# <a name="vocabulary"></a><span data-ttu-id="10b56-102">ボキャブラリ</span><span class="sxs-lookup"><span data-stu-id="10b56-102">Vocabulary</span></span>
<span data-ttu-id="10b56-103">HL7 バージョン 2 は、コード化された要素のボキャブラリのいくつかのサポートを提供しますが、ほとんどの場合、ローカル システムのコーディングから描画コードを送信する構造を提供します。</span><span class="sxs-lookup"><span data-stu-id="10b56-103">HL7 Version 2 provides some support for vocabularies for coded elements, but for the most part, provides a structure that transmits codes drawn from local coding systems.</span></span>  
  
 <span data-ttu-id="10b56-104">HL7 バージョン 2 では、セグメント テーブルは、すべてのコード化されたフィールドをリンクします。</span><span class="sxs-lookup"><span data-stu-id="10b56-104">In HL7 Version 2, a segment table links all coded fields.</span></span> <span data-ttu-id="10b56-105">セグメント テーブルには、フィールドを使用するテーブルの識別子が含まれています。</span><span class="sxs-lookup"><span data-stu-id="10b56-105">The segment table includes the identifier of the table that the field uses.</span></span> <span data-ttu-id="10b56-106">テーブルの 3 つの種類があります: HL7 定義、およびユーザー定義の外部で定義します。</span><span class="sxs-lookup"><span data-stu-id="10b56-106">There are three types of tables: HL7 defined, externally defined, and user-defined.</span></span> <span data-ttu-id="10b56-107">場合によってでは、標準は、ユーザー定義テーブルの値の例を提供します。</span><span class="sxs-lookup"><span data-stu-id="10b56-107">In some cases, the standard supplies example values for a user-defined table.</span></span> <span data-ttu-id="10b56-108">HL7 標準がラベルが、これらを扱う必要があります。</span><span class="sxs-lookup"><span data-stu-id="10b56-108">You should treat these as the HL7 standard has labeled them.</span></span>  
  
 <span data-ttu-id="10b56-109">新しいバージョンでは、HL7 定義のテーブルからコードを削除することはできませんが、新しいコードを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="10b56-109">In new versions, you cannot remove codes from HL7 defined tables, but you can add new codes.</span></span> <span data-ttu-id="10b56-110">ユーザー定義テーブルを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="10b56-110">You can change user-defined tables at will.</span></span>  
  
 <span data-ttu-id="10b56-111">Microsoft BizTalk Accelerator for HL7 の次の関数 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) これらの要件をサポートします。</span><span class="sxs-lookup"><span data-stu-id="10b56-111">The following functions of Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) support these requirements:</span></span>  
  
-   <span data-ttu-id="10b56-112">HL7 が定義されているテーブルのすべてを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="10b56-112">You can use all of the HL7 defined tables.</span></span>  
  
-   <span data-ttu-id="10b56-113">インポートすることができ、社外での使用が ICD9 LOINC などのコード セットを定義します。</span><span class="sxs-lookup"><span data-stu-id="10b56-113">You can import and use externally defined code sets such as ICD9 and LOINC.</span></span>  
  
-   <span data-ttu-id="10b56-114">ユーザー定義テーブルの値を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="10b56-114">You can provide the values for user-defined tables.</span></span>  
  
-   <span data-ttu-id="10b56-115">システムがコードのさまざまなセットをサポートする場合は、相互運用するさまざまなコードのセットを許可するマッピングを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="10b56-115">In cases where systems are supporting different sets of codes, you can set up mappings that allow disparate code sets to interoperate.</span></span> <span data-ttu-id="10b56-116">必要に応じて、中間マッピングと共に移動する 1 つのユーザー定義テーブルの複数のインスタンスを定義できます。</span><span class="sxs-lookup"><span data-stu-id="10b56-116">If necessary, you can define multiple instances of a single user-defined table to go along with the intermediary mapping.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10b56-117">参照</span><span class="sxs-lookup"><span data-stu-id="10b56-117">See Also</span></span>  
 <span data-ttu-id="10b56-118">[HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="10b56-118">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="10b56-119">[メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="10b56-119">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="10b56-120">HL7 2.X スキーマの使用</span><span class="sxs-lookup"><span data-stu-id="10b56-120">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)