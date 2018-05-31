---
title: 動的解決のサンプルを実行している |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c933839f-13e6-4b49-9838-2773e3f99b64
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e613934c44db03cf29edbf3fff4ef34d6b946577
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22300050"
---
# <a name="running-the-dynamic-resolution-sample"></a><span data-ttu-id="b453e-102">動的解決のサンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="b453e-102">Running the Dynamic Resolution Sample</span></span>
<span data-ttu-id="b453e-103">使用例のいずれかを実行する GlobalBank.ESB BizTalk アプリケーションに適切な Microsoft BizTalk バインド ファイルをインポートしし、サンプルの入力フォルダに適切なメッセージをドロップまたはサンプルの Web サービスを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b453e-103">To execute one of the use case examples, you import the appropriate Microsoft BizTalk binding file into the GlobalBank.ESB BizTalk application and then either drop a suitable message into the sample input folder or call the sample Web service.</span></span> <span data-ttu-id="b453e-104">動的解決のサンプルには、次の 2 つの主なシナリオがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b453e-104">The Dynamic Resolution sample supports two main scenarios:</span></span>  
  
-   <span data-ttu-id="b453e-105">[動的解決のサンプルの一方向のメッセージング シナリオ](../esb-toolkit/one-way-messaging-scenarios-for-the-dynamic-resolution-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="b453e-105">[One-Way Messaging Scenarios for the Dynamic Resolution Sample](../esb-toolkit/one-way-messaging-scenarios-for-the-dynamic-resolution-sample.md).</span></span> <span data-ttu-id="b453e-106">動的解決サンプルは、Microsoft BizTalk へのポイントを文書としてファイル ドロップ フォルダーを使用してこのシナリオをサポートします。</span><span class="sxs-lookup"><span data-stu-id="b453e-106">The Dynamic Resolution sample supports this scenario using a file drop folder as the publication point into Microsoft BizTalk.</span></span>  
  
-   <span data-ttu-id="b453e-107">[動的解決のサンプルについては、双方向のメッセージング シナリオ](../esb-toolkit/two-way-messaging-scenarios-for-the-dynamic-resolution-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="b453e-107">[Two-Way Messaging Scenarios for the Dynamic Resolution Sample](../esb-toolkit/two-way-messaging-scenarios-for-the-dynamic-resolution-sample.md).</span></span> <span data-ttu-id="b453e-108">動的解決のサンプルは、パブリケーションとして http://localhost/ESB.NorthAmericanServices/CustomerOrder.asmx にある NorthAmerican Web サービスを使用してこのシナリオをサポートしている BizTalk へのポイント。</span><span class="sxs-lookup"><span data-stu-id="b453e-108">The Dynamic Resolution sample supports this scenario using the NorthAmerican Web service located at http://localhost/ESB.NorthAmericanServices/CustomerOrder.asmx as the publication point into BizTalk.</span></span>  
  
 <span data-ttu-id="b453e-109">このサンプルでの ESB ディスパッチャーと ESB ディスパッチャーの逆アセンブラー パイプライン コンポーネントの使用方法を理解するのを参照してください。 [「動的解決サンプルの動作](../esb-toolkit/how-the-dynamic-resolution-sample-works.md)です。</span><span class="sxs-lookup"><span data-stu-id="b453e-109">To understand how the sample uses the ESB Dispatcher and ESB Dispatcher Disassembler pipeline components, see [How the Dynamic Resolution Sample Works](../esb-toolkit/how-the-dynamic-resolution-sample-works.md).</span></span>