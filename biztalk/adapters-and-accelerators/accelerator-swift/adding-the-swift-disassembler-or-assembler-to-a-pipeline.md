---
title: SWIFT 逆アセンブラーまたはアセンブラーをパイプラインに追加する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, adding assembler
- assembler, adding to pipelines
- pipelines, adding disassembler
- disassembler, adding to pipelines
ms.assetid: f39eb340-fe58-4c8f-b3f2-f7686a245095
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f48317c21942e0912f88d3e48523e07728c16ad3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968003"
---
# <a name="adding-the-swift-disassembler-or-assembler-to-a-pipeline"></a><span data-ttu-id="38e2f-102">SWIFT 逆アセンブラーまたはアセンブラーをパイプラインに追加します。</span><span class="sxs-lookup"><span data-stu-id="38e2f-102">Adding the SWIFT Disassembler or Assembler to a Pipeline</span></span>
<span data-ttu-id="38e2f-103">BizTalk パイプライン デザイナを使用するには Microsoft と[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]カスタム BizTalk を作成する受信パイプラインと送信されます。</span><span class="sxs-lookup"><span data-stu-id="38e2f-103">You can use BizTalk Pipeline Designer with Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] to create custom BizTalk receive and send pipelines.</span></span> <span data-ttu-id="38e2f-104">SWIFT 逆アセンブラーは、カスタム受信パイプラインの「逆アセンブル」段階を使用できます。</span><span class="sxs-lookup"><span data-stu-id="38e2f-104">You can use the SWIFT disassembler for the "disassemble" stage in a custom receive pipeline.</span></span> <span data-ttu-id="38e2f-105">同様に、カスタム送信パイプラインの「アセンブル」段階の SWIFT アセンブラーを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="38e2f-105">Similarly, you can use the SWIFT assembler for the "assemble" stage in a custom send pipeline.</span></span> <span data-ttu-id="38e2f-106">SWIFT 逆アセンブラーまたはアセンブラーをパイプライン デザイナーのツールボックスからを起動するには、は、パイプライン デザイナー キャンバスに、逆アセンブラーまたはアセンブラーを対応するパイプライン ステージにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="38e2f-106">To invoke the SWIFT disassembler or assembler from the Pipeline Designer toolbox, you drag the disassembler or assembler onto the corresponding pipeline stage on the Pipeline Designer canvas.</span></span> <span data-ttu-id="38e2f-107">逆アセンブラーまたはアセンブラーを呼び出す方法について詳しい手順については、「[モジュール 3: パイプライン プロジェクトの追加](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md)でエンド ツー エンド チュートリアル。</span><span class="sxs-lookup"><span data-stu-id="38e2f-107">For step-by-step instructions about invoking the disassembler or assembler, see [Module 3: Adding a Pipeline Project](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md) in the End-to-End Tutorial.</span></span> <span data-ttu-id="38e2f-108">パイプライン プロジェクトでの作業やパイプライン デザイナーに関する詳細については、BizTalk Server のヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="38e2f-108">For more information about the Pipeline Designer or working with pipeline projects, see BizTalk Server Help.</span></span>  
  
 <span data-ttu-id="38e2f-109">仕様では、SWIFT 逆アセンブラーに「逆アセンブル」ステージが必要ですが、*最終的な*呼び出される受信パイプラインのステージ。</span><span class="sxs-lookup"><span data-stu-id="38e2f-109">By design, the SWIFT disassembler expects the "disassemble" stage to be the *final* stage of the receive pipeline that is invoked.</span></span> <span data-ttu-id="38e2f-110">すべての後続のステージを使用すると、予期しない動作 (いない後続のステージを呼び出し、このような逆アセンブラーまたはが以前設定され、メッセージ ボックスに、メッセージを発行する前に昇格するコンテキスト プロパティを削除する逆アセンブラーデータベースの場合)。</span><span class="sxs-lookup"><span data-stu-id="38e2f-110">Using any subsequent stages will result in unexpected behavior (such the disassembler not invoking subsequent stages, or the disassembler removing context properties that it had previously populated and promoted before publishing the message to the MessageBox database).</span></span> <span data-ttu-id="38e2f-111">SWIFT アセンブラーを「アセンブル」段階が必要ですが、同様に、*最初*送信パイプラインのステージ。</span><span class="sxs-lookup"><span data-stu-id="38e2f-111">Similarly, the SWIFT assembler expects the "assemble" stage to be the *first* stage of the send pipeline.</span></span> <span data-ttu-id="38e2f-112">前のステージを使用して SWIFT アセンブラーが動的メッセージ型の探索が損なわれる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="38e2f-112">Using any preceding stages may impair dynamic message type discovery by the SWIFT assembler.</span></span>  
  
 <span data-ttu-id="38e2f-113">SWIFT 逆アセンブラーおよびアセンブラーは、それらを使用するときに、パイプライン デザイナー ツールボックス最初に手動で追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38e2f-113">You must manually add the SWIFT disassembler and assembler to the Pipeline Designer toolbox the first time you use them.</span></span> <span data-ttu-id="38e2f-114">これを行うための手順の詳細については[モジュール 3: パイプライン プロジェクトの追加](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md)でエンド ツー エンド チュートリアル。</span><span class="sxs-lookup"><span data-stu-id="38e2f-114">Step-by-step instructions for doing this are detailed in [Module 3: Adding a Pipeline Project](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md) in the End-to-End Tutorial.</span></span> <span data-ttu-id="38e2f-115">コンポーネントは引き続き手動で追加すると、ツールボックスに表示されます (手動で削除するまで、またはアンインストールする[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="38e2f-115">The components will continue to appear in the toolbox once you manually add them (until you manually remove them or until you uninstall [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38e2f-116">参照</span><span class="sxs-lookup"><span data-stu-id="38e2f-116">See Also</span></span>  
 [<span data-ttu-id="38e2f-117">SWIFT 逆アセンブラーおよびアセンブラーの操作</span><span class="sxs-lookup"><span data-stu-id="38e2f-117">Working with the SWIFT Disassembler and Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)