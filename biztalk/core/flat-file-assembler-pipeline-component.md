---
title: "フラット ファイル アセンブラー パイプライン コンポーネント |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components, Flat File Assembler
- Flat File Assembler [pipeline component]
ms.assetid: 3c851771-55b2-4d21-9291-d707dd66837c
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 385b1f8ea6c2ce707069cde522ea2f6712290be7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="flat-file-assembler-pipeline-component"></a><span data-ttu-id="ca93b-102">フラット ファイル アセンブラー パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ca93b-102">Flat File Assembler Pipeline Component</span></span>
<span data-ttu-id="ca93b-103">フラット ファイル アセンブラーは、個別のドキュメントを 1 つのバッチとしてまとめ、必要に応じて、ヘッダーやトレーラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="ca93b-103">A Flat File Assembler combines individual documents into a batch and optionally adds a header or trailer (or both) to it.</span></span> <span data-ttu-id="ca93b-104">フラット ファイルの詳細については、次を参照してください。[区切り記号付きレコードとフラット ファイル メッセージ](../core/flat-file-messages-with-delimited-records.md)です。</span><span class="sxs-lookup"><span data-stu-id="ca93b-104">For more information about flat files, see [Flat File Messages with Delimited Records](../core/flat-file-messages-with-delimited-records.md).</span></span> <span data-ttu-id="ca93b-105">参照してください[位置指定レコードのフラット ファイル メッセージ](../core/flat-file-messages-with-positional-records.md)です。</span><span class="sxs-lookup"><span data-stu-id="ca93b-105">Also see [Flat File Messages with Positional Records](../core/flat-file-messages-with-positional-records.md).</span></span>  
  
 <span data-ttu-id="ca93b-106">フラット ファイル アセンブラー パイプライン コンポーネントでは、受信した XML メッセージは検証されません。</span><span class="sxs-lookup"><span data-stu-id="ca93b-106">The Flat File Assembler pipeline component does not validate the incoming XML message.</span></span> <span data-ttu-id="ca93b-107">XML 検証を実行するには、送信パイプラインのプリアセンブル ステージに XML 検証コンポーネントを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca93b-107">To ensure XML validation, include the XML Validator component in the Pre-Assemble stage of the send pipeline.</span></span>  
  
 <span data-ttu-id="ca93b-108">フラット ファイル アセンブラー パイプライン コンポーネントでサポートされる変換は、Microsoft .NET Framework がサポートしている変換に限定されます。</span><span class="sxs-lookup"><span data-stu-id="ca93b-108">The Flat File Assembler pipeline component only supports conversions supported by the Microsoft .NET Framework.</span></span> <span data-ttu-id="ca93b-109">カスタム テキスト ライターに出力することで、その他のさまざまな変換を実行できます。</span><span class="sxs-lookup"><span data-stu-id="ca93b-109">Any additional conversion can be done by writing to a custom text writer.</span></span>  
  
 <span data-ttu-id="ca93b-110">フラット ファイル アセンブラー パイプライン コンポーネントの構成方法の詳細については、次を参照してください。 [、フラット ファイル アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)です。</span><span class="sxs-lookup"><span data-stu-id="ca93b-110">For information about configuring the Flat File Assembler pipeline component, see [How to Configure the Flat File Assembler Pipeline Component](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ca93b-111">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、複数のメッセージを 1 つのインターチェンジとしてアセンブルすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ca93b-111">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you cannot assemble messages into one interchange.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ca93b-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ca93b-112">In This Section</span></span>  
  
-   [<span data-ttu-id="ca93b-113">フラット ファイル アセンブラー パイプライン コンポーネントでの文字エン コード</span><span class="sxs-lookup"><span data-stu-id="ca93b-113">Character Encoding in the Flat File Assembler Pipeline Component</span></span>](../core/character-encoding-in-the-flat-file-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="ca93b-114">フラット ファイル アセンブラー パイプライン コンポーネントにおけるドキュメント構造の強化</span><span class="sxs-lookup"><span data-stu-id="ca93b-114">Document Structure Enforcement in the Flat File Assembler Pipeline Component</span></span>](../core/document-structure-enforcement-in-the-flat-file-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="ca93b-115">フラット ファイル アセンブラー パイプライン コンポーネントの区切り記号の保持</span><span class="sxs-lookup"><span data-stu-id="ca93b-115">Retaining Delimiters in the Flat File Assembler Pipeline Component</span></span>](../core/retaining-delimiters-in-the-flat-file-assembler-pipeline-component.md)