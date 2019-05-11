---
title: 無効な Adler32 チェックサムが検出されました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa47a208-0f33-496e-8dbe-b50be9979bf2
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3f6f3cbc822aa6e71a5789914ccdbcc5731db37
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381438"
---
# <a name="invalid-adler32-checksum-encountered"></a><span data-ttu-id="366ae-102">無効な Adler32 チェックサムが検出されました</span><span class="sxs-lookup"><span data-stu-id="366ae-102">Invalid Adler32 checksum encountered</span></span>
## <a name="details"></a><span data-ttu-id="366ae-103">詳細</span><span class="sxs-lookup"><span data-stu-id="366ae-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="366ae-104">製品名</span><span class="sxs-lookup"><span data-stu-id="366ae-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="366ae-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="366ae-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="366ae-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="366ae-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="366ae-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="366ae-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="366ae-108">EDI</span><span class="sxs-lookup"><span data-stu-id="366ae-108">EDI</span></span> |
|    <span data-ttu-id="366ae-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="366ae-109">Component</span></span>    |                                       <span data-ttu-id="366ae-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="366ae-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="366ae-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="366ae-111">Symbolic Name</span></span>  |                     <span data-ttu-id="366ae-112">InvalidAdler32ChecksumInCompressedMessageError</span><span class="sxs-lookup"><span data-stu-id="366ae-112">InvalidAdler32ChecksumInCompressedMessageError</span></span>                     |
|  <span data-ttu-id="366ae-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="366ae-113">Message Text</span></span>   |                          <span data-ttu-id="366ae-114">無効な Adler32 チェックサムが検出されました</span><span class="sxs-lookup"><span data-stu-id="366ae-114">Invalid Adler32 checksum encountered</span></span>                          |
  
## <a name="explanation"></a><span data-ttu-id="366ae-115">説明</span><span class="sxs-lookup"><span data-stu-id="366ae-115">Explanation</span></span>  
 <span data-ttu-id="366ae-116">このエラーは、圧縮データの ASN.1 構造に関係しています。</span><span class="sxs-lookup"><span data-stu-id="366ae-116">This error refers to the ASN.1 structure of the compressed data.</span></span> <span data-ttu-id="366ae-117">このエラーは、圧縮データの送信者が作成した圧縮データの構造に誤りがあるか、メッセージの改ざん (無許可の変更) があったことを示します。</span><span class="sxs-lookup"><span data-stu-id="366ae-117">The error indicates the sender of the compressed data either structured the compressed data incorrectly or there was tampering (unauthorized change) of the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="366ae-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="366ae-118">User Action</span></span>  
 <span data-ttu-id="366ae-119">使用**無効な Adler32 チェックサムが検出されました**改ざんの可能性が高いことを示します。</span><span class="sxs-lookup"><span data-stu-id="366ae-119">The use of **Invalid Adler32 checksum encountered** indicates a high probability of tampering.</span></span> <span data-ttu-id="366ae-120">表示された場合、改ざんについて確認**無効な Adler32 チェックサムが検出されました**します。</span><span class="sxs-lookup"><span data-stu-id="366ae-120">Check for tampering if you see **Invalid Adler32 checksum encountered**.</span></span>