---
title: "認識されないメッセージを XML アセンブラー パイプライン コンポーネント |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XMLNorm.AllowUnrecognizedMessage property
- XML Assembler [pipeline component], unrecognized messages
- pipeline components, XML Assembler
ms.assetid: dd98512a-33a4-4b2e-977e-1b3a30747c6a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6766554374413c3d1b6a3ce385f24d4046521c91
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="unrecognized-messages-in-the-xml-assembler-pipeline-component"></a><span data-ttu-id="c3930-102">XML アセンブラー パイプライン コンポーネントで認識されないメッセージ</span><span class="sxs-lookup"><span data-stu-id="c3930-102">Unrecognized Messages in the XML Assembler Pipeline Component</span></span>
<span data-ttu-id="c3930-103">XML アセンブラー コンポーネントは、メッセージが次に示す事項に該当する場合、"認識されない" メッセージとして処理します。</span><span class="sxs-lookup"><span data-stu-id="c3930-103">The XML Assembler component treats a message as "unrecognized" if a message has:</span></span>  
  
-   <span data-ttu-id="c3930-104">ボディ部がない。</span><span class="sxs-lookup"><span data-stu-id="c3930-104">No body part.</span></span>  
  
-   <span data-ttu-id="c3930-105">ボディ部が空である。</span><span class="sxs-lookup"><span data-stu-id="c3930-105">An empty body part.</span></span>  
  
-   <span data-ttu-id="c3930-106">ボディ部にデータがない。</span><span class="sxs-lookup"><span data-stu-id="c3930-106">No data in the body part.</span></span>  
  
-   <span data-ttu-id="c3930-107">展開されている関連スキーマがない。</span><span class="sxs-lookup"><span data-stu-id="c3930-107">No associated schema deployed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c3930-108">XML 以外のメッセージは、常に "認識されない" メッセージとして処理されます。</span><span class="sxs-lookup"><span data-stu-id="c3930-108">Non-XML messages are always treated as unrecognized.</span></span>  
  
 <span data-ttu-id="c3930-109">によって、XML アセンブラーが認識されないメッセージを処理する方法を制御、 **XMLNorm.AllowUnrecognizedMessage**メッセージ コンテキスト プロパティです。</span><span class="sxs-lookup"><span data-stu-id="c3930-109">The manner in which the XML Assembler handles an unrecognized message is controlled by the **XMLNorm.AllowUnrecognizedMessage** message context property.</span></span>  
  
 <span data-ttu-id="c3930-110">ときに**XMLNorm.AllowUnrecognizedMessage**に設定されている**True**、XML アセンブラーが XML ドキュメントを次のように処理します。</span><span class="sxs-lookup"><span data-stu-id="c3930-110">When **XMLNorm.AllowUnrecognizedMessage** is set to **True**, the XML Assembler handles XML documents as follows:</span></span>  
  
-   <span data-ttu-id="c3930-111">ボディ部のないメッセージ、ボディ部が空のメッセージ、またはボディ部にデータがないメッセージは、アセンブラーを通じて変更せずに渡されます。</span><span class="sxs-lookup"><span data-stu-id="c3930-111">A message with no body part or with an empty body part or empty data in the body part passes unchanged through the assembler.</span></span>  
  
-   <span data-ttu-id="c3930-112">展開されたスキーマがドキュメントに関連付けられていない場合、アセンブラーを通じて変更せずに渡されます。</span><span class="sxs-lookup"><span data-stu-id="c3930-112">A document that does not have a deployed schema associated with it passes unchanged through the assembler.</span></span>  
  
-   <span data-ttu-id="c3930-113">スキーマがコンポーネントのプロパティで明示的に参照されているか、スキーマ解決プロセスで見つかったかどうかに関係なく、展開されたスキーマがドキュメントに関連付けられている場合は、アセンブラーによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="c3930-113">A document with an associated deployed schema is processed by the assembler (regardless of whether the schema is explicitly referenced in a component property or found during the schema resolution process).</span></span>  
  
 <span data-ttu-id="c3930-114">場合**XMLNorm.AllowUnrecognizedMessage**に設定されている**False**、XML アセンブラーが XML ドキュメントを次のように処理します。</span><span class="sxs-lookup"><span data-stu-id="c3930-114">If **XMLNorm.AllowUnrecognizedMessage** is set to **False**, the XML Assembler handles XML documents as follows:</span></span>  
  
-   <span data-ttu-id="c3930-115">ボディ部のないメッセージ、ボディ部が空のメッセージ、またはボディ部にデータがないメッセージは、処理されません。</span><span class="sxs-lookup"><span data-stu-id="c3930-115">A message with no body part or with an empty body part or empty data in the body part is not processed.</span></span> <span data-ttu-id="c3930-116">エラーが報告され、メッセージが中断されます。</span><span class="sxs-lookup"><span data-stu-id="c3930-116">An error is reported and the message is suspended.</span></span>  
  
-   <span data-ttu-id="c3930-117">展開されたスキーマがメッセージに関連付けられていない場合、メッセージは処理されません。</span><span class="sxs-lookup"><span data-stu-id="c3930-117">A message that does not have a deployed schema associated with it is not processed.</span></span> <span data-ttu-id="c3930-118">エラーが報告され、メッセージが中断されます。</span><span class="sxs-lookup"><span data-stu-id="c3930-118">An error is reported and the message is suspended.</span></span>  
  
-   <span data-ttu-id="c3930-119">スキーマがコンポーネントのプロパティで明示的に参照されているか、スキーマ解決プロセスで見つかったかどうかに関係なく、展開されたスキーマがドキュメントに関連付けられている場合は、アセンブラーによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="c3930-119">A document with an associated deployed schema is processed by the assembler (regardless of whether the schema is explicitly referenced in a component property or found during the schema resolution process).</span></span>  
  
-   <span data-ttu-id="c3930-120">既定では、XML アセンブラー コンポーネントはメッセージを許可しません認識されていない (つまり、 **XMLNorm.AllowUnrecognizedMessages**と見なされます**False**メッセージ コンテキストに設定されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="c3930-120">By default, the XML Assembler component does not allow unrecognized messages (that is, **XMLNorm.AllowUnrecognizedMessages** is considered **False** if it is not set on the message context).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3930-121">参照</span><span class="sxs-lookup"><span data-stu-id="c3930-121">See Also</span></span>  
 <span data-ttu-id="c3930-122">[XML アセンブラー パイプライン コンポーネント](../core/xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="c3930-122">[XML Assembler Pipeline Component](../core/xml-assembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="c3930-123">[XML アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="c3930-123">[How to Configure the XML Assembler Pipeline Component](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="c3930-124">パイプライン AssemblerDisassembler (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="c3930-124">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)