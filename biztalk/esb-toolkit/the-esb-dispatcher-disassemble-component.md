---
title: "逆アセンブル コンポーネントの ESB ディスパッチャー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b1f5e46b-8f41-47f8-b22b-b9e9eaac6475
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c846ca716aef72d43e4f4a6ed75a2b20a81c351a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-esb-dispatcher-disassemble-component"></a><span data-ttu-id="023ea-102">ESB ディスパッチャーに逆アセンブル コンポーネント</span><span class="sxs-lookup"><span data-stu-id="023ea-102">The ESB Dispatcher Disassemble Component</span></span>
<span data-ttu-id="023ea-103">ESB ディスパッチャーの逆アセンブル コンポーネントは、ディスパッチャーのコンポーネントに同様の方法で送信メッセージのエンドポイントの場所のプロパティを動的に設定できます。</span><span class="sxs-lookup"><span data-stu-id="023ea-103">The ESB Dispatcher Disassemble component can dynamically set endpoint location properties for outbound messages in a similar way to the Dispatcher component.</span></span> <span data-ttu-id="023ea-104">このパイプライン コンポーネントは、Microsoft BizTalk メッセージのバッチ解除機能 (XML 逆アセンブラー クラスから継承することで、名前付き**XmlDasmComp**) ESB 行程を実行できるメカニズムをディスパッチ メッセージBizTalk パイプラインのメッセージング サービスです。</span><span class="sxs-lookup"><span data-stu-id="023ea-104">This pipeline component combines Microsoft BizTalk message de-batching functionality (by inheriting from the XML disassembler class named **XmlDasmComp**) with the message dispatching mechanism that can execute ESB itinerary messaging services in a BizTalk pipeline.</span></span>