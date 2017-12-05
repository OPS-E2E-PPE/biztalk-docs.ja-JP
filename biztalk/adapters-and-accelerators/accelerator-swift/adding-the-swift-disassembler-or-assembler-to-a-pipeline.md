---
title: "SWIFT 逆アセンブラーまたはアセンブラーをパイプラインに追加する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipelines, adding assembler
- assembler, adding to pipelines
- pipelines, adding disassembler
- disassembler, adding to pipelines
ms.assetid: f39eb340-fe58-4c8f-b3f2-f7686a245095
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0648e6c51d83a95fb24b36d872e06e157480c5fb
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="adding-the-swift-disassembler-or-assembler-to-a-pipeline"></a><span data-ttu-id="13ca2-102">SWIFT 逆アセンブラーまたはアセンブラーをパイプラインに追加します。</span><span class="sxs-lookup"><span data-stu-id="13ca2-102">Adding the SWIFT Disassembler or Assembler to a Pipeline</span></span>
<span data-ttu-id="13ca2-103">BizTalk パイプライン デザイナを使用する[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]カスタム BizTalk を作成する受信および送信パイプラインです。</span><span class="sxs-lookup"><span data-stu-id="13ca2-103">You can use BizTalk Pipeline Designer with [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] to create custom BizTalk receive and send pipelines.</span></span> <span data-ttu-id="13ca2-104">「逆アセンブル」カスタム受信パイプラインのステージの SWIFT の逆アセンブラーを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="13ca2-104">You can use the SWIFT disassembler for the "disassemble" stage in a custom receive pipeline.</span></span> <span data-ttu-id="13ca2-105">同様に、カスタム送信パイプラインで"をアセンブル"ステージの SWIFT アセンブラーを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="13ca2-105">Similarly, you can use the SWIFT assembler for the "assemble" stage in a custom send pipeline.</span></span> <span data-ttu-id="13ca2-106">呼び出すには、SWIFT 逆アセンブラーまたはアセンブラー パイプライン デザイナーのツールボックスは、パイプライン デザイナー キャンバスに逆アセンブラーまたはアセンブラー対応するパイプラインのステージにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="13ca2-106">To invoke the SWIFT disassembler or assembler from the Pipeline Designer toolbox, you drag the disassembler or assembler onto the corresponding pipeline stage on the Pipeline Designer canvas.</span></span> <span data-ttu-id="13ca2-107">逆アセンブラーまたはアセンブラーの呼び出しについての詳しい手順については、「[第 3 章: パイプライン プロジェクトを追加する](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md)、エンド ツー エンド チュートリアル」でします。</span><span class="sxs-lookup"><span data-stu-id="13ca2-107">For step-by-step instructions about invoking the disassembler or assembler, see [Module 3: Adding a Pipeline Project](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md) in the End-to-End Tutorial.</span></span> <span data-ttu-id="13ca2-108">詳細については、パイプライン デザイナーまたはパイプライン プロジェクトでの作業では、BizTalk Server ヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="13ca2-108">For more information about the Pipeline Designer or working with pipeline projects, see BizTalk Server Help.</span></span>  
  
 <span data-ttu-id="13ca2-109">仕様では、SWIFT の逆アセンブラーである「逆アセンブル」ステージが必要ですが、*最終*呼び出される受信パイプラインのステージ。</span><span class="sxs-lookup"><span data-stu-id="13ca2-109">By design, the SWIFT disassembler expects the "disassemble" stage to be the *final* stage of the receive pipeline that is invoked.</span></span> <span data-ttu-id="13ca2-110">すべての後続のステージを使用すると、予期しない動作 (後続のステージを呼び出していない、このような逆アセンブラーや逆アセンブラーが以前設定と、メッセージ ボックスに、メッセージを発行する前に昇格されたコンテキスト プロパティを削除します。データベースの場合)。</span><span class="sxs-lookup"><span data-stu-id="13ca2-110">Using any subsequent stages will result in unexpected behavior (such the disassembler not invoking subsequent stages, or the disassembler removing context properties that it had previously populated and promoted before publishing the message to the MessageBox database).</span></span> <span data-ttu-id="13ca2-111">SWIFT アセンブラー"をアセンブル"ステージをするが必要ですが、同様に、*最初*送信パイプラインのステージ。</span><span class="sxs-lookup"><span data-stu-id="13ca2-111">Similarly, the SWIFT assembler expects the "assemble" stage to be the *first* stage of the send pipeline.</span></span> <span data-ttu-id="13ca2-112">前のステージを使用すると、SWIFT アセンブラーによって動的なメッセージの種類の探索が損なわれる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="13ca2-112">Using any preceding stages may impair dynamic message type discovery by the SWIFT assembler.</span></span>  
  
 <span data-ttu-id="13ca2-113">それらを使用するパイプライン デザイナー ツールボックス最初の時刻に SWIFT 逆アセンブラおよびアセンブラを手動で追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13ca2-113">You must manually add the SWIFT disassembler and assembler to the Pipeline Designer toolbox the first time you use them.</span></span> <span data-ttu-id="13ca2-114">これを行うための手順の詳細については[第 3 章: パイプライン プロジェクトを追加する](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md)エンド ツー エンド チュートリアル」でします。</span><span class="sxs-lookup"><span data-stu-id="13ca2-114">Step-by-step instructions for doing this are detailed in [Module 3: Adding a Pipeline Project](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md) in the End-to-End Tutorial.</span></span> <span data-ttu-id="13ca2-115">手動で追加すると、ツールボックスに表示するには、コンポーネントが続行されます (手動で削除するまで、またはアンインストールする[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="13ca2-115">The components will continue to appear in the toolbox once you manually add them (until you manually remove them or until you uninstall [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13ca2-116">参照</span><span class="sxs-lookup"><span data-stu-id="13ca2-116">See Also</span></span>  
 [<span data-ttu-id="13ca2-117">SWIFT 逆アセンブラーおよびアセンブラーの操作</span><span class="sxs-lookup"><span data-stu-id="13ca2-117">Working with the SWIFT Disassembler and Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)