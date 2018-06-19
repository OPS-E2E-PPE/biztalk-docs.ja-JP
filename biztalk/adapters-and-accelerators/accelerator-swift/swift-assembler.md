---
title: SWIFT アセンブラー |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assembler
- send pipelines, messages
- messages, send pipelines
ms.assetid: 2a95c7d4-da10-4058-bc2c-3efc35958e14
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91d9411cce90079e8a84fc6919bd6ebf8b2b4371
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214434"
---
# <a name="swift-assembler"></a><span data-ttu-id="527c4-102">SWIFT アセンブラー</span><span class="sxs-lookup"><span data-stu-id="527c4-102">SWIFT Assembler</span></span>
<span data-ttu-id="527c4-103">出力方向の送信パイプラインによって送信されるすべてのメッセージの処理、[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]アプリケーション (送信ポートを通じて送信されます)。</span><span class="sxs-lookup"><span data-stu-id="527c4-103">An outbound send pipeline processes all messages transmitted by an [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] application (sent through a send port).</span></span>  
  
 <span data-ttu-id="527c4-104">送信処理に関連する論理実行段階は、BizTalk 送信パイプラインを構成します。</span><span class="sxs-lookup"><span data-stu-id="527c4-104">Logical execution stages related to outbound processing make up the BizTalk send pipelines.</span></span> <span data-ttu-id="527c4-105">パイプライン コンポーネントは、サービスまたは、各ステージを実装します。</span><span class="sxs-lookup"><span data-stu-id="527c4-105">A pipeline component services or implements each stage.</span></span> <span data-ttu-id="527c4-106">具体的には、アセンブラーは、受信パイプラインのアセンブル ステージをサービスします。</span><span class="sxs-lookup"><span data-stu-id="527c4-106">In particular, the assembler services the assemble stage in the receive pipeline.</span></span> <span data-ttu-id="527c4-107">A4SWIFT は、SWIFT に固有の送信メッセージがカスタムのアセンブラー コンポーネントで処理機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="527c4-107">A4SWIFT provides SWIFT-specific outbound message processing functionality in a custom assembler component.</span></span>  
  
 <span data-ttu-id="527c4-108">SWIFT のアセンブラーは、カスタムのフラット ファイル アセンブラーでは、送信 SWIFT メッセージの処理に機能を提供し、次の機能を実行します。</span><span class="sxs-lookup"><span data-stu-id="527c4-108">The SWIFT assembler, a custom flat file assembler, provides functionality for processing outbound SWIFT messages, and performs the following functions:</span></span>  
  
-   <span data-ttu-id="527c4-109">動的にメッセージの種類を検出し、ドキュメント スキーマの解決</span><span class="sxs-lookup"><span data-stu-id="527c4-109">Dynamically discovers the message type and resolves the document schema</span></span>  
  
-   <span data-ttu-id="527c4-110">SWIFT のフラット ファイル解析された XML にシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="527c4-110">Serializes parsed XML into SWIFT flat files</span></span>  
  
 <span data-ttu-id="527c4-111">次の図は、SWIFT アセンブラー データ フローです。</span><span class="sxs-lookup"><span data-stu-id="527c4-111">The following figure shows the SWIFT assembler data flow.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro3.gif "FSA_Intro3")  
  
 <span data-ttu-id="527c4-112">SWIFT アセンブラーの詳細については、次を参照してください。 [SWIFT 逆アセンブラおよびアセンブラ扱う](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)です。</span><span class="sxs-lookup"><span data-stu-id="527c4-112">For more information about the SWIFT assembler, see [Working with the SWIFT Disassembler and Assembler](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="527c4-113">参照</span><span class="sxs-lookup"><span data-stu-id="527c4-113">See Also</span></span>  
 [<span data-ttu-id="527c4-114">BizTalk Accelerator for SWIFT のランタイム</span><span class="sxs-lookup"><span data-stu-id="527c4-114">BizTalk Accelerator for SWIFT Runtime</span></span>](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)