---
title: 無効か見つかりません ASN.1 圧縮ヘッダー圧縮解除処理中に発生した |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e59afea-436c-42c0-b424-0b72dd9db9a8
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f1329fd8afd46ad48d014a173dd1680d12462e2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348011"
---
# <a name="invalid-or-missing-asn1-compressed-header-encountered-during-decompression-processing"></a><span data-ttu-id="9deb9-102">圧縮解除処理中に無効な ASN.1 圧縮ヘッダーが検出されたか、ASN.1 圧縮ヘッダーが見つかりませんでした</span><span class="sxs-lookup"><span data-stu-id="9deb9-102">Invalid or missing ASN.1 compressed header encountered during decompression processing</span></span>
## <a name="details"></a><span data-ttu-id="9deb9-103">詳細</span><span class="sxs-lookup"><span data-stu-id="9deb9-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="9deb9-104">製品名</span><span class="sxs-lookup"><span data-stu-id="9deb9-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="9deb9-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="9deb9-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="9deb9-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="9deb9-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="9deb9-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="9deb9-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="9deb9-108">EDI</span><span class="sxs-lookup"><span data-stu-id="9deb9-108">EDI</span></span> |
|    <span data-ttu-id="9deb9-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9deb9-109">Component</span></span>    |                                       <span data-ttu-id="9deb9-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="9deb9-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="9deb9-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="9deb9-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="9deb9-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="9deb9-112">Message Text</span></span>   | <span data-ttu-id="9deb9-113">圧縮解除処理中に無効な ASN.1 圧縮ヘッダーが検出されたか、ASN.1 圧縮ヘッダーが見つかりませんでした</span><span class="sxs-lookup"><span data-stu-id="9deb9-113">Invalid or missing ASN.1 compressed header encountered during decompression processing</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="9deb9-114">説明</span><span class="sxs-lookup"><span data-stu-id="9deb9-114">Explanation</span></span>  
 <span data-ttu-id="9deb9-115">このエラーは、圧縮データの ASN.1 構造に関係しています。</span><span class="sxs-lookup"><span data-stu-id="9deb9-115">This error refers to the ASN.1 structure of the compressed data.</span></span> <span data-ttu-id="9deb9-116">このエラーは、圧縮データの送信者が作成した圧縮データの構造に誤りがあるか、メッセージの改ざん (無許可の変更) があったことを示します。</span><span class="sxs-lookup"><span data-stu-id="9deb9-116">The error indicates the sender of the compressed data either structured the compressed data incorrectly or there was tampering (unauthorized change) of the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9deb9-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="9deb9-117">User Action</span></span>  
 <span data-ttu-id="9deb9-118">圧縮データの構造を見直し、メッセージの改ざんがないかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="9deb9-118">Review the structure of the compressed data and check for tampering with the message.</span></span>