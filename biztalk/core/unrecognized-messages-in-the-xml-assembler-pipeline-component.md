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
ms.openlocfilehash: c61a82f051349b69d72089093f4646325490a943
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292608"
---
# <a name="unrecognized-messages-in-the-xml-assembler-pipeline-component"></a><span data-ttu-id="4e0c1-102">XML アセンブラー パイプライン コンポーネントで認識されないメッセージ</span><span class="sxs-lookup"><span data-stu-id="4e0c1-102">Unrecognized Messages in the XML Assembler Pipeline Component</span></span>
<span data-ttu-id="4e0c1-103">XML アセンブラー コンポーネントでは、メッセージがメッセージは「認識されない」として扱われます。</span><span class="sxs-lookup"><span data-stu-id="4e0c1-103">The XML Assembler component treats a message as "unrecognized" if a message has:</span></span>  
  
-   <span data-ttu-id="4e0c1-104">ボディ部がないです。</span><span class="sxs-lookup"><span data-stu-id="4e0c1-104">No body part.</span></span>  
  
-   <span data-ttu-id="4e0c1-105">空の本文。</span><span class="sxs-lookup"><span data-stu-id="4e0c1-105">An empty body part.</span></span>  
  
-   <span data-ttu-id="4e0c1-106">ボディ部にデータがありません。</span><span class="sxs-lookup"><span data-stu-id="4e0c1-106">No data in the body part.</span></span>  
  
-   <span data-ttu-id="4e0c1-107">関連付けられているスキーマが展開されているはありません。</span><span class="sxs-lookup"><span data-stu-id="4e0c1-107">No associated schema deployed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4e0c1-108">XML 以外のメッセージの処理は常に認識されないとします。</span><span class="sxs-lookup"><span data-stu-id="4e0c1-108">Non-XML messages are always treated as unrecognized.</span></span>  
  
 <span data-ttu-id="4e0c1-109">XML アセンブラーが認識されないメッセージを処理する方法がによって制御される、 **XMLNorm.AllowUnrecognizedMessage**メッセージ コンテキスト プロパティ。</span><span class="sxs-lookup"><span data-stu-id="4e0c1-109">The manner in which the XML Assembler handles an unrecognized message is controlled by the **XMLNorm.AllowUnrecognizedMessage** message context property.</span></span>  
  
 <span data-ttu-id="4e0c1-110">ときに**XMLNorm.AllowUnrecognizedMessage**に設定されている**True**、XML アセンブラーが XML ドキュメントを次のように処理します。</span><span class="sxs-lookup"><span data-stu-id="4e0c1-110">When **XMLNorm.AllowUnrecognizedMessage** is set to **True**, the XML Assembler handles XML documents as follows:</span></span>  
  
- <span data-ttu-id="4e0c1-111">メッセージのボディ部がないと、空の本文の一部またはデータが空の本文部分パスでは、アセンブラーを通じて変更されていません。</span><span class="sxs-lookup"><span data-stu-id="4e0c1-111">A message with no body part or with an empty body part or empty data in the body part passes unchanged through the assembler.</span></span>  
  
- <span data-ttu-id="4e0c1-112">アセンブラーを通じて変更せずに関連付けられている展開されたスキーマがないドキュメントが渡されます。</span><span class="sxs-lookup"><span data-stu-id="4e0c1-112">A document that does not have a deployed schema associated with it passes unchanged through the assembler.</span></span>  
  
- <span data-ttu-id="4e0c1-113">関連付けられている展開済みのスキーマを持つドキュメントは、(かにかかわらず、スキーマが明示的にコンポーネントのプロパティで参照されるスキーマの解決プロセスで見つかった) アセンブラーによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="4e0c1-113">A document with an associated deployed schema is processed by the assembler (regardless of whether the schema is explicitly referenced in a component property or found during the schema resolution process).</span></span>  
  
  <span data-ttu-id="4e0c1-114">場合**XMLNorm.AllowUnrecognizedMessage**に設定されている**False**、XML アセンブラーが XML ドキュメントを次のように処理します。</span><span class="sxs-lookup"><span data-stu-id="4e0c1-114">If **XMLNorm.AllowUnrecognizedMessage** is set to **False**, the XML Assembler handles XML documents as follows:</span></span>  
  
- <span data-ttu-id="4e0c1-115">メッセージのボディ部がないと、空の本文の一部または本文部分に空のデータは処理されません。</span><span class="sxs-lookup"><span data-stu-id="4e0c1-115">A message with no body part or with an empty body part or empty data in the body part is not processed.</span></span> <span data-ttu-id="4e0c1-116">エラーが報告され、メッセージは中断されます。</span><span class="sxs-lookup"><span data-stu-id="4e0c1-116">An error is reported and the message is suspended.</span></span>  
  
- <span data-ttu-id="4e0c1-117">関連付けられている展開されたスキーマがないメッセージは処理されません。</span><span class="sxs-lookup"><span data-stu-id="4e0c1-117">A message that does not have a deployed schema associated with it is not processed.</span></span> <span data-ttu-id="4e0c1-118">エラーが報告され、メッセージは中断されます。</span><span class="sxs-lookup"><span data-stu-id="4e0c1-118">An error is reported and the message is suspended.</span></span>  
  
- <span data-ttu-id="4e0c1-119">関連付けられている展開済みのスキーマを持つドキュメントは、(かにかかわらず、スキーマが明示的にコンポーネントのプロパティで参照されるスキーマの解決プロセスで見つかった) アセンブラーによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="4e0c1-119">A document with an associated deployed schema is processed by the assembler (regardless of whether the schema is explicitly referenced in a component property or found during the schema resolution process).</span></span>  
  
- <span data-ttu-id="4e0c1-120">既定では、XML アセンブラー コンポーネントにより認識されないメッセージ (つまり、 **XMLNorm.AllowUnrecognizedMessages**と見なされます**False**メッセージ コンテキストに設定されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="4e0c1-120">By default, the XML Assembler component does not allow unrecognized messages (that is, **XMLNorm.AllowUnrecognizedMessages** is considered **False** if it is not set on the message context).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e0c1-121">参照</span><span class="sxs-lookup"><span data-stu-id="4e0c1-121">See Also</span></span>  
 <span data-ttu-id="4e0c1-122">[XML アセンブラー パイプライン コンポーネント](../core/xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="4e0c1-122">[XML Assembler Pipeline Component](../core/xml-assembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="4e0c1-123">[XML アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="4e0c1-123">[How to Configure the XML Assembler Pipeline Component](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="4e0c1-124">Pipelines-AssemblerDisassembler (BizTalk Server サンプル フォルダー)</span><span class="sxs-lookup"><span data-stu-id="4e0c1-124">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)