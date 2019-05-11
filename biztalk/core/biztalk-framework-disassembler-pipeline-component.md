---
title: BizTalk Framework 逆アセンブラー パイプライン コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, BizTalk Framework Disassembler
- BizTalk Framework Disassembler [pipeline component]
ms.assetid: 48d6c530-5c02-4c70-ad11-0ea6c3c808f8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36269df0c1b93ca68ffeb41d78742e926af14c92
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358052"
---
# <a name="biztalk-framework-disassembler-pipeline-component"></a><span data-ttu-id="dfd70-102">BizTalk Framework 逆アセンブラー パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="dfd70-102">BizTalk Framework Disassembler Pipeline Component</span></span>
<span data-ttu-id="dfd70-103">BizTalk Framework 逆アセンブラー パイプライン コンポーネントは、XML データを解析し、BizTalk Framework ベースのメッセージング ペイロードが含まれているかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="dfd70-103">The BizTalk Framework Disassembler pipeline component parses XML data and determines whether it contains a BizTalk Framework-based messaging payload.</span></span> <span data-ttu-id="dfd70-104">パイプライン コンポーネントが、メッセージ コンテキストを保存しを生成する必要がある BizTalk Framework プロパティを使用して、新しいメッセージ コンテキストを作成します。</span><span class="sxs-lookup"><span data-stu-id="dfd70-104">The pipeline component saves the message context, and a new message context is created with the BizTalk Framework property that needs to be generated.</span></span> <span data-ttu-id="dfd70-105">このプロパティは、BizTalk Framework の受信ハンドラーに処理するメッセージを受信できるようにメッセージをルーティングに使用されます。</span><span class="sxs-lookup"><span data-stu-id="dfd70-105">This property is used to route the message to the BizTalk Framework inbound handler, so it can receive the message to process.</span></span>  
  
 <span data-ttu-id="dfd70-106">BizTalk Framework 逆アセンブラー パイプライン コンポーネントは、1 つに、BizTalk Framework エンベロープ内の deliverReceiptRequest ヘッダーを使用して、送信側が要求された場合に生成されたメッセージの受信確認を生成します。</span><span class="sxs-lookup"><span data-stu-id="dfd70-106">The BizTalk Framework Disassembler pipeline component generates an acknowledgment for the generated message if the sender requested one using the deliverReceiptRequest header within the BizTalk Framework envelope.</span></span> <span data-ttu-id="dfd70-107">これは、BizTalk Framework アセンブラー パイプライン コンポーネントで生成配信確認メッセージのプロパティによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="dfd70-107">This is controlled by the generate delivery receipt property in the BizTalk Framework Assembler pipeline component.</span></span> <span data-ttu-id="dfd70-108">BizTalk フレームワークの詳細については、次を参照してください。 [BizTalk Framework アセンブラー パイプライン コンポーネント](../core/biztalk-framework-assembler-pipeline-component.md)します。</span><span class="sxs-lookup"><span data-stu-id="dfd70-108">For more information about the BizTalk Framework, see [BizTalk Framework Assembler Pipeline Component](../core/biztalk-framework-assembler-pipeline-component.md).</span></span>  
  
 <span data-ttu-id="dfd70-109">BizTalk Framework 逆アセンブラー パイプライン コンポーネントの構成およびオーケストレーションの作成については、次を参照してください。 [BizTalk Framework 逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-biztalk-framework-disassembler-pipeline-component.md)します。</span><span class="sxs-lookup"><span data-stu-id="dfd70-109">For information about configuring the BizTalk Framework Disassembler pipeline component and creating the orchestration, see [How to Configure the BizTalk Framework Disassembler Pipeline Component](../core/how-to-configure-the-biztalk-framework-disassembler-pipeline-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfd70-110">参照</span><span class="sxs-lookup"><span data-stu-id="dfd70-110">See Also</span></span>  
 <span data-ttu-id="dfd70-111">[BizTalk Framework 逆アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-biztalk-framework-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="dfd70-111">[How to Configure the BizTalk Framework Disassembler Pipeline Component](../core/how-to-configure-the-biztalk-framework-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="dfd70-112">パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="dfd70-112">Pipeline Components</span></span>](../core/pipeline-components.md)