---
title: XML アセンブラーで認識されないメッセージのパイプライン コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XMLNorm.AllowUnrecognizedMessage property
- XML Assembler [pipeline component], unrecognized messages
- pipeline components, XML Assembler
ms.assetid: dd98512a-33a4-4b2e-977e-1b3a30747c6a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de9f072fc09126d56397725f93505afaca46adf4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974819"
---
# <a name="unrecognized-messages-in-the-xml-assembler-pipeline-component"></a><span data-ttu-id="9d174-102">XML アセンブラー パイプライン コンポーネントで認識されないメッセージ</span><span class="sxs-lookup"><span data-stu-id="9d174-102">Unrecognized Messages in the XML Assembler Pipeline Component</span></span>
<span data-ttu-id="9d174-103">XML アセンブラー コンポーネントは、メッセージが次に示す事項に該当する場合、"認識されない" メッセージとして処理します。</span><span class="sxs-lookup"><span data-stu-id="9d174-103">The XML Assembler component treats a message as "unrecognized" if a message has:</span></span>  
  
-   <span data-ttu-id="9d174-104">ボディ部がない。</span><span class="sxs-lookup"><span data-stu-id="9d174-104">No body part.</span></span>  
  
-   <span data-ttu-id="9d174-105">ボディ部が空である。</span><span class="sxs-lookup"><span data-stu-id="9d174-105">An empty body part.</span></span>  
  
-   <span data-ttu-id="9d174-106">ボディ部にデータがない。</span><span class="sxs-lookup"><span data-stu-id="9d174-106">No data in the body part.</span></span>  
  
-   <span data-ttu-id="9d174-107">展開されている関連スキーマがない。</span><span class="sxs-lookup"><span data-stu-id="9d174-107">No associated schema deployed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9d174-108">XML 以外のメッセージは、常に "認識されない" メッセージとして処理されます。</span><span class="sxs-lookup"><span data-stu-id="9d174-108">Non-XML messages are always treated as unrecognized.</span></span>  
  
 <span data-ttu-id="9d174-109">XML アセンブラーが認識されないメッセージを処理する方法がによって制御される、 **XMLNorm.AllowUnrecognizedMessage**メッセージ コンテキスト プロパティ。</span><span class="sxs-lookup"><span data-stu-id="9d174-109">The manner in which the XML Assembler handles an unrecognized message is controlled by the **XMLNorm.AllowUnrecognizedMessage** message context property.</span></span>  
  
 <span data-ttu-id="9d174-110">ときに**XMLNorm.AllowUnrecognizedMessage**に設定されている**True**、XML アセンブラーが XML ドキュメントを次のように処理します。</span><span class="sxs-lookup"><span data-stu-id="9d174-110">When **XMLNorm.AllowUnrecognizedMessage** is set to **True**, the XML Assembler handles XML documents as follows:</span></span>  
  
- <span data-ttu-id="9d174-111">ボディ部のないメッセージ、ボディ部が空のメッセージ、またはボディ部にデータがないメッセージは、アセンブラーを通じて変更せずに渡されます。</span><span class="sxs-lookup"><span data-stu-id="9d174-111">A message with no body part or with an empty body part or empty data in the body part passes unchanged through the assembler.</span></span>  
  
- <span data-ttu-id="9d174-112">展開されたスキーマがドキュメントに関連付けられていない場合、アセンブラーを通じて変更せずに渡されます。</span><span class="sxs-lookup"><span data-stu-id="9d174-112">A document that does not have a deployed schema associated with it passes unchanged through the assembler.</span></span>  
  
- <span data-ttu-id="9d174-113">スキーマがコンポーネントのプロパティで明示的に参照されているか、スキーマ解決プロセスで見つかったかどうかに関係なく、展開されたスキーマがドキュメントに関連付けられている場合は、アセンブラーによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="9d174-113">A document with an associated deployed schema is processed by the assembler (regardless of whether the schema is explicitly referenced in a component property or found during the schema resolution process).</span></span>  
  
  <span data-ttu-id="9d174-114">場合**XMLNorm.AllowUnrecognizedMessage**に設定されている**False**、XML アセンブラーが XML ドキュメントを次のように処理します。</span><span class="sxs-lookup"><span data-stu-id="9d174-114">If **XMLNorm.AllowUnrecognizedMessage** is set to **False**, the XML Assembler handles XML documents as follows:</span></span>  
  
- <span data-ttu-id="9d174-115">ボディ部のないメッセージ、ボディ部が空のメッセージ、またはボディ部にデータがないメッセージは、処理されません。</span><span class="sxs-lookup"><span data-stu-id="9d174-115">A message with no body part or with an empty body part or empty data in the body part is not processed.</span></span> <span data-ttu-id="9d174-116">エラーが報告され、メッセージが中断されます。</span><span class="sxs-lookup"><span data-stu-id="9d174-116">An error is reported and the message is suspended.</span></span>  
  
- <span data-ttu-id="9d174-117">展開されたスキーマがメッセージに関連付けられていない場合、メッセージは処理されません。</span><span class="sxs-lookup"><span data-stu-id="9d174-117">A message that does not have a deployed schema associated with it is not processed.</span></span> <span data-ttu-id="9d174-118">エラーが報告され、メッセージが中断されます。</span><span class="sxs-lookup"><span data-stu-id="9d174-118">An error is reported and the message is suspended.</span></span>  
  
- <span data-ttu-id="9d174-119">スキーマがコンポーネントのプロパティで明示的に参照されているか、スキーマ解決プロセスで見つかったかどうかに関係なく、展開されたスキーマがドキュメントに関連付けられている場合は、アセンブラーによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="9d174-119">A document with an associated deployed schema is processed by the assembler (regardless of whether the schema is explicitly referenced in a component property or found during the schema resolution process).</span></span>  
  
- <span data-ttu-id="9d174-120">既定では、XML アセンブラー コンポーネントにより認識されないメッセージ (つまり、 **XMLNorm.AllowUnrecognizedMessages**と見なされます**False**メッセージ コンテキストに設定されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="9d174-120">By default, the XML Assembler component does not allow unrecognized messages (that is, **XMLNorm.AllowUnrecognizedMessages** is considered **False** if it is not set on the message context).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d174-121">参照</span><span class="sxs-lookup"><span data-stu-id="9d174-121">See Also</span></span>  
 <span data-ttu-id="9d174-122">[XML アセンブラー パイプライン コンポーネント](../core/xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="9d174-122">[XML Assembler Pipeline Component](../core/xml-assembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="9d174-123">[XML アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="9d174-123">[How to Configure the XML Assembler Pipeline Component](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="9d174-124">Pipelines-AssemblerDisassembler (BizTalk Server サンプル フォルダー)</span><span class="sxs-lookup"><span data-stu-id="9d174-124">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)