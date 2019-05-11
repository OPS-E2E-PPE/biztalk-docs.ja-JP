---
title: パイプライン コンポーネントで受信データ ストリームの処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1b7c4f7-99ba-4bfa-89ab-1fabfe0845d1
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 691e0e28b8c3ab6cea273979a69d2eeba0135aa9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344663"
---
# <a name="handling-incoming-data-streams-in-pipeline-components"></a><span data-ttu-id="ddb41-102">パイプライン コンポーネントで受信データ ストリームの処理</span><span class="sxs-lookup"><span data-stu-id="ddb41-102">Handling Incoming Data Streams in Pipeline Components</span></span>
<span data-ttu-id="ddb41-103">カスタム逆アセンブラー パイプライン コンポーネント用にコードを記述する場合、次の考慮事項を行う必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="ddb41-103">The following considerations should be made when writing custom disassembler code for pipeline components in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="do-not-close-the-incoming-data-stream-in-custom-dissasember-code"></a><span data-ttu-id="ddb41-104">カスタム逆アセンブラー コードでの受信データ ストリームを閉じない</span><span class="sxs-lookup"><span data-stu-id="ddb41-104">Do not close the incoming data stream in custom dissasember code</span></span>  
 <span data-ttu-id="ddb41-105">カスタム逆アセンブラー パイプライン コンポーネント用にコードを記述するとき[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、逆アセンブラー コードでの受信データ ストリームが終了していないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ddb41-105">When you write custom disassembler code for pipeline components in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], ensure that you do not close the incoming data stream in the disassembler code.</span></span> <span data-ttu-id="ddb41-106">入力メッセージからの受信ストリームは、共有リソースです。</span><span class="sxs-lookup"><span data-stu-id="ddb41-106">The incoming stream from the input message is a shared resource.</span></span> <span data-ttu-id="ddb41-107">受信ストリームは、メッセージ本文の追跡コンポーネントでも使用、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ エンジン。</span><span class="sxs-lookup"><span data-stu-id="ddb41-107">The incoming stream is also used by the message body tracking component in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] message engine.</span></span>  
  
 <span data-ttu-id="ddb41-108">追跡データが失われる可能性があり、メッセージ イベントとのサービス インスタンスの追跡を使用してストリーム データを確認できなく暗黙的または明示的に、受信ストリームを閉じる場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="ddb41-108">If you either implicitly or explicitly close the incoming stream, tracking data may be lost and you will be unable to examine the stream data using message event and service instance tracking in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="use-the-seek-method-of-the-stream-class-to-set-the-data-stream-pointer-to-the-start-of-the-stream"></a><span data-ttu-id="ddb41-109">Stream クラスの Seek メソッドを使用して、ストリームの先頭に、データ ストリーム ポインターを設定するには</span><span class="sxs-lookup"><span data-stu-id="ddb41-109">Use the Seek method of the Stream class to set the data stream pointer to the start of the stream</span></span>  
 <span data-ttu-id="ddb41-110">ストリームの末尾に到達するまで、着信データ ストリームから読み取ることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ddb41-110">Ensure that you read from the incoming data stream until the end of the stream is reached.</span></span> <span data-ttu-id="ddb41-111">たとえば、カスタム コードが 300 KB のデータの読み取り要求を行うし、コードのみ 34 KB のデータを受信すると見なさないでくださいストリームの末尾に達したこと。</span><span class="sxs-lookup"><span data-stu-id="ddb41-111">For example, if custom code makes a read request for 300 KB of data and the code only receives 34 KB of data, do not assume that the end of the stream has been reached.</span></span> <span data-ttu-id="ddb41-112">0 バイトのデータが返されるまで、カスタム コードは、受信ストリームから読み取り常にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddb41-112">The custom code should always read from the incoming stream until 0 bytes is returned.</span></span>  
  
 <span data-ttu-id="ddb41-113">カスタム コンポーネントでデータ ストリームを返す前に、ロジックはストリームの先頭に戻る、データ ストリーム ポインターを設定します。</span><span class="sxs-lookup"><span data-stu-id="ddb41-113">Before returning the data stream in the custom component logic, set the data stream pointer back to the start of the stream.</span></span> <span data-ttu-id="ddb41-114">たとえば、このコードは、seek メソッドを使用して、ストリームを返す前に、ストリームの先頭を指すようにするためのロジックを示しています。</span><span class="sxs-lookup"><span data-stu-id="ddb41-114">For example, this code illustrates logic to use the seek method to point to the beginning of the stream before returning the stream:</span></span>  
  
```  
myDataStream.Seek(0, SeekOrigin.Begin);  
return myDataStream;  
```  
  
 <span data-ttu-id="ddb41-115">これを行わないし、現在のコンポーネントで最後に、ストリームは読み取り専用された場合、次のコンポーネントは、データ ストリーム ポインターがストリームの先頭に設定されていないため、空のストリームに見えるものを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ddb41-115">If you do not do this and the stream is read to the end in the current component, the next component receives what appears to be an empty stream because the data stream pointer was not set to the start of the stream.</span></span> <span data-ttu-id="ddb41-116">後のパイプライン コンポーネントで予期しない解析と検証エラーができます。</span><span class="sxs-lookup"><span data-stu-id="ddb41-116">This can cause unexpected parsing and validation errors in subsequent pipeline components.</span></span>