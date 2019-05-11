---
title: フラット ファイル アセンブラー パイプライン コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, Flat File Assembler
- Flat File Assembler [pipeline component]
ms.assetid: 3c851771-55b2-4d21-9291-d707dd66837c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 666a6612be354b1c5cda9f1c4f40a3702cadfb78
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387931"
---
# <a name="flat-file-assembler-pipeline-component"></a><span data-ttu-id="55c9e-102">フラット ファイル アセンブラー パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="55c9e-102">Flat File Assembler Pipeline Component</span></span>
<span data-ttu-id="55c9e-103">フラット ファイル アセンブラーでは、個々 のドキュメントをバッチに結合し、必要に応じて、ヘッダーまたはトレーラー (またはその両方) を追加します。</span><span class="sxs-lookup"><span data-stu-id="55c9e-103">A Flat File Assembler combines individual documents into a batch and optionally adds a header or trailer (or both) to it.</span></span> <span data-ttu-id="55c9e-104">フラット ファイルの詳細については、次を参照してください。[で区切られたレコードのフラット ファイル メッセージ](../core/flat-file-messages-with-delimited-records.md)します。</span><span class="sxs-lookup"><span data-stu-id="55c9e-104">For more information about flat files, see [Flat File Messages with Delimited Records](../core/flat-file-messages-with-delimited-records.md).</span></span> <span data-ttu-id="55c9e-105">参照してください[位置指定レコードのフラット ファイル メッセージ](../core/flat-file-messages-with-positional-records.md)します。</span><span class="sxs-lookup"><span data-stu-id="55c9e-105">Also see [Flat File Messages with Positional Records](../core/flat-file-messages-with-positional-records.md).</span></span>  
  
 <span data-ttu-id="55c9e-106">フラット ファイル アセンブラー パイプライン コンポーネントは、受信 XML メッセージを検証しません。</span><span class="sxs-lookup"><span data-stu-id="55c9e-106">The Flat File Assembler pipeline component does not validate the incoming XML message.</span></span> <span data-ttu-id="55c9e-107">XML 検証を確認するには、するには、送信パイプラインのプリアセンブル ステージでは、XML 検証コンポーネントを含めます。</span><span class="sxs-lookup"><span data-stu-id="55c9e-107">To ensure XML validation, include the XML Validator component in the Pre-Assemble stage of the send pipeline.</span></span>  
  
 <span data-ttu-id="55c9e-108">フラット ファイル アセンブラー パイプライン コンポーネントは、Microsoft .NET Framework でサポートされる変換のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="55c9e-108">The Flat File Assembler pipeline component only supports conversions supported by the Microsoft .NET Framework.</span></span> <span data-ttu-id="55c9e-109">カスタム テキスト ライターに書き込むことで、追加の変換を実行できます。</span><span class="sxs-lookup"><span data-stu-id="55c9e-109">Any additional conversion can be done by writing to a custom text writer.</span></span>  
  
 <span data-ttu-id="55c9e-110">フラット ファイル アセンブラー パイプライン コンポーネントの構成方法の詳細については、次を参照してください。[フラット ファイル アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)します。</span><span class="sxs-lookup"><span data-stu-id="55c9e-110">For information about configuring the Flat File Assembler pipeline component, see [How to Configure the Flat File Assembler Pipeline Component](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="55c9e-111">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージを 1 つのインターチェンジにアセンブルできません。</span><span class="sxs-lookup"><span data-stu-id="55c9e-111">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you cannot assemble messages into one interchange.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="55c9e-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="55c9e-112">In This Section</span></span>  
  
-   [<span data-ttu-id="55c9e-113">フラット ファイル アセンブラー パイプライン コンポーネントでの文字エンコード</span><span class="sxs-lookup"><span data-stu-id="55c9e-113">Character Encoding in the Flat File Assembler Pipeline Component</span></span>](../core/character-encoding-in-the-flat-file-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="55c9e-114">フラット ファイル アセンブラー パイプライン コンポーネントにおけるドキュメント構造の強化</span><span class="sxs-lookup"><span data-stu-id="55c9e-114">Document Structure Enforcement in the Flat File Assembler Pipeline Component</span></span>](../core/document-structure-enforcement-in-the-flat-file-assembler-pipeline-component.md)  
  
-   [<span data-ttu-id="55c9e-115">フラット ファイル アセンブラー パイプライン コンポーネントでの区切り記号の保持</span><span class="sxs-lookup"><span data-stu-id="55c9e-115">Retaining Delimiters in the Flat File Assembler Pipeline Component</span></span>](../core/retaining-delimiters-in-the-flat-file-assembler-pipeline-component.md)