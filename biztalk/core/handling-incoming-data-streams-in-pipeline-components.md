---
title: "パイプライン コンポーネントで受信したデータ ストリームを処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a1b7c4f7-99ba-4bfa-89ab-1fabfe0845d1
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20fc34da3a5c8e65f81cd6bbbb699f52506cdc6b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="handling-incoming-data-streams-in-pipeline-components"></a><span data-ttu-id="f499c-102">パイプライン コンポーネントでの受信データ ストリームの処理</span><span class="sxs-lookup"><span data-stu-id="f499c-102">Handling Incoming Data Streams in Pipeline Components</span></span>
<span data-ttu-id="f499c-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のパイプライン コンポーネント用にカスタム逆アセンブラー コードを記述する場合は、次のことを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f499c-103">The following considerations should be made when writing custom disassembler code for pipeline components in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="do-not-close-the-incoming-data-stream-in-custom-dissasember-code"></a><span data-ttu-id="f499c-104">カスタム逆アセンブラー コードで受信データ ストリームを閉じない</span><span class="sxs-lookup"><span data-stu-id="f499c-104">Do not close the incoming data stream in custom dissasember code</span></span>  
 <span data-ttu-id="f499c-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のパイプライン コンポーネント用にカスタム逆アセンブラー コードを記述する場合は、逆アセンブラー コードで受信データ ストリームを閉じないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="f499c-105">When you write custom disassembler code for pipeline components in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], ensure that you do not close the incoming data stream in the disassembler code.</span></span> <span data-ttu-id="f499c-106">入力メッセージからの受信ストリームは共有リソースであり、</span><span class="sxs-lookup"><span data-stu-id="f499c-106">The incoming stream from the input message is a shared resource.</span></span> <span data-ttu-id="f499c-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] メッセージ エンジンの、メッセージ本文の追跡コンポーネントでも使用されます。</span><span class="sxs-lookup"><span data-stu-id="f499c-107">The incoming stream is also used by the message body tracking component in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] message engine.</span></span>  
  
 <span data-ttu-id="f499c-108">暗黙的せよ明示的にせよ、受信ストリームを閉じると追跡データが失われる可能性があります。この場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のメッセージ イベントとサービス インスタンスの追跡でストリーム データを確認できなくなります。</span><span class="sxs-lookup"><span data-stu-id="f499c-108">If you either implicitly or explicitly close the incoming stream, tracking data may be lost and you will be unable to examine the stream data using message event and service instance tracking in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="use-the-seek-method-of-the-stream-class-to-set-the-data-stream-pointer-to-the-start-of-the-stream"></a><span data-ttu-id="f499c-109">Stream クラスの Seek メソッドを使い、データ ストリーム ポインターをストリームの先頭に設定する</span><span class="sxs-lookup"><span data-stu-id="f499c-109">Use the Seek method of the Stream class to set the data stream pointer to the start of the stream</span></span>  
 <span data-ttu-id="f499c-110">受信データ ストリームから、ストリームの末尾に達するまで確実にデータを読み込むようにしてください。</span><span class="sxs-lookup"><span data-stu-id="f499c-110">Ensure that you read from the incoming data stream until the end of the stream is reached.</span></span> <span data-ttu-id="f499c-111">たとえば、カスタム コードで 300 KB のデータの読み取り要求を発行し、34 KB のデータしか受信していない場合は、ストリームの末尾に達していません。</span><span class="sxs-lookup"><span data-stu-id="f499c-111">For example, if custom code makes a read request for 300 KB of data and the code only receives 34 KB of data, do not assume that the end of the stream has been reached.</span></span> <span data-ttu-id="f499c-112">カスタム コードでは常に、残り 0 バイトになるまで受信ストリームから読み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="f499c-112">The custom code should always read from the incoming stream until 0 bytes is returned.</span></span>  
  
 <span data-ttu-id="f499c-113">カスタム コンポーネント ロジックでデータ ストリームを返す前に、データ ストリーム ポインターをストリームの先頭に戻してください。</span><span class="sxs-lookup"><span data-stu-id="f499c-113">Before returning the data stream in the custom component logic, set the data stream pointer back to the start of the stream.</span></span> <span data-ttu-id="f499c-114">たとえば、このコードは、ストリームを返す前に、ストリームの先頭を指す seek メソッドを使用するためのロジックを示しています。</span><span class="sxs-lookup"><span data-stu-id="f499c-114">For example, this code illustrates logic to use the seek method to point to the beginning of the stream before returning the stream:</span></span>  
  
```  
myDataStream.Seek(0, SeekOrigin.Begin);  
return myDataStream;  
```  
  
 <span data-ttu-id="f499c-115">この操作を行わずに現在のコンポーネントでストリームを最後まで読み込んだ場合は、データ ストリーム ポインターがストリームの先頭にないため、次のコンポーネントで受信するストリームは空のストリームになります。</span><span class="sxs-lookup"><span data-stu-id="f499c-115">If you do not do this and the stream is read to the end in the current component, the next component receives what appears to be an empty stream because the data stream pointer was not set to the start of the stream.</span></span> <span data-ttu-id="f499c-116">これは、後のパイプライン コンポーネントで予期しない解析エラーや検証エラーが発生する原因となります。</span><span class="sxs-lookup"><span data-stu-id="f499c-116">This can cause unexpected parsing and validation errors in subsequent pipeline components.</span></span>