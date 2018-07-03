---
title: AS2 デコーダーの処理中に例外が発生しました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b5f16d2e-e83c-4e2c-84be-41b5ed012dce
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e80ce8b53e6b5eb77770d7abcf9dbfbd157d9d64
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010267"
---
# <a name="the-as2-decoder-encountered-an-exception-during-processing"></a><span data-ttu-id="59c83-102">AS2 デコーダーで、処理中に例外が発生しました</span><span class="sxs-lookup"><span data-stu-id="59c83-102">The AS2 Decoder encountered an exception during processing</span></span>
## <a name="details"></a><span data-ttu-id="59c83-103">詳細</span><span class="sxs-lookup"><span data-stu-id="59c83-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="59c83-104">製品名</span><span class="sxs-lookup"><span data-stu-id="59c83-104">Product Name</span></span>   |                                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                         |
| <span data-ttu-id="59c83-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="59c83-105">Product Version</span></span> |                                                                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                     |
|    <span data-ttu-id="59c83-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="59c83-106">Event ID</span></span>     |                                                                                                 -                                                                                                 |
|  <span data-ttu-id="59c83-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="59c83-107">Event Source</span></span>   |                                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="59c83-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="59c83-108"> EDI</span></span>                                                       |
|    <span data-ttu-id="59c83-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="59c83-109">Component</span></span>    |                                                                                            <span data-ttu-id="59c83-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="59c83-110">AS2 Engine</span></span>                                                                                             |
|  <span data-ttu-id="59c83-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="59c83-111">Symbolic Name</span></span>  |                                                                          <span data-ttu-id="59c83-112">AS2DecoderExceptionEncounteredDuringProcessing</span><span class="sxs-lookup"><span data-stu-id="59c83-112">AS2DecoderExceptionEncounteredDuringProcessing</span></span>                                                                           |
|  <span data-ttu-id="59c83-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="59c83-113">Message Text</span></span>   | <span data-ttu-id="59c83-114">AS2 デコーダで、処理中に例外が発生しました。</span><span class="sxs-lookup"><span data-stu-id="59c83-114">The AS2 Decoder encountered an exception during processing.</span></span>  <span data-ttu-id="59c83-115">メッセージと例外の詳細は次のとおり: AS2-から:"{0}"AS2-を:"{1}"MessageID:"{2}"MessageType:"{3}"例外:"{4}"</span><span class="sxs-lookup"><span data-stu-id="59c83-115">Details of the message and exception are as follows:  AS2-From:"{0}" AS2-To:"{1}" MessageID:"{2}" MessageType: "{3}" Exception:"{4}"</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="59c83-116">説明</span><span class="sxs-lookup"><span data-stu-id="59c83-116">Explanation</span></span>  
 <span data-ttu-id="59c83-117">このエラー/警告/情報イベントは、AS2 デコーダーの問題のため、受信パイプラインが受信 AS2 メッセージを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="59c83-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming AS2 message because of an issue with the AS2 Decoder.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="59c83-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="59c83-118">User Action</span></span>  
 <span data-ttu-id="59c83-119">このエラーを解決するには、AS2 エラー コードを確認してエラー状態の性質を特定します。</span><span class="sxs-lookup"><span data-stu-id="59c83-119">To resolve this error, determine the nature of the error condition by checking the AS2 error code.</span></span> <span data-ttu-id="59c83-120">AS2 エラー コードの詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプ ファイルの「AS2 エラー コード」トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="59c83-120">For more information on AS2 error codes, see the "AS2 Error Codes" topic in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] help file.</span></span>