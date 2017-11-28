---
title: "BizTalk Framework 逆アセンブラー パイプライン コンポーネント |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components, BizTalk Framework Disassembler
- BizTalk Framework Disassembler [pipeline component]
ms.assetid: 48d6c530-5c02-4c70-ad11-0ea6c3c808f8
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1ab54ddb9ef0b5fa389e6716fc4426978dcbd7a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-framework-disassembler-pipeline-component"></a><span data-ttu-id="c5647-102">BizTalk Framework 逆アセンブラー パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c5647-102">BizTalk Framework Disassembler Pipeline Component</span></span>
<span data-ttu-id="c5647-103">BizTalk Framework 逆アセンブラー パイプライン コンポーネントでは、XML データを解析して、そのデータに BizTalk Framework ベースのメッセージ ペイロードが含まれるかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="c5647-103">The BizTalk Framework Disassembler pipeline component parses XML data and determines whether it contains a BizTalk Framework-based messaging payload.</span></span> <span data-ttu-id="c5647-104">メッセージ コンテキストはこのパイプライン コンポーネントによって保存され、必要な BizTalk Framework プロパティを生成した上で、新しいメッセージ コンテキストが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c5647-104">The pipeline component saves the message context, and a new message context is created with the BizTalk Framework property that needs to be generated.</span></span> <span data-ttu-id="c5647-105">このプロパティは、処理の対象となるメッセージを BizTalk Framework の受信ハンドラーにルーティングする際に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c5647-105">This property is used to route the message to the BizTalk Framework inbound handler, so it can receive the message to process.</span></span>  
  
 <span data-ttu-id="c5647-106">BizTalk Framework 逆アセンブラー パイプライン コンポーネントは、送信元から送られてきた BizTalk Framework エンベロープ内の deliverReceiptRequest ヘッダーを見て、必要に応じて、生成されたメッセージの受信確認を生成します。</span><span class="sxs-lookup"><span data-stu-id="c5647-106">The BizTalk Framework Disassembler pipeline component generates an acknowledgment for the generated message if the sender requested one using the deliverReceiptRequest header within the BizTalk Framework envelope.</span></span> <span data-ttu-id="c5647-107">これは、BizTalk Framework アセンブラー パイプライン コンポーネントの配信確認メッセージ要求の生成プロパティによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="c5647-107">This is controlled by the generate delivery receipt property in the BizTalk Framework Assembler pipeline component.</span></span> <span data-ttu-id="c5647-108">BizTalk フレームワークの詳細については、次を参照してください。 [BizTalk Framework アセンブラー パイプライン コンポーネント](../core/biztalk-framework-assembler-pipeline-component.md)です。</span><span class="sxs-lookup"><span data-stu-id="c5647-108">For more information about the BizTalk Framework, see [BizTalk Framework Assembler Pipeline Component](../core/biztalk-framework-assembler-pipeline-component.md).</span></span>  
  
 <span data-ttu-id="c5647-109">BizTalk Framework 逆アセンブラー パイプライン コンポーネントを構成して、オーケストレーションの作成については、次を参照してください。 [BizTalk Framework 逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-biztalk-framework-disassembler-pipeline-component.md)です。</span><span class="sxs-lookup"><span data-stu-id="c5647-109">For information about configuring the BizTalk Framework Disassembler pipeline component and creating the orchestration, see [How to Configure the BizTalk Framework Disassembler Pipeline Component](../core/how-to-configure-the-biztalk-framework-disassembler-pipeline-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5647-110">参照</span><span class="sxs-lookup"><span data-stu-id="c5647-110">See Also</span></span>  
 <span data-ttu-id="c5647-111">[BizTalk Framework 逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-biztalk-framework-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="c5647-111">[How to Configure the BizTalk Framework Disassembler Pipeline Component](../core/how-to-configure-the-biztalk-framework-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="c5647-112">パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c5647-112">Pipeline Components</span></span>](../core/pipeline-components.md)