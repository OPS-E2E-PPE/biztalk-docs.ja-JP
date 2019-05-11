---
title: カスタム ハンドラーを使用して例外を送信する外部の処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53fa661e-d391-47c0-92d5-1d0c45b5963d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ec780adcc28318eb76c3dd00aa1f5081323105b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400788"
---
# <a name="handling-externally-submitted-exceptions-using-a-custom-handler"></a><span data-ttu-id="26793-102">カスタム ハンドラーを使用して例外を送信する外部の処理</span><span class="sxs-lookup"><span data-stu-id="26793-102">Handling Externally Submitted Exceptions Using a Custom Handler</span></span>
<span data-ttu-id="26793-103">このユース ケースでは、外部のクライアントは、Web サービスを通じた例外メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="26793-103">In this use case, an external client submits an exception message through a Web service.</span></span> <span data-ttu-id="26793-104">ESB 例外エンコーダー パイプライン コンポーネントを事前構成済み、送信ポートをサブスクライブするエラー メッセージ。処理し、表示できる、Microsoft InfoPath を使用して図 1 に示すようにディスク ファイルとして保存します。</span><span class="sxs-lookup"><span data-stu-id="26793-104">A send port, preconfigured with the ESB Exception Encoder pipeline component, subscribes to the fault message; it processes and persists it as a disk file that you can view using Microsoft InfoPath, as shown in Figure 1.</span></span>  
  
 <span data-ttu-id="26793-105">![外部例外の処理](../esb-toolkit/media/ch3-handlingexternalexceptions.gif "Ch3 HandlingExternalExceptions")</span><span class="sxs-lookup"><span data-stu-id="26793-105">![Handling External Exceptions](../esb-toolkit/media/ch3-handlingexternalexceptions.gif "Ch3-HandlingExternalExceptions")</span></span>  
  
 <span data-ttu-id="26793-106">**図 1**</span><span class="sxs-lookup"><span data-stu-id="26793-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="26793-107">**受信の例外またはエラー メッセージを処理し、ディスク ファイルに保存します。**</span><span class="sxs-lookup"><span data-stu-id="26793-107">**Handling incoming exception or fault messages and persisting to a disk file**</span></span>  
  
 <span data-ttu-id="26793-108">例外処理サービス サンプルに含まれている、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示します。</span><span class="sxs-lookup"><span data-stu-id="26793-108">The Exception Handling Service Sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="26793-109">格納される外部のアプリケーションからのエラー メッセージを送信する汎用メカニズムとして、ESB 例外サービスを使用する方法を示しています、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]例外管理データベース。</span><span class="sxs-lookup"><span data-stu-id="26793-109">It shows how to use the ESB Exception Service as a universal mechanism to submit fault messages from external applications that will be stored in the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] exception management database.</span></span> <span data-ttu-id="26793-110">詳細については、次を参照してください。[例外処理サービス サンプルを実行している](../esb-toolkit/running-the-exception-handling-service-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="26793-110">For more information, see [Running the Exception Handling Service Sample](../esb-toolkit/running-the-exception-handling-service-sample.md).</span></span>