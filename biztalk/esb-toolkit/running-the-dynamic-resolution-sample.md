---
title: 動的解決サンプルを実行する |Microsoft Docs
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
ms.openlocfilehash: 66a61262bab3c3abeb7a4eb7113f09d8d3f7e8db
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983131"
---
# <a name="running-the-dynamic-resolution-sample"></a><span data-ttu-id="89129-102">動的解決サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="89129-102">Running the Dynamic Resolution Sample</span></span>
<span data-ttu-id="89129-103">ユース ケースの例のいずれかを実行する GlobalBank.ESB BizTalk アプリケーションに適切な Microsoft BizTalk バインド ファイルをインポートし、サンプルの入力フォルダーに適切なメッセージをドロップするかサンプル Web サービスを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="89129-103">To execute one of the use case examples, you import the appropriate Microsoft BizTalk binding file into the GlobalBank.ESB BizTalk application and then either drop a suitable message into the sample input folder or call the sample Web service.</span></span> <span data-ttu-id="89129-104">動的解決サンプルでは、2 つの主なシナリオがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="89129-104">The Dynamic Resolution sample supports two main scenarios:</span></span>  
  
- <span data-ttu-id="89129-105">[動的解決サンプルの一方向のメッセージング シナリオ](../esb-toolkit/one-way-messaging-scenarios-for-the-dynamic-resolution-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="89129-105">[One-Way Messaging Scenarios for the Dynamic Resolution Sample](../esb-toolkit/one-way-messaging-scenarios-for-the-dynamic-resolution-sample.md).</span></span> <span data-ttu-id="89129-106">動的解決サンプルは、Microsoft BizTalk へのポイントを文書としてファイル ドロップ フォルダーを使用してこのシナリオをサポートします。</span><span class="sxs-lookup"><span data-stu-id="89129-106">The Dynamic Resolution sample supports this scenario using a file drop folder as the publication point into Microsoft BizTalk.</span></span>  
  
- <span data-ttu-id="89129-107">[動的解決サンプルの双方向のメッセージング シナリオ](../esb-toolkit/two-way-messaging-scenarios-for-the-dynamic-resolution-sample.md) します。</span><span class="sxs-lookup"><span data-stu-id="89129-107">[Two-Way Messaging Scenarios for the Dynamic Resolution Sample](../esb-toolkit/two-way-messaging-scenarios-for-the-dynamic-resolution-sample.md).</span></span> <span data-ttu-id="89129-108">動的解決サンプルは、サービスがある NorthAmerican Web を使用してこのシナリオをサポートしている http://localhost/ESB.NorthAmericanServices/CustomerOrder.asmx にパブリケーションとして BizTalk にポイントします。</span><span class="sxs-lookup"><span data-stu-id="89129-108">The Dynamic Resolution sample supports this scenario using the NorthAmerican Web service located at http://localhost/ESB.NorthAmericanServices/CustomerOrder.asmx as the publication point into BizTalk.</span></span>  
  
  <span data-ttu-id="89129-109">ESB ディスパッチャーと ESB ディスパッチャー逆アセンブラー パイプライン コンポーネントのサンプルの使用については、次を参照してください。 [、動的解決サンプルのしくみ](../esb-toolkit/how-the-dynamic-resolution-sample-works.md)します。</span><span class="sxs-lookup"><span data-stu-id="89129-109">To understand how the sample uses the ESB Dispatcher and ESB Dispatcher Disassembler pipeline components, see [How the Dynamic Resolution Sample Works](../esb-toolkit/how-the-dynamic-resolution-sample-works.md).</span></span>