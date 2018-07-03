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
ms.openlocfilehash: 843958cdfe00a9fc9d1a2c178cb85adfe4ffc8d7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999723"
---
# <a name="developing-a-disassembling-pipeline-component"></a><span data-ttu-id="25394-102">逆アセンブラー パイプライン コンポーネントの開発</span><span class="sxs-lookup"><span data-stu-id="25394-102">Developing a Disassembling Pipeline Component</span></span>
<span data-ttu-id="25394-103">逆アセンブラー パイプライン コンポーネントは入力時に 1 通のメッセージを受け取り、出力時に 0 通以上のメッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="25394-103">A disassembling pipeline component receives one message on input and produces zero or more messages on output.</span></span> <span data-ttu-id="25394-104">逆アセンブラー コンポーネントは、メッセージのインターチェンジを個別のドキュメントに分割するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="25394-104">Disassembling components are used to split interchanges of messages into individual documents.</span></span> <span data-ttu-id="25394-105">逆アセンブラー コンポーネントは次のインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="25394-105">Disassembler components must implement the following interfaces:</span></span>  
  
- `IBaseComponent`
  
- `IDisassemblerComponent`
  
- `IComponentUI`
  
- <span data-ttu-id="25394-106">**IPersistPropertyBag します。**</span><span class="sxs-lookup"><span data-stu-id="25394-106">**IPersistPropertyBag .**</span></span> <span data-ttu-id="25394-107">(このインターフェイスについては、.NET Framework SDK のドキュメントを参照してください)</span><span class="sxs-lookup"><span data-stu-id="25394-107">Refer to the .NET Framework SDK documentation for this interface.</span></span>  
  
  <span data-ttu-id="25394-108">独自の逆アセンブラー コンポーネントを作成するには拡張することによって、 **FFDasmComp**または**XMLDasmComp**クラス。</span><span class="sxs-lookup"><span data-stu-id="25394-108">You can create your own disassembling component by extending the **FFDasmComp** or **XMLDasmComp** class.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="25394-109">カスタム逆アセンブラーで MessageDestination コンテキスト プロパティを SuspendQueue に設定する場合、逆アセンブラーから返されるストリームでは保留が動作するように Seek(0) をサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="25394-109">If your custom disassembler will be setting the MessageDestination context property to SuspendQueue, the stream returned by the disassembler must to support Seek(0) for the suspension to work.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="25394-110">カスタム パイプライン コンポーネントでは入力メッセージの追加部分を出力メッセージにコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="25394-110">Custom pipeline components should copy any additional parts from the input message to the output message(s).</span></span> <span data-ttu-id="25394-111">これにより、パイプラインでの後続の処理のために追加部分が保持されます。</span><span class="sxs-lookup"><span data-stu-id="25394-111">This preserves them for further processing in the pipeline.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="25394-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="25394-112">In This Section</span></span>  
  
-   [<span data-ttu-id="25394-113">パイプライン コンポーネントでの受信データ ストリームの処理</span><span class="sxs-lookup"><span data-stu-id="25394-113">Handling Incoming Data Streams in Pipeline Components</span></span>](../core/handling-incoming-data-streams-in-pipeline-components.md)  
  
-   [<span data-ttu-id="25394-114">逆アセンブラー パイプライン コンポーネントでのエンコードの処理</span><span class="sxs-lookup"><span data-stu-id="25394-114">Handling Encoding in a Disassembler Pipeline Component</span></span>](../core/handling-encoding-in-a-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="25394-115">フラット ファイル逆アセンブラー パイプライン コンポーネントの拡張</span><span class="sxs-lookup"><span data-stu-id="25394-115">Extending the Flat File Disassembler Pipeline Component</span></span>](../core/extending-the-flat-file-disassembler-pipeline-component.md)