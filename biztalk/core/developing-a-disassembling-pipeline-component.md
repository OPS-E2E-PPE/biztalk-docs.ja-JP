---
title: パイプライン コンポーネントの開発を逆アセンブル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDisassemblerComponent interface, disassembling
- pipeline components [custom], IDisassemblerComponent
- pipeline components [custom], IBaseComponent
- IBaseComponent interface, disassembling
- pipeline components [custom], disassembling
ms.assetid: 77c0aa7d-4d1b-4a8f-bef8-d38e7e4045c6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00258b86f2da320b0ec13963a96a93aca8de477a
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530925"
---
# <a name="developing-a-disassembling-pipeline-component"></a><span data-ttu-id="572b3-102">逆アセンブラー パイプライン コンポーネントの開発</span><span class="sxs-lookup"><span data-stu-id="572b3-102">Developing a Disassembling Pipeline Component</span></span>
<span data-ttu-id="572b3-103">逆アセンブラー パイプライン コンポーネントは、入力に 1 つのメッセージを受け取り、出力で、0 個以上のメッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="572b3-103">A disassembling pipeline component receives one message on input and produces zero or more messages on output.</span></span> <span data-ttu-id="572b3-104">逆アセンブラー コンポーネントは、個別のドキュメントにメッセージのインターチェンジの分割に使用されます。</span><span class="sxs-lookup"><span data-stu-id="572b3-104">Disassembling components are used to split interchanges of messages into individual documents.</span></span> <span data-ttu-id="572b3-105">逆アセンブラー コンポーネントは、次のインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="572b3-105">Disassembler components must implement the following interfaces:</span></span>  
  
- `IBaseComponent`
  
- `IDisassemblerComponent`
  
- `IComponentUI`
  
- <span data-ttu-id="572b3-106">**IPersistPropertyBag します。**</span><span class="sxs-lookup"><span data-stu-id="572b3-106">**IPersistPropertyBag .**</span></span> <span data-ttu-id="572b3-107">このインターフェイスは .NET Framework SDK ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="572b3-107">Refer to the .NET Framework SDK documentation for this interface.</span></span>  
  
  <span data-ttu-id="572b3-108">独自の逆アセンブラー コンポーネントを作成するには拡張することによって、 **FFDasmComp**または**XMLDasmComp**クラス。</span><span class="sxs-lookup"><span data-stu-id="572b3-108">You can create your own disassembling component by extending the **FFDasmComp** or **XMLDasmComp** class.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="572b3-109">カスタム逆アセンブラーを suspendqueue MessageDestination コンテキスト プロパティ設定は、作業の中断の Seek(0) をサポートするために、逆アセンブラーによって返されるストリーム必要があります。</span><span class="sxs-lookup"><span data-stu-id="572b3-109">If your custom disassembler will be setting the MessageDestination context property to SuspendQueue, the stream returned by the disassembler must to support Seek(0) for the suspension to work.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="572b3-110">カスタム パイプライン コンポーネントは、出力メッセージ用に、入力メッセージからその他のパーツをコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="572b3-110">Custom pipeline components should copy any additional parts from the input message to the output message(s).</span></span> <span data-ttu-id="572b3-111">これはさらに、パイプラインで処理するためを保持します。</span><span class="sxs-lookup"><span data-stu-id="572b3-111">This preserves them for further processing in the pipeline.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="572b3-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="572b3-112">In This Section</span></span>  
  
-   [<span data-ttu-id="572b3-113">パイプライン コンポーネントでの受信データ ストリームの処理</span><span class="sxs-lookup"><span data-stu-id="572b3-113">Handling Incoming Data Streams in Pipeline Components</span></span>](../core/handling-incoming-data-streams-in-pipeline-components.md)  
  
-   [<span data-ttu-id="572b3-114">逆アセンブラー パイプライン コンポーネントでのエンコードの処理</span><span class="sxs-lookup"><span data-stu-id="572b3-114">Handling Encoding in a Disassembler Pipeline Component</span></span>](../core/handling-encoding-in-a-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="572b3-115">フラット ファイル逆アセンブラー パイプライン コンポーネントの拡張</span><span class="sxs-lookup"><span data-stu-id="572b3-115">Extending the Flat File Disassembler Pipeline Component</span></span>](../core/extending-the-flat-file-disassembler-pipeline-component.md)